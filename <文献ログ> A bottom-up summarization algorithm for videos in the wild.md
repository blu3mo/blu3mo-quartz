---
title: "<文献ログ> A bottom-up summarization algorithm for videos in the wild"
---

[https://www.researchgate.net/publication/331362582_A_bottom-up_summarization_algorithm_for_videos_in_the_wild/link/5fc4679292851c933f76ad01/download](https://www.researchgate.net/publication/331362582_A_bottom-up_summarization_algorithm_for_videos_in_the_wild/link/5fc4679292851c933f76ad01/download)

* [映像](%E6%98%A0%E5%83%8F.md)の*要約*

* 既存手法
  
  * Unsupervised vs Supervized
  * 既存はtasksがindependent
* やること
  
  * まず映像を細かめにセグメント分け
    * さすがに全フレームがisolatedな分けないし、効率のためにoversegmentする
  * 次に、importance measure (frame "energy")をはかる
    * dissimilatiry E vs representativeness E
    * dis: 前後のフレームと違い大きいほどE高い
    * rep: 前後のフレームと似てるほどE高い
  * 二つの和は、類似度についてU字形のカーブを描く感じかな?
  * 最後にenergyを元に良いとこどりをする
* 評価方法
  
  * やっぱり*主観*的なものなので*定量的*評価はむずい
  * *Open Video Project*なるものがある
  * SumMe, Tour20 datasetとかいうsummaryと元映像のセットの*データセット*もある
