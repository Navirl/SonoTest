---
date: 2024-12-21T15:18:54+09:00
title: "UEと参照連鎖、ヘキサドライブ"
tags:
 - Info
---

daily:: [2023-01-02](/Daily_Note/2023-01-02.md)
up:: [UE](../Bar/App/Unreal_Engine.md)
source:: [BPの参照連鎖を断つ手法 | 株式会社ヘキサドライブ | HEXADRIVE | ゲーム制作を中心としたコンテンツクリエイト会社](https://hexadrive.jp/lab/tips/atc/101479/)

UEはアセットがロードされるとき、そのアセットが参照している依存アセットも一緒にロードして軽くするという手法が使われている。
待ち時間なく依存アセットを使えるので親切だが、使わない依存アセットも使ってしまうのでロード時間やらエディタの起動時間やらが遅くなる。

参照としてカウントされるのは型参照。
アセットに対してキャストや変数代入、引数戻り値関数などなど一瞬でも型を決められると参照としてロードする。

これは多重参照もカウントしてロードする。参照の参照までロードしてしまうということ。
なので気を抜くとめちゃくちゃ重くなる。


対策は抽象依存。C++クラス、BPInterfaceや手空きの親クラス、アクタータグなどを参照することで参照の連鎖を断ち切れる。

C++。参照の連鎖カウントされるのはBPのアセットなので、C++なら参照連鎖しない。
BPInterface。BPInterfaceなら目当ての機能だけ参照できる。ただしInterfaceに型情報付き変数があるともちろん参照しちゃうので注意。
親クラス。継承の末端の子クラスにだけ参照を仕込めばロードを最小限に抑えられる。これはBPInterfaceも同様。
アクタータグ。タグそのものがC++のAActorの機能なので、完全に断ち切れる。


他、つまずきやすいところとして関数ライブラリがある。
これもアセットの一つなので、ここに参照が仕込まれてたりすると関数ライブラリを使うたびに参照がざらざら増えていく。
これの対策はC++で関数ライブラリ作るか、分割するか、そもそも関数ライブラリに参照を持たせないか。

お得な情報として、Get Component by Classを使ってコンポーネントにアクセスした場合はアクタの型を参照せず依存を抑えられる。

大量にスポーンさせるアイテムやアビリティといった量産コンテンツは参照しないこと。
使うならGameplay AbilityやAnimation Montageに入れてから使う。もしくは必要な時だけ手動で読み込むSoft Object Reference。