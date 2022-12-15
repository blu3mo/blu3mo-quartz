---
title: Rust入門
---

*RustでAtCoder*
[可変参照｜RustCoder ―― AtCoder と Rust で始める競技プログラミング入門](https://zenn.dev/toga/books/rust-atcoder/viewer/18-mutable-reference#可変として借用されている変数の使用)

* Rustの[関数型言語](%E9%96%A2%E6%95%B0%E5%9E%8B%E8%A8%80%E8%AA%9E.md)っぽい所
  * let x = if ~~~みたいな書き方、ぽい?
  * デフォルトがimmutableで、mutableだとしても制約が色々ついてる
    * [参照透明性](%E5%8F%82%E7%85%A7%E9%80%8F%E6%98%8E%E6%80%A7.md)に近い事を目指している..?

[/villagepump/Rustlings](https://scrapbox.io/villagepump/Rustlings)

* 気になる<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

[Rustのリンク集 - Qiita](https://qiita.com/mosh/items/7e327dafbe53b72ad99d)

[Rust ツアー - Let's go on an adventure!](https://tourofrust.com/00_ja.html)

* とっかかりとして

* letはmutにしない限り変えられない
  
  * でも再宣言はできるのか
* usize, isize
  
  * 配列のindexはusize
* 配列とスライスってのがあるのね
  
  * 固定長かどうか
  * 配列は実質タプルのn個版みたいな感じか
* [RustにNullは無い](Rust%E3%81%ABNull%E3%81%AF%E7%84%A1%E3%81%84.md)

* 
   > 
   > if、match、関数、ブロックの最後が ; のない式であれば、戻り値として使用されます。 これは値を返すための簡潔なロジックを作成するのに最適な方法で、その値は新しい変数に入れることができます。

* [メモリの領域](%E3%83%A1%E3%83%A2%E3%83%AA%E3%81%AE%E9%A0%98%E5%9F%9F.md)

* RustのError
  
  * `do_something_that_might_fail(432)?`
    * は、Errorを返したら`return Err(e)`になる
  * `do_something_that_might_fail(432)?`をmain()で実行してたら、mainがerrでreturnされて終了するって仕組みか
* Vec
  
  * C++のvectorと同じ感じ
  * *ヒープメモリ*への参照をvector structが持つ
* macro
  
  * println!とかvec!とかはmacroなのね
* [Rustの所有権](Rust%E3%81%AE%E6%89%80%E6%9C%89%E6%A8%A9.md)

* ライフタイム
  
  * 造られてからdropされるまでの期間のことなのは理解した
  * ただ、lifetime specifierはいまいち掴めない
    * lifetimeってプログラムの内容によって決まることかと思ってたけど、人為的に設定してもいいの？矛盾とか大丈夫なの？という気持ち
  * static variableとかのstatic lifetimeは、プログラムの終わりまで
    * *データメモリ*に置かれるってことかな
* 感想
  
  * 結構好きだな
    * すっきりしている
    * 少ない本質的な要素で物事をやろうとしている感じがあって綺麗(?)
  * 所有権周りの制約、非同期的なコード書くのむずそう
* [macOSでRustのローカル開発環境を整えるための手順2022 - Qiita](https://qiita.com/notakaos/items/9f3ee8a3f3a0caf39f7b)
