---
title: AVPlayerがnginx-rmtpの配信映像をある地点以上読み込まなかった話
---

* nginx-rmtpの配信を受け取るAVPlayerが映像をある地点以上読み込まなかった話

* よく調べたら、nginx.confのhls_playlist_lengthにplayerItem.currentTimeがたどり着くと、止まる

* hls_playlist_lengthのちょっと手前からAVPlayerが再生始めるから、一定時間経つと毎回止まることになっていた

* つまり、AVPlayerが配信を無限に続くものだと思ってない

* とりあえずhls_playlist_lengthを馬鹿でかい数字にして解決したけど、もっとちゃんとした方法を見つけたい

\#nginx-rmtp #nginx #hls
