---
title: UserCSSを動的に改変
---

* 動的って表現合ってるのかな

* なにかの条件に応じてsettingsが自動編集されて*UserCSS*が変わる仕組みを作れると面白そう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

* 例えば、
  
  * あるページのある行に特定の文字列が含まれていた場合に、その行にだけ黒塗りCssがあてらてる、みたいな
    * [/villagepump/特定ページの特定行だけにスタイルを付与する](https://scrapbox.io/villagepump/特定ページの特定行だけにスタイルを付与する)を使う
    * この挙動はUserCSS単独では実現できない
      * UserScriptを使えばできたけど、Scrapboxの仕様上自分にしか見えない
      * 本ページで提案している手法なら、全員に見える形でこの挙動を実現できる
