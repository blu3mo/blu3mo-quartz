---
title:
 'Scrapboxのファイルアップロード'
---

アップロードしたファイル
- [a.csv.zip](https://scrapbox.io/files/605b3d2c01dfb300239de7b6.zip)
- [b.csv.zip](https://scrapbox.io/files/605b3d4781a7b0001caddcfa.zip)
- [test.json](https://scrapbox.io/files/605c360494fed400239f226d.json)

記法
- `[ファイル名 URL]`と書くと、titleがついたURLに飛べるようになるっぽい
- ついでにゴミ箱アイコンが付く
    - クリックでファイル削除

URLの実験
`https://scrapbox.io/files/605b3d2c01dfb300239de7b6.zip?title=a.csv.zip`
- 結果: a.csv.zip

`https://scrapbox.io/files/605b3d2c01dfb300239de7b6.zip?title=b.csv.zip`
- 結果: b.csv.zip

`https://scrapbox.io/files/605b3d2c01dfb300239de7b6.zip`
- title=を付けずに
- 結果: a.csv.zip

`https://scrapbox.io/files/605b3d2c01dfb300239de7b6.ziptitle=x.csv.zip`
- 存在しないファイル名
- 結果: x.csv.zip

API
- ファイル削除とかのAPIはありそうだな
    - ただ見つからん
- アップロードもあると嬉しいな
