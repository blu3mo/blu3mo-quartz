---
title:
 'GAN'
---

- 一回触ってみたい

- [https://www.imagazine.co.jp/gan%EF%BC%9A敵対的生成ネットワークとは何か%E3%80%80%EF%BD%9E%E3%80%8C教師/](https://www.imagazine.co.jp/gan%EF%BC%9A敵対的生成ネットワークとは何か%E3%80%80%EF%BD%9E%E3%80%8C教師/)
    - ![image](https://www.imagazine.co.jp/wp-content/uploads/2018/09/is20tech001zu004-1.jpg)
    - z（ノイズ）が[[シード値]]みたいなもの
        - シード値を動かすとだんだん画像が変わっていくのね
        - よくGANで生成された画像で見るやつか

[今さら聞けないGAN（1） 基本構造の理解 - Qiita](https://qiita.com/triwave33/items/1890ccc71fab6cbca87e)
- 対象読者ど真ん中な感じ
- Discriminator
    - まあこれは普通(?)の分類問題の[[ニューラルネットワーク]]って感じ
- Generator
    - [[アップサンプリング]]をする
    - 逆CNNとかはせずに、シンプルに値をreshapeするのね
        - 逆CNNをするのは[[DCGAN]]とか呼ばれるらしい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- 学習
    - 「真データを使って、Discriminatorのみを学習」
    - 「Discriminatorを使って、Generatorを訓練」
    - の二つを交互?にやる感じかな
- [[Loss Function]]
    - ![image](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.amazonaws.com%2F0%2F233208%2F78f624e8-cc53-c7a3-178c-0551048bef30.jpeg?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&w=1400&fit=max&s=e003da075ce59572516d53df27ea3ef8)
    - $\mathbb{E}$の意味がわからないな
    - Discriminatorの学習では、V(D, G)を最大化させたい
        - $\log D(x)$を最大化したい = 真データ（x）の時に1を出力させたい
        - $\log (1-D(G(z)))$を最大化したい = 偽データ（G(z)）の時に==0==を出力させたい
    - Generatorの学習の時は、V(D,G)を最小化させたい
        - $\log (1-D(G(z)))$を最小化したい = 偽データ（G(z)）の時に==1==を出力させたい
        - つまり、Discriminatorと真逆の方向に学習
