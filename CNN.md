---
title: CNN
---

from *東大1S情報α*

* 「行列とベクトルの掛け算」の代わりに、[空間フィルタ](%E7%A9%BA%E9%96%93%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF.md)の処理もやるニューラルネットワーク
  * 「小さいベクトルをスカラーに変換」するフィルタを、大きいベクトル（元画像）の色々な部分（カーネル）に対してやることで、大きいベクトル（元画像）をちょっと小さくしたベクトルを得る
    * みたいな感じかな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    * この動作、確かに「*畳み込み*」って感じ
  * これをやることで、画像の中で必要な特徴を抽出する / いらない情報を排除する
    * その抽出方法も当然訓練される
* あと、畳み込みの後に*プーリング*という処理もやることが多い
  * これは、シンプルに画像の解像度を下げる処理

from #Udacity_Intro_to_Deep_Learning_with_PyTorch

* [輪郭検知](%E8%BC%AA%E9%83%AD%E6%A4%9C%E7%9F%A5.md)のとこで説明した[空間フィルタ](%E7%A9%BA%E9%96%93%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF.md)、が鍵

* フィルタを、自動で学習するのが[CNN](CNN.md)

* 複数のフィルタを自動で作り出す、そのカーネルの数がConvolutional Layerの数
  
  * あるフィルタは、犬の耳を検出できる物かもしれない
  * 別のフィルタは、犬の目を検出するかも
* 間にpooling layerってのも挟むことがある
  
  * 情報をできるだけ保ったまま、サイズを小さくするためのもの
  * 平均とる手法や、最大値取る手法などがある
    * 最大値のやつが、画像検知には向いてる（特徴のある部分を強調するから）
* CNNは、画像のdepthを増やして、widthとheightを減らしていく処理
  
  * 最初のlayerはdepthは3(rgbの場合)、だからwidthとheightの方が圧倒的に大きい
  * Conv Layerがdepthを増やす、Pooling layerがwidthとheightを減らす
    ![image](https://gyazo.com/8cf5670cb3417aba8b95954b5f481cbe/thumb/1000)
    ![image](https://gyazo.com/4a870c8d12f0cb44abb62fdda0cecb2a/thumb/1000)
