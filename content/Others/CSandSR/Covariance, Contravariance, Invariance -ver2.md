---
date: 2022-04-29 01:28:10
tags:
 - Program/CSharp
 - Fragment
---

## Covariance, Contravariance, Invariance
### 前提
#### 1
ある一つのクラスAと、それを継承したもう一つのクラスBがあったとする。
この二つには以下の関係性が成り立つ。

| 視点 | 図 | 概要 |
| --- | --- | --- |
| 型 | ![](Images/Pasted%20image%2020220329143150.png) | B を A として扱えることから、A が B を含むイメージ |
| 実装 | ![](Images/Pasted%20image%2020220329143845.png) | A を継承した B が実装を追加することから、B が A を含むイメージ |

詳しく言うと、BはAの一種であり、Aの派生形として出発しているとみているのが上。
Aをもとに、Bは様々な機能が追加されるため、機能的にはAを包括しているとみているのが下。

どちらも正しく、説明によって使い分ける。
今回使うのは上。

#### 2
前述したAの型には、Bのインスタンスを入れることが出来る。
なぜなら、BはAの一種だから。
つまり、Aの型にはAとBのインスタンスが、Bの型にはBのインスタンスだけを受け入れることが出来る。
### 本題
元々一つの型を選んでいたとして、そこから制限を強める、つまり受け入れるインスタンスの対象範囲を狭めることを**共変**と呼ぶ。　型を継承先のクラスに変えること。
反対に、制限を弱める、受け入れるインスタンスの対象範囲を広げることは**反変**と呼ぶ。型を継承元のクラスに変えること。

覚え方は、継承が進む方向と共通なのが共変。



[共変戻り値と反変引数 - Qiita](https://qiita.com/7shi/items/39a222b5928bf0b6f745#java)

[共変戻り値と反変引数 - Qiita](共変戻り値と反変引数%20-%20Qiita.md)