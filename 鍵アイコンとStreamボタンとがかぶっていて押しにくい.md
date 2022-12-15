---
title: 鍵アイコンとStreamボタンとがかぶっていて押しにくい
---

from [settings](settings.md)
鍵アイコンとStreamボタンとがかぶっていて押しにくいかも？<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

* ![image](https://gyazo.com/d5a35474c6ecbb6a42a5acbaa27d976c/thumb/1000)
* 鍵アイコンの置き場がなくて困ってます<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

  * Streamボタンの横に置くのもしっくりこない
  * タイトル横に置ければ嬉しいが、雰囲気で*css*を書いているのでそこまでする技術がない
    * `left`を、「`.quick-launch .project-home`の`left` + 80px」くらいにするとちょうど良さそうです
    * ![image](https://gyazo.com/2dba02a23e713100f10027715c1fa6f6/thumb/1000)
      * `top: 4px`より`top: 8px`の方がきれいに揃うかな？
    * こんな感じでどうでしょう？(未検証)
      * [/bluemountain-theme/settings#6006e03e79e11300007882d5](https://scrapbox.io/bluemountain-theme/settings#6006e03e79e11300007882d5)を改変しました
        home.css

````
/* プロジェクトTOPへのリンクと周辺パーツを強引にnavbarに移動 */
 /* ※次のnavbar固定と同時に使う必要がある */
 @media screen and (min-width: 768px) {
   .quick-launch .project-home {
     position: fixed; top: 4px; left: calc((100% - 1080px)/2); z-index: 990; }
   .quick-launch .project-home {
      line-height: 30px;
      min-height: 30px;
   }
   .project-home .title {
      font-size: 17px;
   }
   .quick-launch .private-badge {
     color: #ffffff75;
     position: fixed; top: 8px; right: 40px ; z-index: 991 }
   .app {
     padding-top: 45px;
   }
   /*.page { padding-top: 0 }*/ }
 @media screen and (min-width: 768px) and (max-width: 991px) {
    .quick-launch .project-home { left: 65px }
    .quick-launch .private-badge { left: 145px }
 }
 @media screen and (min-width: 992px) and (max-width: 1260px) {
   .quick-launch .project-home { left: 80px }
   .quick-launch .private-badge { left: 160px }
 }
 @media screen and (min-width: 1261px) {
    .quick-launch .project-home { left: calc((100% - 1260px)/2 + 80px) }
    .quick-launch .private-badge { left: calc((100% - 1260px)/2 + 160px) }
 }
````

````
    - ありがとうございます🙏<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - このcssを他projectでも使っているので、タイトルの長さの変化に対応したいなーと思ってました<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - 固定のleftの値だと変化に対応できないなーと思って悩んでます
        - タイトルの長さの変化にも対応できました<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
            - [/customize/titleをnav barに固定するUserCSS](https://scrapbox.io/customize/titleをnav barに固定するUserCSS)
        - ありがとうございます！！🙏🙏🙏<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - 結果🙌
            - ![image](https://gyazo.com/9adcd3fa342dd9d24c025f9359abb8e7/thumb/1000)
            - ![image](https://gyazo.com/990850a491ebff741fa20c045aaf7c9d/thumb/1000)

- Nav barとeditorの間に置き去りにするのはどうでしょう?<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
    - 流石に雑すぎるかな？
    - ![image](https://gyazo.com/794cb916d3544b585647d5dda72a8891/thumb/1000)
````

* というか別にprivateアイコンいらない気がしてきました<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
