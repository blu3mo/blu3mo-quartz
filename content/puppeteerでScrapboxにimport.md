---
title:
 'puppeteerでScrapboxにimport'
---

<img src='https://scrapbox.io/api/pages/blu3mo-public/public/icon' alt='public.icon' height="19.5"/>
- [[puppeteer]]で[[Scrapbox]]にimportするコード
- [[node.js]]
- [/ras/NodeでPrivateなscrapboxの情報を取得する](https://scrapbox.io/ras/NodeでPrivateなscrapboxの情報を取得する)のように、sidをセットして動かす
- とりあえず動くレベル
    - 雰囲気でjavascriptを書いてるので色々と雑
    - $と$xが混在したりしてるけど後で直す

- importが動いている間に別ブラウザで開いているページはoverwriteされないっぽい？
    - いや違うな
- 「Importing Pages...」になった時点で、ブラウザを閉じようが関係ないのかな?
    - これも違うな
- 元々なかったページのコピーは毎回成功するけど、上書き処理がうまくいかない場合がある
    - 条件がわからない、、

 .js

```javascript
const puppeteer = require('puppeteer');

const sid = "YOUR SID"
const project = "experiment-blu3mo";

(async () => {
    const url = new URL(`https://scrapbox.io/projects/${project}/settings/page-data`);
    const browser = await puppeteer.launch({
        args: ['--no-sandbox', '--disable-setuid-sandbox'],
        defaultViewport: {width: 800, height: 1024}
    });
    const page = await browser.newPage();

    await page.setCookie({name: 'connect.sid', value: sid, domain: 'scrapbox.io'});
    await page.goto(url.toString());
    await page.waitFor(1000);
    
    const inputUploadHandle = await page.$('input[name="import-file"]');
    inputUploadHandle.uploadFile("FILE.json");
    await page.waitFor(1000);

    const importSubmitButton = await page.$x("//button[contains(., 'Import Pages')]");
    await importSubmitButton[0].click();

    await browser.close();
})()
```


- これを試してみてる<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
    - この`FILE.json`ってどこからきたの？
    - 適当なプロジェクトからJSONでexportして、ファイル名を変更して同じディレクトリに置いて`$ node example.js` したらとりあえず動いたけど、これを[[puppeteerでScrapboxにimport]]ではどうやって引っ張ってきてるのかわからない
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>これは手動でexportする前提の物
        - エクスポートを自動でやりたければ、[[GASでScrapboxのexport APIを呼ぶ]]でできる
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>[[puppeteerでScrapboxにimport]]と[[GASでScrapboxのexport APIを呼ぶ]]を組み合わせると、
        - [[scrapbox-duplicator]]になる
