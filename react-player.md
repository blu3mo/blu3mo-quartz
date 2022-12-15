---
title: react-player
---

* 一部操作、[ReactのRef](React%E3%81%AERef.md)を使うみたい

* getDuration()がYoutube Liveだとうまくいかないな
  
  * 何度呼んでも同じ値を返す
    * Liveだから増えていくはずなのに
  * seekすると値が更新される
    * 値が更新されるけど、特に視聴上問題がない処理を探したいな
  * これはiFrame APIの問題?
* onSeekもうまく行かない
  
  * [onSeek callback not working on youtube player · Issue #356 · cookpete/react-player · GitHub](https://github.com/cookpete/react-player/issues/356)
  * ええ、、、
