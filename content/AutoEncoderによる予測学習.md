---
title:
 'AutoEncoderによる予測学習'
---

<img src='https://scrapbox.io/api/pages/blu3mo-public/情報科学の達人/icon' alt='情報科学の達人.icon' height="19.5"/> 認知ロボティクスの講義
- [[AutoEncoder]]による[[予測学習]]
- 物掴むタスク
    - ある瞬間の、①視界の画像、②音、③[[ロボット]]の[[関節角度]]のそれぞれを、[[AutoEncoder]]で低次元の[[特徴量]]に変換
    - それぞれの特徴量をまとめて、[[予測学習]]のある瞬間の値として扱う
    - そして予測学習にかけると、物掴むタスクができる
- [[Seq2Seq]]を使うと、
    - 自然言語をエンコードして、[[予測学習]]的手法