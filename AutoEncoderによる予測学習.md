---
title: AutoEncoderによる予測学習
---

<img src='https://scrapbox.io/api/pages/blu3mo-public/情報科学の達人/icon' alt='情報科学の達人.icon' height="19.5"/> 認知ロボティクスの講義

* [AutoEncoder](Autoencoder.md)による[予測学習](%E4%BA%88%E6%B8%AC%E5%AD%A6%E7%BF%92.md)
* 物掴むタスク
  * ある瞬間の、①視界の画像、②音、③*ロボット*の*関節角度*のそれぞれを、[AutoEncoder](Autoencoder.md)で低次元の[特徴量](%E7%89%B9%E5%BE%B4%E9%87%8F.md)に変換
  * それぞれの特徴量をまとめて、[予測学習](%E4%BA%88%E6%B8%AC%E5%AD%A6%E7%BF%92.md)のある瞬間の値として扱う
  * そして予測学習にかけると、物掴むタスクができる
* *Seq2Seq*を使うと、
  * 自然言語をエンコードして、[予測学習](%E4%BA%88%E6%B8%AC%E5%AD%A6%E7%BF%92.md)的手法
