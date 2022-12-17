---
title:
 'AVPlayerが止まっちゃう問題'
---

- [[kineto]]で困ってるやつ、[[Kinetoのユーザテスト1]]とか大変だった



- 再現方法
    - 再生途中に通信を悪くして、buffer先までジャンプする
        - すると映像がMinimzieStallで止まる（これは問題ない）
    - その後、バッファ範囲内に戻るとWaitingWhileEvaluatingBufferingRateReasonで止まる
        - これが不明
        - [https://developer.apple.com/documentation/avfoundation/avplayerwaitingwhileevaluatingbufferingratereason](https://developer.apple.com/documentation/avfoundation/avplayerwaitingwhileevaluatingbufferingratereason)
            - > It is recommended that you do not show UI indicating a waiting state to the user when this is the reason the player is in a wait state.
- おそらくこの再現方法に近いことが、通信環境が絶妙に悪い場所だと最初から起こるんだと思う
