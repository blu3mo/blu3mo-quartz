---
title: WWDC2018： Measuring and Optimizing HLS Performance
---

[https://developer.apple.com/videos/play/wwdc2018/502/](https://developer.apple.com/videos/play/wwdc2018/502/) #WWDC2018

* 配信のクオリティの上げ方と、その評価方法について

* 5つの[KPI](KPI.md) = 評価基準
  
  * 再生できるまでにかかる時間 (startup time)
    
    * 改善方法
    * 連続で映像再生するなら、2つ目に行く前からロードしちゃうと良い的な
    * AVQueuePlayer使う
    * あと、buffering time減らしたいならbitrateとかをうまく調整してがんばってーてきな話だった
      * initial video qualityとのトレードオフ
    * ここはあんまり参考にならない
  * 再生中に止まってしまう頻度
    
    * AVPlayerItemPlaybackStalledで測れる
    * 改善するには、これはたくさんhlsサーバー側でbitrateを用意しろと
    * ErrorLogとAccessLogが問題を示してくれる
      * ex: indicateBitrateがobservedBIrtateより大きいなら、帯域の限界を超えたデーターを送ってしまってる
  * 再生中に止まる長さ
    
    * stall time per hour watched
    * playerItem.accessLog()でduration watched測れる
  * 映像の解像度
    
    * bitrateの平均値を見る
  * Steraming Error
    
    * 再生ボタンに斜め線入るやつ
    * これはErrorLogでがんばってーという
* m3u8の書き方
  
  * 「教えられることは全部教えろ」by Apple
  * codes, bandwidth, resolutionとか全部かけること書けよと
  * そうすればあとはAVPlayerが頑張るよって話かな?
* シークバーにサムネイル出したいなら、I-frame playlistを与える必要がある

* あとmultichannel audio(副音声的な)の話もしてたけど興味ないので飛ばした

* このトークは、生配信とかよりは既に存在する映像の再生がメインな感じがした

* ただstall timeの最適化は参考になる
