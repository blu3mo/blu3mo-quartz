---
title: "<論文ログ> Content-Aware Dynamic Timeline for Video Browsing"
---

* *\<論文ログ> Advanced User Interfaces for Dynamic Video Browsing*に近いものを感じる
  
  * というか、↑の研究の上に積み重なる研究だった
* バーって[映像](%E6%98%A0%E5%83%8F.md)をskimしたいときに、早送りで映像の意味がほとんどわからない
  
  * *elastic*な動画再生UIでも、この問題が起きる
* 解決のために、
  
  * まず*キーフレーム*を抽出（後述）
  * その後、取れたキーフレームをあるアルゴリズムで選択する
    * 検出したヒエラルキーを活用
    * （詳しくは論文よめばわかる）
* キーフレームの取り方（論文の本質ではない）
  
  * まず、*Shot Boundary Detection*で得られた各範囲の真ん中を選ぶ
    * Shot Boundary Detectionは、映像が切り替わる場所を検出するアルゴリズム
  * 得られた各場所のあたりで短い映像を取り出す
  * カラーヒストグラムを使って、何個かの映像を一つにまとめる
    * それを繰り返して、映像の*ヒエラルキー*を作る

[https://dl.acm.org/doi/epdf/10.1145/1866029.1866053](https://dl.acm.org/doi/epdf/10.1145/1866029.1866053)
\#文献ログ
[https://www.youtube.com/watch?v=fqf_w5JE6CA](https://www.youtube.com/watch?v=fqf_w5JE6CA)
