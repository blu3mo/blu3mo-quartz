---
title: "<論文ログ> Comparison of Automatic Shot Boundary Detection Algorithms Based On Color, Edges and Wavelets"
---

* [映像](%E6%98%A0%E5%83%8F.md)の*Shot Boundary Detection*のアルゴリズムを比較
  
  * *カラーヒストグラム*、*エッジ*、*ウェーブレット*のそれぞれを用いる方法を比較
* カラーヒストグラム
  
  * *24ビットカラー*のうち、各色上位4ビットを使って12ビットカラーにした
    * 合計2^12=4096色 #量子化
  * ヒストグラムが大きく変化する=boundary
* *エッジ方向ヒストグラム*
  
  * *エッジ方向*を使って*ヒストグラム*作る、
    * 大きく変わるやつ=boundary
* Wavelet
  
  * フーリエ変換の兄弟みたいなやつ
* 結果、カラーヒストグラムベースが映画とかには良い、waveletベースが自然とかスポーツ映像には良いって結論

* 音楽mv動画とかだとキツかった、動きとトランジション激しいし

[https://www.researchgate.net/publication/232630485_Comparison_of_Automatic_Shot_Boundary_Detection_Algorithms_Based_On_Color_Edges_and_Wavelets](https://www.researchgate.net/publication/232630485_Comparison_of_Automatic_Shot_Boundary_Detection_Algorithms_Based_On_Color_Edges_and_Wavelets)
\#文献ログ
\#画像処理
