---
title:
 '<論文ログ> SmartPlayer： User-Centric Video Fast-Forwarding'
---

- [[kineto]]の企画練る時にもう一回読むべき

- [[映像]]をみるときの体験として、運転中の景色のような物を実現
    - メタファーにもとづいて実現
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>今考えると、このメタファー時間と空間が融合した[[没入できる軸]]みがある
- [[速度]]を自由に見ながら調整できる #早送り #スロー再生

- 時間ないときに、既存のインターフェースだとユーザーは勘で動画を飛ばさないといけない
- 自動でやろうよ
- 映像を[[スキム]]することをサポート

- 映像[[要約]]手法は、二つのアプローチを紹介
    - still-image abstraction
        - 映像の一部の画像を並べる感じ
    - video skimming
        - 映像の一部をカットしてつなげる感じ?

- video skimmingで、初見の映像を飛ばしてくと、ユーザーは情報を逃していないか不安になる

- 機能
    - 映像の再生速度を、その時の内容の複雑さに基づいて自由に操作できる
    - 運転中にGPSナビを使うように、再生バーに重要な点が明示される(POI)
    - 自動運転的な感じで、自動で速度をいじるモードもある
        - 機械学習で、映像のフレームの動きと、映像の意味的なとこを見ながら速度をいじる
            - 3つのレイヤーでこれを実現
            - Motion Layer
                - [[LucasKanade]]法で[[オプティカルフロー]]見て、その値使って計算
            - 意味的なとこのレイヤー
                - 今回のテストでは人力で設定した、でも映像の種類別に使える自動モデルはある
                - 例: 結婚式動画でsemanticなポイント抽出をするやつとか
                - この研究の本質はここではないから、人力で設定
            - [[パーソナライズ]]レイヤー
                - ユーザーの操作を元に学習調整する
        - パーソナライズする

- 先行研究で、様々な映像インタラクションが載ってる
- 映像要約したりするやつも
    - ノートまとめる方に使えるかも

- 思ったこと
    - すごい近いことを目指している？
    - 映像を要約するアプローチ参考になる
    - これを、リアルタイムでやる（[[後知恵]]なし）方法を考えたい
    - 同時に複数人が講義を受けていることを活用して、機械学習チックなことできるかも？
    - ユーザーフィードバックのこの意見参考になる
        - 「政治ニュースには興味がなかったから早送りしたけど、10秒飛ばしはしなかった。なぜなら、ざっくりとは一応知っておきたかったから」
        - 学校でも、知ってる内容を飛ばしつつ、一応全部分かってる内容なのかどうかは確認したい = 早送り、not10秒飛ばし
    - 事前にユーザーが映像について知識ある場合はもっと良い感じにできるかも
        - 例: 野球ゲームの流れを分かってる人が観戦する時は、シークバーに試合についての情報を増やして人力で映像を飛ばせるようにする

- [[時間操作]]インターフェースのノウハウが結構詰まってる?


- 次によむべき論文は？
    - この二つは、[[kineto]]みたいな特異な環境における映像分析だから参考になりそう
        - [[<論文ログ> Explicit Semantic Events Detection and Development of Realistic Applications for Broadcasting Baseball Videos]]
        - [[<論文ログ> Semantic Analysis for Automatic Event Recognitionand Segmentation of Wedding Ceremony Videos]]
    - 映像のSummarize系
        - [[<論文ログ> An Extended Framework for Adaptive Playback-Based Video Summarization]]

[https://www.researchgate.net/publication/221518075_Smartplayer_User-centric_video_fast-forwarding](https://www.researchgate.net/publication/221518075_Smartplayer_User-centric_video_fast-forwarding)
#kineto
