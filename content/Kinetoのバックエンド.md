---
title:
 'Kinetoのバックエンド'
---

#pKineto
- バックエンドは比較的知識が少ないので不安

- 通信
- [https://qiita.com/suin/items/00dee8bac706a6d66862](https://qiita.com/suin/items/00dee8bac706a6d66862)
    - フロントエンドとバックエンドのリアルタイム通信の選択肢を教えて下さい
- [https://cloud.google.com/solutions/mobile/mobile-app-backend-services?hl=ja#firebase-appengine-flexible](https://cloud.google.com/solutions/mobile/mobile-app-backend-services?hl=ja#firebase-appengine-flexible)
    - これの三つ目が良さげ

- 処理してFirebaseをいじくったりする元は、[[Kubernetes]]か[[Cloud Functions]]かな
- [https://medium.com/statuscode/cloud-functions-vs-container-engine-5c773e364ced#:~:text=With%20Kubernetes%20Engine%20you%20have,to%20the%20other%20compute%20services.](https://medium.com/statuscode/cloud-functions-vs-container-engine-5c773e364ced#:~:text=With%20Kubernetes%20Engine%20you%20have,to%20the%20other%20compute%20services.)
    - > Cloud Functions vs Kubernetes Engine

- 今のペン同期システムが頭悪いので、もっと良い形を見つけたい
    - [[Kinetoのホワイトボード]]もできるように
    - とりあえず、一番悪いのは定期更新
    - pullじゃなくてpushであるべき
- 改良版の仕様としては、
    - 監視範囲秒数内に変化があったらpush通知を受け取る
    - 表示範囲秒数より広めに監視して、定期更新テンポより時間方向の解像度をあげる

- あと、[[プロトコル]]を決めておかないとバージョンアップ時とかが大変になる

- [[Firebase Realtime Database]]の構造を以下に書く（ここのをマスターとする）

- <key>
    - devices:
        - <UDID>
            - <item UUID>: true
    - items:
        - <UUID>
            - type: <String> {"sticky", "stroke", "vote"...}
            - frames:
                - <frame UUID>: true
    - timeline:
        - <playingPoint (1k)>
            - <frame UUID>: true
    - frames
        - <UUID>
            - itemUUID: <item UUID>
            - deviceUDID: <UDID>
            - playingPoint: <time (0.1k, k:Int)>
            - createdDate: <date>
            - content (sticky):
                - text: <String>
                - xCoord:
                - yCoord:
            - content (stroke):
                - stroke: <base64 encoded stroke>
            - content (counter):
                - diff: <Int> (差分)

- Note
    - 各フレームは、あくまでも差分しか持たない
    - ある地点までの総和とかは、クライアントで自力でとる
        - （じゃないと、過去改変が起きた時に未来のデーターも変えないといけない）
    - ただまあふせんに関しては例外かな



- 疑似同期: 0.1秒単位
- 同期: 1秒単位
