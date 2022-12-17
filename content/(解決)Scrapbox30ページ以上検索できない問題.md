---
title:
 '(解決)Scrapbox30ページ以上検索できない問題'
---

- [[Scrapbox]]は検索結果に30ページ以上出ないらしい
- [/forum-jp/scrapbox内の検索機能では30ページ分しか表示できない件について](https://scrapbox.io/forum-jp/scrapbox内の検索機能では30ページ分しか表示できない件について)
    - 今後変更予定らしい
    - 100ページまで検索できるようになりました
- ちょっと困る
    - [[情報科学の達人]]のページ探すときとか

- [[API]]の方だとlimitの値自由に変更できる
    - `GET https://scrapbox.io/api/pages/blu3mo/search/query?skip=0&sort=updated&limit=1000&q=情報科学の達人`
    - その結果を見れるようにするシンプルなページ/userscriptを作る
    - （後で）
    - 100 pages固定になっています
        - cf. [/scrapboxlab/api/pages/:projectname/search/query](https://scrapbox.io/scrapboxlab/api/pages/:projectname/search/query)

#実装するかも
- というかTodo
