---
title:
 '曜日ページに飛ぶBookmarklet'
---

[[pin-diary-3]]で生成しているページに直接飛べる[[Bookmarklet]]を作る
 .js

```javascript
const currentDate = new Date();
const nextSunday = new Date();
function zero(n) {
    return String(n).padStart(2, '0');
}
nextSunday.setDate(currentDate.getDate() + (7-currentDate.getDay())%7);
window.location.href=`https://scrapbox.io/blu3mo/~${nextSunday.getFullYear()}${zero(nextSunday.getMonth() + 1)}${zero(nextSunday.getDate())}`;
```


 bookmarklet

```
javascript:const currentDate = new Date();const nextSunday = new Date();function zero(n) {return String(n).padStart(2, '0');}nextSunday.setDate(currentDate.getDate() + (7-currentDate.getDay())%7);window.location.href=`https://scrapbox.io/blu3mo/~${nextSunday.getFullYear()}${zero(nextSunday.getMonth() + 1)}${zero(nextSunday.getDate())}`;
```

