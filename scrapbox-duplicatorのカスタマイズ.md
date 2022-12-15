---
title: scrapbox-duplicatorのカスタマイズ
---

* [scrapbox-duplicator](scrapbox-duplicator.md)をデプロイした後、*Heroku*で設定する事

* *Heroku Scheduler*
  
  * ![image](https://gyazo.com/1897143fcca011988e59b068d7f28249/thumb/1000)
* ↑の設定で、日本時間の朝9時~夜9時まで、3時間に一回syncされる

* Config Vars
  
  * `DESTINATION_PROJECT_NAME`: `blu3mo-public`
  * `SOURCE_PROJECT_NAME`: `blu3mo`
  * `SID`: もってくる
  * `SHOULD_DUPLICATE_BY_DEFAULT`: `True`
    * これは*Scrapboxを一部以外全てミラーする運用*をするために必要

*scrapbox-duplicatorの設定をコードブロックから読み込む案*
