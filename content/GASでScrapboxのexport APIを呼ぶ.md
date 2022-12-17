---
title:
 'GASでScrapboxのexport APIを呼ぶ'
---

参考
- [/nishio/ScrapboxのprivateプロジェクトのAPIを叩く](https://scrapbox.io/nishio/ScrapboxのprivateプロジェクトのAPIを叩く)
- > もしうっかりこの情報(SID)を漏らしてしまった場合にリセットする方法があるかどうかは知らないので気をつける必要がある。
- 多分漏らすとどうにも出来なさそうなので、サブGoogleアカウントのログインセッションのsidを使う方が良さそう
    - 万が一の時は切り捨てればとりあえず何とかなる
- [/ras/非公式なscrapboxのAPIを叩く](https://scrapbox.io/ras/非公式なscrapboxのAPIを叩く)


 script.js

```javascript
function myFunction() {
  const sid = "YOUR_SID";
  const cookie = "connect.sid=" + sid;
  const userInfoJSON = UrlFetchApp.fetch("https://scrapbox.io/api/users/me", {
    method: "get",
    headers: {
       "Cookie" : cookie
    }
  });
  const userInfoData = JSON.parse(userInfoJSON);
  const csrfToken = userInfoData.csrfToken
  const response = UrlFetchApp.fetch("https://scrapbox.io/api/page-data/export/blu3mo.json", {
    method: 'post',
    headers: {
       "Cookie" : cookie,
       "X-CSRF-TOKEN": csrfToken,
    },
    muteHttpExceptions : true,
  });
  Logger.log(JSON.parse(response))
}
```


- ↑のコードのexportのところが動かなくてずっと悩んでたんだけど、どうやらGETメゾットに変更になったらしい<img src='https://scrapbox.io/api/pages/blu3mo-public/inoue2002/icon' alt='inoue2002.icon' height="19.5"/>
    - [/scrapboxlab/api/page-data/export/:projectname.json#61d3a3381280f00000f07eda](https://scrapbox.io/scrapboxlab/api/page-data/export/:projectname.json#61d3a3381280f00000f07eda)
    - そうだったのか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - scrapbox-stdに依存していたので気づかなかった

