---
title:
 'CALayerで自前スクロール実装'
---

- [[kineto]]の下のバーのために、ドラッグで動かせるバーをUIKit使わず実装したい
    - contentを出したいわけではないので、CALayerで実装

[https://youtu.be/kFrKiItslfc](https://youtu.be/kFrKiItslfc)
- （UIデザインは見苦しいけど雑、仮）
- 問題
    - {sublayer}.frameを上書きして移動させようとすると、もっさりする
    - 理由: 勝手にアニメーションされちゃう
    - 解決方法
        - [https://qiita.com/shintax/items/78f2634286c69f2e14c5](https://qiita.com/shintax/items/78f2634286c69f2e14c5)

#iOS
