---
title:
 'DelayChat'
---

- これ: [/collab/遅延チャット](https://scrapbox.io/collab/遅延チャット)
- work with <img src='https://scrapbox.io/api/pages/blu3mo-public/axokxi/icon' alt='axokxi.icon' height="19.5"/>

- 同期性がすごい省かれたコミュニケーション
    - 緊急性のないゆるい話を、同期していない環境でできる
    - 同期性、
        - <-- 電話 -- LINE -- メール -- DelayChat -->
            - 電話: [[同期]]only
            - LINE: 同期のことも非同期のことも
            - メール: 大体非同期, でも一応同期的即レスも可能
            - DelayChat: 非同期only
        - って感じかな


- 実装の話を書いておく
- [[LINE Bot]]
    - [[Node.js]]でサーバーサイド
- [[Heroku]]を初めて使った
    - [[Heroku Scheduler]]で10分おきに[[Firebase Realtime Database]]を読んで、今届けるべきものがあるかをチェック
- [[axios]]でプッシュ通知
# ![image](https://gyazo.com/9c10a58800f6aa72d9eeac86190c9500/thumb/1000)

- [[LINE Bot]]を[[完全に理解した]]気分

- 体験記 <img src='https://scrapbox.io/api/pages/blu3mo-public/aka/icon' alt='aka.icon' height="19.5"/>
    - 手紙を書いてる気分
        - もらうと（届くと）普通に嬉しい
    - LINEとかのCHAT、普通の会話とは違った感じ
