---
title: Attention機構
---

とは

* [【深層学習】Attention機構とは何のか？ | DenDenBlog](https://dendenblog.xyz/what-is-attention/)

* 
   > 
   > データのどこに注目するかを推論

* 入力: contextと、注目度を評価したいデータ群
  
  * それぞれの非線形関数に(context + データの一つ)を入力して、重要度が出力される様に訓練する
* 出力: それぞれのデータの相対的重要さ

* これを、[CNN](CNN.md)とか*LSTM*とかと組み合わせる方法が今まで使われていた
  
  * [Attention is all you need](Attention%20is%20all%20you%20need.md)は、組み合わせる必要すらねぇと言っている?
