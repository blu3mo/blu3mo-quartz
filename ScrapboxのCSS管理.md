---
title: ScrapboxのCSS管理
---

* *Scrapboxのcss/scriptを別プロジェクトで管理*をやめて、このプロジェクトにcssを置く
  * [general_css](general_css.md): 全体に導入して損は無さそうな無難なcss
  * [personal_css](personal_css.md): 癖があるけど個人で使いたいcss
* 他プロジェクトで参照する時は[/blu3mo-public](https://scrapbox.io/blu3mo-public)の方のリンクを使う
  インポート.css

````
@import "https://scrapbox.io/api/code/blu3mo-public/general_css/style.css";
@import "https://scrapbox.io/api/code/blu3mo-public/personal_css/style.css";
````
