---
title:
 'AVFoundation'
---

[https://developer.apple.com/videos/play/wwdc2016/503/](https://developer.apple.com/videos/play/wwdc2016/503/)
- [[Playback]]について
- [[Kinetoの映像通信]]

- [[バッファリング]]について
    - playbackLikelyToKeepUpが、このままいけばstallせずに終わりまでたどり着きそうかどうか
    - PlaybackBufferFullは全部ロードしたらtrue
    - playbackBufferEmptyは、stallしそう/してるときにtrue
- AVPlayer.rate = 1で再生?
    - これは旧verか

![image](https://gyazo.com/49e13e88965b0295b8652a8e516cf772/thumb/1000)

AVPlayer.rateはややこしいよと
![image](https://gyazo.com/9afc38776883fa952912dec0db9c5c7f/thumb/1000)

- 上記画像の新バージョンではなく、旧バージョン使いたかったら
    - automaticallyWaitsTominimizeStalling = false
    - setRate(time:atHostTime:)使いたかったらfalseにしないといけないらしい
    - 覚えておこう

- 連続で複数の映像を流したい場合は、[[AVQueuePlayer]]でうまくやる
    - 今はAVPlayerLooper?

- [[カラースペース]]の話もしてるけど、興味ないので飛ばす

- Playback Startup TimeのBest Practices
- ![image](https://gyazo.com/c8014ecf514de091e124175f19b96999/thumb/1000)
        - いろいろ設定して、play()してからplayerItemをセットした方が良いらしい
        - 順番逆だと、静的画像（1フレーム）を出したいだけだとAVPlayerが勘違いする的な感じらしい

- HLS


---