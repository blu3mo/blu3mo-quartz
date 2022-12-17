---
title:
 'Kineto MVP実装プラン'
---

- Minimal Viable Productの方のMVP

- どこまで実装するか
    - 映像の配信
        - 送り側はRTMP送れる既存サービスで
    - 軽い独自の時間操作UI
    - ペンの共有はニコニコ方式で
        - 擬似同期的に全部表示
            - （ニコニコは別に全表示じゃないか?）
            - 同期扱いのユーザーは対話可能レベルなラグに

    - コード入力すると指定のhls配信+ペン共有に接続

    - [[アーキテクチャ]]
        - MVP
        - [https://medium.com/@rockname/clean-archirecture-7be37f34c943](https://medium.com/@rockname/clean-archirecture-7be37f34c943) これ参考に
            - 抽象化は大変なのでとりあえず一方向だけで
                - あとで（テストするときとか）両方向する
            - Delegate = Model -> Presenter
            - Interface = Presenter -> View

- 2週間しかない 2週間もある

#kineto