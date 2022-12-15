---
title: ピン留めされたページを独立した段に表示するCSS
---

ピン留めされたページを独立した段に表示する

* cf. [/aioilight/settings](https://scrapbox.io/aioilight/settings)
  style.css

````
.page-list-item.pin + .page-list-item:not(.pin) {
  	clear: both;
}
````

* 20220409
  * 公式実装されたので不要に
