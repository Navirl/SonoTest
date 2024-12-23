---
date: 2024-12-21T15:18:33+09:00
title: "Nintendo Entry"
tags:
 - Info
---

daily:: [2022-07-26](Daily_Note/2022-07-26.md)
up:: [Job](../Bar/Job.md)

![](Pasted%20image%2020220726100104.png)

何度も同じことを繰り返したり、煩雑でミスが頻発しそうな仕事に対して手を加えることで、仕事の流れをスムーズにしたい。それを通して、後に同じ仕事をする人たちの悩みを払拭し、より本業に深く集中できるようになる環境づくりを担っていきたい。

Q.![悩みを払拭して本業に深く集中できるようになるため](悩みを払拭して本業に深く集中できるようになるため.md)

開発や普段の生活において効率化ができるもの、楽になるものに対して日々情報を集め、どちらを使うべきかを考え方・使い心地・カスタマイズ性など多角的な視点から比較を行い、検討している。

+AR上でスマホをラケットにして、テニスを行うゲームを開発している。
ボールを打つ直前まではスマホの画面を使用してボールの場所を把握するが、いざ打つ瞬間は画面を見ずにスマホを振り、打ち返すことになる。

そのままでは写真を撮るような体勢で、画面を見たまま打つという形になることが予想されるため、ゲームのスピード感を上げてその形を封じる。また、視覚の代わりになるボール位置の手掛かりとして、ボールの位置によって変動する音、バウンドする場所に応じて別々に鳴る衝撃音、スマホのバイブレーション機能、スピーカーの振動といった変化を提供する。

+動画を制作する際に当たって、ゆっくりムービーメーカー4というソフトを使用していた。
その際、ソフトの一つ前のバージョンであるゆっくりムービーメーカー3と立ち絵のファイル形式について互換性が無かったため、3形式の立ち絵を4形式の立ち絵に変換するためのpythonプログラムを書いた。

https://gist.github.com/Navirl/721998bed99bc474669fbfa821e7767b
https://scrapbox.io/PublicPortfolio/%E5%8F%8D%E7%9C%81
https://scrapbox.io/PublicPortfolio/memo4

上記に対して、技術的に困難な課題は何だったのか、そのために何をしたのかを記入してください。※
いきなりコードを書くところから始めたところ、リネーム関数に大量のif文が入り、デバッグやメンテナンスが困難な状態に陥った。
そのためメモを書いて処理の全体を見直すことで、リネーム関数がファイル移動という別の責任を負っていることを突き止めた。その後、ファイル移動関数とリネーム関数を分割することで、柔軟に変更に対応できるようにした。

以下の年代をどのように過ごしたかを総括し、どのようなところが今のあなたらしさにつながっているか、合わせて記入してください。
中学校
図書室から多くの本を借りていた。美術部に属しており、絵を描く練習や七宝焼きの体験などを行った。ゲームに熱中した。
これにより、抽象度の高い問題に取り組むにあたり重要な、想像力の基礎を育んだ。

高校
引き続き本を借りていた。吹奏楽部にて連携について考え、三年次には文化祭の劇で音響を担当した。中国語を学んだ。
これにより、他の人と協力して得られる力の大きさ、交流することの重要性を学んだ。

Q.中国語を学んだことはあなたの人生においてどのように役立ちましたか。
なぜ台湾に行けるまで頑張らなかったのですか？

- 自分が納得していなかった
- 台湾に行くことで得られるメリットを自分ごととして受け入れられなかった
- やったこと自体は悪くないと思っている、他言語を学ぶことはその国の考え方を取り入れることなので、人生が豊かになる




大学
最初からレポートを見据え、見返しやすく頭に残るノートの付け方について、授業ごとに試行錯誤を繰り返した。興味のある授業は出来る限り出席し、見識を深めて問題に対する心構えを養った。

趣味・特技・興味のある音楽・映画・書籍・スポーツについて記入
凋叶棕という同人サークルの曲が好きです。綺麗なピアノと力強い旋律もさることながら、歌詞や曲調に込められた深い物語を決して押し付けず、ただこちらが覗き込んでいるだけ、と感じられる点がとても好きです。

