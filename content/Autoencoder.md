---
title:
 'Autoencoder'
---

<img src='https://scrapbox.io/api/pages/blu3mo-public/情報科学の達人/icon' alt='情報科学の達人.icon' height="19.5"/> 認知ロボティクスの講義
- a.k.a. [[自己符号化機]]
- 高次元の入力Xを低次元な[[特徴量]]zに[[エンコード]]し、
- 低次元の特徴量zを、高次元のX'に[[デコード]]する
- [[ニューラルネットワーク]]の[[Loss Function]]はxとx'の差
- ![image](https://lilianweng.github.io/lil-log/assets/images/autoencoder-architecture.png)
- これのデコーダーを、同じものを再現するのではない別のものにしてあげるとできることが広がる
    - 「[[Seq2Seq]]」と言う
    - 例えば
        - エンコーダが画像to低次元
        - デコーダが低次元to文章
        - --> 画像のキャプション生成ができる #画像処理 #自然言語処理
    - 例えば
        - エンコーダが日本語to低次元
        - デコーダが低次元to英語
        - --> [[機械翻訳]] #自然言語処理
#ディープラーニング
