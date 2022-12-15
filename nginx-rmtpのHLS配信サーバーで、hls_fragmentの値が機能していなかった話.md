---
title: nginx-rmtpのHLS配信サーバーで、hls_fragmentの値が機能していなかった話
---

* [https://github.com/arut/nginx-rtmp-module](https://github.com/arut/nginx-rtmp-module)

* *nginx-rmtp* moduleを使ってRMTP -> HLSの配信サーバーを作っていた時発生した問題と、その原因

* 問題
  
  * nginx.confでhls_fragmentを1sに設定して、各fragmentを一秒単位にしたかった
  * ただ、 .m3u8ファイルを確認するとそれぞれのdurationが4秒程度になってしまっていた
  * hls_fragmentの値を変えてもdurationに変化がない
* 原因
  
  * OBSで配信をするときに、*GOP*の最小単位が自動的に決められていた
  * それが1秒を超えている場合は、hls_fragmentの値よりそっちが優先される
  * GOPをマニュアルで設定することで解決
    \#nginx #hls