動機は大きく分けて二つあります。
一つ目は、業界の要求する技術やその水準を学ぶ機会があると思ったためです。御社はゲーム業界にて有数の企業ですので、蓄積するノウハウの数や、それ自身の効率化も進んでいるのではないかと感じています。それらを学んだうえで、私の持つ視点からそれらを捉え直し、より時代に合った効率化を行うための手伝いがしたいと思い、志望しました。
二つ目は、御社のゲームが大好きであるためです。効率化により空いた時間で、昔の私のような人を含む他の人たちが楽しめるものが作られていくこの環境であれば、私はその助力が出来たことを心から喜び、それを仕事の意義として持つことが出来るからです。

働くうえで大切にしたいこと１２３
ワークライフバランス
仕事の面白さを見つけること
1年後の自分がその分野において単独で飯を食べられる人材になるか


C++
大学の授業でゲームを二つ作った。Unreal EngineでBlueprintの関数を作った。

+以外
pythonを趣味と、自己判断で一度大学の授業で使った。
processingとjavascriptを大学の授業で使いゲームを作った。

OpenGL
大学の授業でZバッファなどの基礎を学んだ。

UnityUE
Unityは自分一人で作ったのが一つ、チームで作ったのが二つある。一つは常にWebGLで確認できるように、GitHubにPushしたらWebGLが勝手にビルドされる環境を整えた。
Unreal Engineは一人で二つ作った。
全て大学の授業上である。

Git
GitはUnityでの開発や、頻繁に更新する個人的なメモの管理などに使った。
submoduleやsubtreeも一度触った。

Linux
Linuxはsudoやcatといった基本的なコマンド、ファイルシステム等について軽く勉強した。主にGoogle Colaboratoryを使用するためである。
+また、DockerはVagrantと一緒に何度か使った。なぜなら個人的に使いたいソフトがLinuxにしかなかったためである。

+Q.Dockerはどのような目的で使用したか
おそらくコレを組み合わせて使うという目的があるがために聞いてきた

経験1、想定クリテク
自身がこだわった点、工夫したところ
関数の中身を意識せず、引数だけで使えるように作った。
変更頻度が低い部分は納期の都合上妥協し、数値をそのままベタ書きした。

プログラムを作るうえで心がけ、工夫
何度も繰り返し使う記述は、すぐに関数化する。
クラスは何度も継承せず、出来る限りシンプルに作る。

バグを少なくするには
後から見ても処理の流れが分かりやすいよう、変数や関数には目的に沿った明確な名前を付け、適宜コメントを残す。

経験2、想定実践データ
自身がこだわった点、工夫したところ
検索して出る答えにすぐ飛びつかず、より新しく、よりシンプルな書き方を調べて使った。
コメントを駆使して適宜必要な部分だけデバッグした。

プログラムを作るうえで心がけ、工夫
処理を適切に分割し、小さな処理を完成させるたびに、ダミーの小さいデータを使ってテストとデバッグを行う。「今ここの処理を書いているのは何のためなのか」を常に意識する。

バグを少なくするには
処理が早いからといって初めからColabを使うのではなく、それほど処理負荷が無い部分はローカルで書いて記述とデバッグのイテレーションを高速化させ、完成してからColabを使う。


興味を持っている技術分野1
DevOps
理由1
「自分の加えた変更が本番環境にどう反映されるのか」という情報は、早期にバグを発見できるほか、自分の行った仕事に対する報酬になるため、結果開発効率が上がってより良いモノを作れるようになるから。

興味を持っている技術分野2
PC作業の自動化
理由2
何度も繰り返す単調な仕事を自動化すれば、人間は得意な想像力を発揮する仕事に集中できるため。
また、PCが不慮の事故で破損した際、スムーズなバックアップが可能になるため。

興味を持っている技術分野2
UI・UX
理由2
プログラムはあくまで処理であり、実際に顧客が触るのはUIである。よってこの分野を学べばより顧客が何を求めているのかのイメージがつきやすくなると感じたため。

興味を持っている技術分野3
クラウド技術
理由3
PCの制約に縛られず、好きなことをするため。
また、関連技術が非常に多彩であるため、学べば別の何かにも役立つと感じた。


Q.今日は気になったこと何でも聞いてくださいね

- 問題を調べようとしてサイトを見ると、大体書いてあるので解決する
- WLBも育休取得促進や介護休業、出退勤時間のコントロール制度、9時間のインターバルなど予想以上に充実していた
	- [社員：社員一人ひとりが力を発揮できる環境づくりに努めます。｜CSR情報｜任天堂](https://www.nintendo.co.jp/csr/report/employees/topics/index.html?active-topics=topics02)

[Nintendo Settings](Nintendo%20Settings.md)