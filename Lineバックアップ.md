---
title: Lineバックアップ
---

* Goal: LINEの履歴を永久に残したい

* 履歴が消えるタイミング:
  
  * PCの機種変
  * スマホのOSをまたぐ機種変
  * その他事故
* *LINE*の同期/*バックアップ*の仕様が本当に意味がわからない

* 調べる過程で有益だったサイトを貼っておく
  
  * （大体適当なサイトなのできつい）
* [https://did2memo.net/2013/02/06/naver-line-pc-talk-history-life/](https://did2memo.net/2013/02/06/naver-line-pc-talk-history-life/)
  
  * PC版LINEのトーク履歴保存期間について
* 20210205
  
  * mac同士でLineの履歴が移行できるかのテストをしてみた
  * iMacのほうがMBPより古い時期までログが残っているので、iMacの/DataでMBPの/Dataを置き換えた
    * `Library/Users/__/Library/Containers/jp.naver.line.mac/Data/Library/Containers/jp.naver.line/Data`
    * （なぜか二回同じようなフォルダ構成を通る）
  * 上手くいったっぽい、*imac*と同じところまでMBPで遡れる
  * なので、~~~~~/Dataをバックアップ取っていきつつ、[mac](mac.md)*乗り換え*時にちゃんとtransferしていけば、永久に引き継げそう
    * （Windowsに乗り換えなければ）
* 20211119
  
  * *M1Max MacBook Pro*に乗り換えるので、↑をやった
  * たぶん問題なく移行できたと思う
  * ちなみに、20181108以降のログをたどれる
    * イメージ: [カヤック職場体験](%E3%82%AB%E3%83%A4%E3%83%83%E3%82%AF%E8%81%B7%E5%A0%B4%E4%BD%93%E9%A8%93.md)や[TEDxGKA](TEDxGKA.md)準備の頃
    * それ以前は多分もうどこにも存在しないから無理、残念
