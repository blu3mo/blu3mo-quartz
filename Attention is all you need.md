---
title: Attention is all you need
---

* 原著 [https://arxiv.org/abs/1706.03762](https://arxiv.org/abs/1706.03762)

* [Transformer](Transformer.md)の提案

* [深層学習界の大前提Transformerの論文解説！ - Qiita](https://qiita.com/omiita/items/07e69aef6c156d23c538)

* 前提:
  
  * [Attention機構](Attention%E6%A9%9F%E6%A7%8B.md)
  * *Encoder-Decoderモデル*
* [Autoencoder](Autoencoder.md)の機構

[AI界を席巻する「Transformer」をゆっくり解説(2日目) ～Introduction / Background編～](https://zenn.dev/attentionplease/articles/c2dba490ccba3f)

* [RNN](RNN.md)の記憶力弱いのに対して、Transformerは強い、と
  [AI界を席巻する「Transformer」をゆっくり解説(3日目) ～Model Architecture編 1～](https://zenn.dev/attentionplease/articles/5b4133a4956578)
* ![image](https://i.imgur.com/J1Znwrs.png)

[Transformer解説：GPT-3、BERT、T5の背後にあるモデルを理解する | AI専門ニュースメディア AINOW](https://ainow.ai/2021/06/25/256107/)

* わかりやすい
* *Self Attention*
  * その単語を理解する上で大事な周辺単語への注目を推論する

[自然言語処理の必須知識 Transformer を徹底解説！ | DeepSquare](https://deepsquare.jp/2020/07/transformer/#outline__3)

* 分からない事
  * *Encoder-Decoderモデル*の構造とどう対応しているのかが分からない

 > 
 > Transformerは基本的な大枠はエンコーダ-デコーダモデルでself-attention層とPosition-wise全結合層を使用していることが特徴。
 > つまり、以下の3つ(+2つ)のことが分かればモデル構造が理解できる ので順に説明していく。
 > 
 > エンコーダ-デコーダモデル
 > Attention
 > Position-wise全結合層
 > 文字の埋め込みとソフトマックス
 > 位置エンコーディング
