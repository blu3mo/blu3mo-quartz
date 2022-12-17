---
title:
 'Kinetoの映像通信'
---

#pKineto

- [[Kinetoの360度カメラの必要性]]
    - ↑に書いた通り、各教室のハブデバイスから映像を流す
    - 他の環境と違う点
        - ライブ配信的な環境（リアルタイム）と、オンデマンド的な環境が入り混じる
        - どうスイッチするか
    - 生徒->ハブは必要?
        - というか生徒間双方向したいなら必要

    - [[HLS]]
        - ラグがきつい
        - アーカイブ映像が残しやすいっぽい
    - [[WebRTC]]
        - 会話できるレベルの超低遅延、その分映像の質は落ちる(adaptive)
        - 数百人以上の同時配信とかだときついらしいけど、授業環境じゃそれは流石にない?
            - いや、普通の授業ならそうだけど、むしろ数百人がつながってれば昔の時間にいても会話相手が常にいる、みたいなことになって良いかもとも思った
                - [[spatial.chat]]は[[コミュニケーション]]相手・[[議論]]相手が二次元の位置で決まる
                - [[kineto]]は、それが場所ではなく時間軸の位置で決まる、みたいな?w　おもろい

            - というかそれ以前に、学校環境でも全校集会レベルならありうるかも
                - そのレベルなら、配信相手と全受信相手がリアルタイムである必要はないか
        - 学校のローカルでやるなら、簡単にp2pできる?

    - WebRTC to HLS [https://medium.com/@voluntas/webrtc-to-hls-の可能性-fb1e847c9537](https://medium.com/@voluntas/webrtc-to-hls-の可能性-fb1e847c9537)

    - 時間操作時はWebRTC to HLS、リアルタイムが必要なときはWebRTC to WebRTC、みたいな器用な事をしないといけない感じかな
        - [[SkyWay]] Gatewayでサーバーまで映像送る、そこからHLSサーバーに送る感じかな
            - 金かかりそうで怖い
        - [[AWS]] [[Kinesis Video Streams]]もある
            - [https://qiita.com/yusuke84/items/73319b9a1dbc61b27c0f](https://qiita.com/yusuke84/items/73319b9a1dbc61b27c0f)
            - ここ(Skywayの人の記事)に書かれてる
            - WebRTCのiOS SDKがSwiftで良いな (Skywayは[[Objective-C]])

    - 発信、Zoomのストリーミングでも良いかも知れん
        - 嬉しい点:
            - 画面共有とかも使える
            - 慣れ親しんだ操作(?)
            - 発信側開発しなくていい
            - HLS, RTMPなどいろいろいけそう [https://devforum.zoom.us/t/how-do-i-get-an-output-from-zoom-as-an-rtmp-push-pull-hls-rtp-for-aws-elemental-media-connect/15586](https://devforum.zoom.us/t/how-do-i-get-an-output-from-zoom-as-an-rtmp-push-pull-hls-rtp-for-aws-elemental-media-connect/15586)
        - 難点
            - 配信先URLの設定とか不便?
            - 画質


- HLSにした
    - typeをeventにしないといけないっぽい、liveだと過去映像見れない
        - nginx.confで設定できる
    - [https://stackoverflow.com/questions/27518519/how-do-you-enable-video-seeking-in-safari-using-http-live-streaming](https://stackoverflow.com/questions/27518519/how-do-you-enable-video-seeking-in-safari-using-http-live-streaming)
        - ただm3u8をsafariで開くだけだとできない、これしないとevent対応しなかった


- [https://note.com/chitapapa/n/n49f5b7b635c4](https://note.com/chitapapa/n/n49f5b7b635c4)
    - いろいろまとめたページ
        - [[SFU Sora]]の人のページはいろいろ公開されてるから知識増えたら読みたい
                - WebRTC周りの資料が充実してる
                - [https://voluntas.github.io/](https://voluntas.github.io/)
                - リアルタイム動画配信コトハジメ [https://gist.github.com/voluntas/076fee77f30a0ca7a9b9](https://gist.github.com/voluntas/076fee77f30a0ca7a9b9)
                - WebRTC コトハジメ [https://gist.github.com/voluntas/67e5a26915751226fdcf](https://gist.github.com/voluntas/67e5a26915751226fdcf)
        - ImageFlux Live Streaming
        - 他にも、HLSの事とかいろいろ載ってる
            - 載ってるスライドあとでしっかり見るべき

- AVPlayerで映像うつしてる時に処理どうかける?
    - [https://stackoverflow.com/questions/44813242/track-faces-in-local-video-using-vision-framework](https://stackoverflow.com/questions/44813242/track-faces-in-local-video-using-vision-framework)
    - これでいけそう


- AVplayer動かない問題
    - 例
        - Akito, Mei

#kineto
