---
date: 2024-12-21T15:18:41+09:00
title: "Rust Lifetime"
tags:
 - Info
---

daily:: [2023-03-07](/Daily_Note/2023-03-07.md)
up:: [Rust](../Bar/Program/Rust.md)

参照が有効になるスコープ。正確に言うとその間だけメモリを保持する期間。
スコープ外で変数を使おうとしてエラーになるのはこのライフタイムが切れているから。

ライフタイムの有効無効はRustコンパイラの借用チェッカーなるもので行われている。
中身は単純な「借用する変数とされる変数、どちらのライフタイムのほうが長いか」という比較。

```rust
fn main() {
    {
        let x = 5;            // ----------+-- 'b
                              //           |
        let r = &x;           // --+-- 'a  |
                              //   |       |
        println!("r: {}", r); //   |       |
                              // --+       |
    }                         // ----------+
}
```

逆に言うと、それが比較できないコードは安全のためエラーになる。
以下のコードはエラー。

```rust
fn main() {
    let string1 = String::from("abcd");
    let string2 = "xyz";

    let result = longest(string1.as_str(), string2);
    println!("The longest string is {}", result);
}

fn longest(x: &str, y: &str) -> &str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}

```

str1から'aを借用しxへ、str2から'bを借用しyへ。
では戻り値はどちらから借用しているのか？　借用チェッカーは何を比較すればいいのか？　これが分からないままだと、ダングリング参照(実際の値が解放済みであるアドレスへの参照)を生成しかねない。ライフタイムが切れてるほうを返してしまえば終わりである。

そこでライフタイム注釈が現れる。
これは変数の実際のライフタイムには何の影響も与えないが、少なくとも関数内ではある値同士のライフタイムが同じであると制限することが出来る。
スコープとの相違点。

```rust
fn main() {
    let string1 = String::from("abcd");
    let string2 = "xyz";

    let result = longest(string1.as_str(), string2);
    println!("The longest string is {}", result);
}

fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}

```

ここではaとしているが、これはタグみたいなもんなので別にbでもcでも動く。
引数のライフタイムを入力ライフタイム、戻り値のライフタイムを出力ライフタイムと呼ぶ。

これが問題になるのは、引数の参照をそのまま戻り値に参照で返しているから。
仮に戻り値に関数内の値を参照で返すと、関数内の値は関数内で全てライフタイムが尽きるためダング化する。これはエラーを返す。


本来はライフタイム注釈は常に必要だが、時と場合に依って省略できるケースがある。それが以下の三つ。コンパイラもこの三つを上から適用していく。

1. 各引数が独自のライフタイム引数を得る。
   `fn foo<'a, 'b>(x: &'a i32, y: &'b i32);`
2. 入力ライフタイム引数が一つの場合、そのライフタイムが全ての出力ライフタイム引数に代入される。
   `fn foo<'a>(x: &'a i32) -> &'a i32`
3. メソッドかつ`&self`のライフタイムが全出力ライフタイム引数に代入される。
   ちなみにこれのおかげでメソッドはライフタイム注釈をあまり書かなくていい。


`'`の後はタグといったが、一つ予約されてるものがある。
それが`'static`。これを付けて参照を宣言するとプログラムの全期間生存できる。プログラムのバイナリに埋め込まれるため。
文字列リテラルのライフタイムは標準でこれ。

ただしむやみに使うモノではない。大体はライフタイムの指定で何とかなるし、そうしたほうがダングリング参照が減る。

[ライフタイムで参照を検証する - The Rust Programming Language 日本語版](https://doc.rust-jp.rs/book-ja/ch10-03-lifetime-syntax.html)

これを使うのはヒープメモリのため。
ヒープメモリじゃないと解放タイミング測るなんてしないし当然。