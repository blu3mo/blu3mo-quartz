---
title: AtCoderで困ったら
---

対処法の*ノウハウ*

* WAの場合
  
  * シンプルに*コーナーケース*を頑張って探す
  * intじゃ*オーバーフロー*してる可能性、llにする
    * これ、ぱっと見intで足りるように見えるけどよく考えたらループしてた、みたいなパターンもあるから注意
    * 入力がgllであるべきなのにgiになってるかも
  * 出力の形式ミス
    * 2を出すべきなのにdoubleを掛けちゃって2.0を出してるみたいなパターンもある（これは部分ACもあって怖い）
    * llの出力が、5e+11みたいに省略形式になってる可能性
* *TLE*の場合
  
  * # define \_GLIBCXX_DEBUGが邪魔してる可能性
  
  * 普通に*計算量*オーバーしてるかも
  * コンテナの意外な操作に計算量食ってるかも
  * めっちゃ入力が多い場合、giの中身がget<ll>であることが影響するかも
* 緑diffのコツ、悩んだら見てみる
  
  * [https://speakerdeck.com/furuya1223/the-view-of-green-difficulty-problems?slide=40](https://speakerdeck.com/furuya1223/the-view-of-green-difficulty-problems?slide=40)
* グラフ系はこれでビジュアライズした方が楽かも
  
  * [https://hello-world-494ec.firebaseapp.com/](https://hello-world-494ec.firebaseapp.com/)
    \#AtCoder
