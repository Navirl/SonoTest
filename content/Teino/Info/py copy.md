---
date: 2024-12-21T15:19:15+09:00
title: "py copy"
tags:
 - Info
---

daily:: [2022-08-03](Daily_Note/2022-08-03.md)
up:: [Python](../Bar/Program/Python.md)
source:: [Pythonのcopyとdeepcopyについて - Qiita](https://qiita.com/Kaz_K/items/a3d619b9e670e689b6db)

変数にはミュータブルとイミュータブルがある。
ミュータブルは再代入可能。ほとんどがこっち。
イミュータブルは再代入不可。文字列、数字、タプルなど。

ミュータブルは新たな値を追加や連結したりしても、指すIDが変わらない。
イミュータブルは変わる。

で、**配列はミュータブル**なので、二次元配列に配列変数を代入し、配列変数を変更すると**二次元配列側も書き換わってしまう。**
それを防ぐのがcopy。

```python
# ソースコード
import copy

a = [1, 2]
b = copy.copy(a)
a.append(3)

print ("a = %s" % a)
print ("b = %s" % b)

print ("id(a) = %i" % id(a))
print ("id(b) = %i" % id(b))

# 実行結果
a = [1, 2, 3]
b = [1, 2]

id(a) = 140092728379976
id(b) = 140092728395208
```

このようにIDを書き換えることが出来るので、二次元配列もcopyした変数配列を入れてやれば無用な編集は生まれない。
なお配列の場合はスライスを使って`配列[:]`で事足りる模様。

ちなみに、二次元配列をcopyするなら`deepcopy()`を使わないと下まで完全コピーできない。