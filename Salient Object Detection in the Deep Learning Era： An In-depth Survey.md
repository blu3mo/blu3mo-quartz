---
title: Salient Object Detection in the Deep Learning Era： An In-depth Survey
---

[https://arxiv.org/pdf/1904.09146.pdf](https://arxiv.org/pdf/1904.09146.pdf)

* *画像*の*顕著性*を*ディープラーニング*で評価する系の研究まとめ
* ![image](https://gyazo.com/1497f6c0f3cee186341772cc108eedaa/thumb/1000)

 > 
 > The rest of the paper is organized as follows. §2 explains the proposed taxonomies, each accompanied with one or two most representative models. §3 examines the most notable SOD datasets, whereas §4 describes several widely used SOD metrics. §5 benchmarks several deep SOD models and provides in-depth analyses. §6 provides further discussions and presents open issues and future research directions of the field. Finally, §7 concludes the paper

* [ニューラルネットワーク](%E3%83%8B%E3%83%A5%E3%83%BC%E3%83%A9%E3%83%AB%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF.md)のアーキテクチャによる分類
  * ピクセルベースのやつと、[CNN](CNN.md)的なやつがある
* 教師のレベルによる分類
  * 人間の視線とかのアノテーションベース
  * weakなやつ（*ImageNet*みたいなやつの途中段階で物体のところがハイライトされる） #弱教師あり学習
    * [Visual complexity analysis using deep intermediate-layer features](Visual%20complexity%20analysis%20using%20deep%20intermediate-layer%20features.md)が近そう
* あと、Single Task Learning vs Multi Task Learning(*MTL*)という分類もある

![image](https://gyazo.com/7716d70fe9db014335f18f45e02c205f/thumb/1000)
