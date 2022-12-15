---
title: (解決)Scrapbox30ページ以上検索できない問題
---

* [Scrapbox](Scrapbox.md)は検索結果に30ページ以上出ないらしい

* [/forum-jp/scrapbox内の検索機能では30ページ分しか表示できない件について](https://scrapbox.io/forum-jp/scrapbox内の検索機能では30ページ分しか表示できない件について)
  
  * 今後変更予定らしい
  * 100ページまで検索できるようになりました
* ちょっと困る
  
  * [情報科学の達人](%E6%83%85%E5%A0%B1%E7%A7%91%E5%AD%A6%E3%81%AE%E9%81%94%E4%BA%BA.md)のページ探すときとか
* *API*の方だとlimitの値自由に変更できる
  
  * `GET https://scrapbox.io/api/pages/blu3mo/search/query?skip=0&sort=updated&limit=1000&q=情報科学の達人`
  * その結果を見れるようにするシンプルなページ/userscriptを作る
  * （後で）
  * 100 pages固定になっています
    * cf. [/scrapboxlab/api/pages/:projectname/search/query](https://scrapbox.io/scrapboxlab/api/pages/:projectname/search/query)

\#実装するかも

* というかTodo
