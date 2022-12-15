---
title: privateページ埋め込みUserscript
---

* 他人に見られるとまずい内容は、[/blu3mo-private](https://scrapbox.io/blu3mo-private)に書いてる

* これをメインの方と紐づけたいなーとずっと思っていた
  
  * タグまで紐付けなくていいから、せめて同じプロジェクト内で管理したい
* Userscriptで*iframe*埋め込みをして、privateを表示
  
  * ページ開くたびに動くと思ってたら、違った
  * \[/kembo/Scrapbox の UserScript でページ遷移をキャッチする方法\](https://scrapbox.io/kembo/Scrapbox の UserScript でページ遷移をキャッチする方法)
  * [/forum-jp/リンクを遷移した後のcallbackが欲しい](https://scrapbox.io/forum-jp/リンクを遷移した後のcallbackが欲しい)
  * これでページ遷移時に呼ばれるようにするかな
  * 追記
    * muta
* 例
  
  * *情報科学の達人 ワークショップ発表資料*
* めっちゃ雑実装だけど、[/bluemountain-theme](https://scrapbox.io/bluemountain-theme)に置いといた
  
  * (というかjavascriptの勝手がわからん)
  * まあ動くのでヨシ!
    * この概念めっちゃ知りたい<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
    * 
       > 
       > ScrapboxのUserScriptの管理がワークスペースの全部に反映しなきゃいけないからめんどくさいんだけど、Githubとかに.json置いて、自分のページに読み込ませるコード置いとくだけで良い感じになる？
    
    * 
       > 
       > ````
       > — 高木俊輔 Shunsuke Takagi (@tkgshn) [March 12, 2021](https://twitter.com/tkgshn/status/1370351058917105669?ref_src=twsrc%5Etfw)
       > ````
    
    * このimportしてるっぽいやつってどうなってるの？[blu3mo > 6044ab6079e1130000896f4c](blu3mo.md#6044ab6079e1130000896f4c)
    * [/takker/UserScriptで使えるscrapbox-parser](https://scrapbox.io/takker/UserScriptで使えるscrapbox-parser)的な感じ？
      * 解説記事等あげてくれるとありがたいです🥺<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
    * <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>そんな面倒なことはやっていない
      * ScrapboxのAPIで、`scrapbox.io/api/code/bluemountain-theme/XXX/script.js`から「XXX」ページのscript.jsを読み込める
      * それをimportしているだけ
* 普通にiframeで出すだけだと細すぎるので、.col-pageのmax-width制限をその時だけ取り払うようにした

2021-05-04 20:40:22 indentがずれてたので直しました<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

* あといくつかコードを単純化しました
* 🙏🙏<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* indentはtabにしますか？spaceにしますか？<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

  * <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>さんの好みに合わせたいと思います
  * spaceを一応いつもは使ってます<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * （わざわざありがとうございます🙇‍♂️🙇‍♂️）
    * ただのお節介なのでお気になさらず<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

      * 目の前の課題をやる気がしなくて別のことしてるとか口が裂けても言えない
        script.js

````javascript
let lastTitle = "";
function presentPrivateFrameIfInPrivatePage() {
    lastTitle = scrapbox.Page.title;
    const page = document.getElementsByClassName("page")[0]; 
    const colPage = document.getElementsByClassName("col-page")[0];
    const privateFrame = document.getElementById('privateFrame');
    privateFrame?.remove();
    const privateLink = document.getElementById('privateLink');
    privateLink?.remove();
    console.log(colPage);
    colPage.classList.remove("ignore-max-width"); 
    		
    //var pagename = document.location.pathname.split("/").pop();
````

↑`pagename`はページのタイトルで合っていますか？

* だとすると↓は`private-`で始まるページに対してのみ処理している？
* です、そういう仕様だったと思います
  * あ、今は使用していない感じですか？<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
  * 今は使ってないです<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * （今久しぶりに見て、やっぱり便利かもと思い始めてます）
* Scrapboxってコード中に文字挟んでも繋がるんですね<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
  script.js

````javascript
    if(!scrpabox.Page.title.startsWith("private-")) return;
    
    console.log("addFrame");
    page.insertAdjacentHTML('afterbegin',
  `<iframe id='privateFrame' style='width:100%; height:100vh;' src='https://scrapbox.io/blu3mo-private/${pagename.slice(8, pagename.length)}</iframe>`);
    page.insertAdjacentHTML('afterbegin',
  `<a id='privateLink' href='https://scrapbox.io/blu3mo-private/${scrapbox.Page.title.slice(8)}">Go to the page</a>`);
   colPage.classList.add("ignore-max-width");
}
````

script.js

````javascript
presentPrivateFrameIfInPrivatePage();

const observer = new MutationObserver((mutation)=>{
    if (lastTitle === location.href) return;
    presentPrivateFrameIfInPrivatePage();
});
observer.observe(document.getElementsByClassName("page-wrapper")[0], {attributes: true, attributeFilter: ["class"]});
````

style.css

````
 .ignore-max-width {
 	max-width: 100% !important;
 }
````
