---
title:
 '自分以外のユーザーによるScrapboxへの書き込みを通知'
---

- [[GAS]]にScrapbox Notificationを流して、GASからSlackに通知
- GASを経由して、author_nameがbluemountainのやつをフィルターする

- [[Scrapbox限定公開運用]]をやっていると、他人の書き込みが気づいたらあったみたいな事がある
    - それを見れるようにしたいなーと

- これSlackよりDiscordに流したいな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - webhookで同じ様に出来るな

- でけた
 gas.js

```javascript
const webhook_url = ""

function doPost(e) {
  const author_name = JSON.parse(e.postData.contents).attachments[0].author_name
  if (author_name !== "Bluemountain") {
    UrlFetchApp.fetch(webhook_url, {
      method: "POST",
      "Content-Type": "application/json",
      payload: e.postData.contents
    })
  }
  
}
```


- ![image](https://gyazo.com/83e46a1748a10c9f162a9d21fe87b266/thumb/1000)
    - こんな感じで自分以外のだけ通知される

- [/youkan-brain/Scrapboxに通知は設定しなくていいと思っている](https://scrapbox.io/youkan-brain/Scrapboxに通知は設定しなくていいと思っている)以前<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>にこのようなコメントをもらった、意見が聞きたいです<img src='https://scrapbox.io/api/pages/blu3mo-public/inoue2002/icon' alt='inoue2002.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/inoue2002/icon' alt='inoue2002.icon' height="19.5"/>
