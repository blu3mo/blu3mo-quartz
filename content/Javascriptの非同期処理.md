---
title:
 'Javascriptの非同期処理'
---

- [[Javascript]]の[[非同期処理]]

- 結構記憶が抜けてる
- [[Promise]]とか[[async]]/[[await]]とか前ちゃんと理解したはずだけど忘れた

- Promise
    - 改めて読むと結構シンプルな仕組みだな
        - 一回以前理解したからかもだけど
    - ややこしいところ
        - 一回catchしたらrejectedからresolvedに変化する
            - エラー処理してもうOK、みたいな
            - なので、catchのあとにthenがあったらそれも処理される
    - [Promise - TypeScript Deep Dive 日本語版](https://typescript-jp.gitbook.io/deep-dive/future-javascript/promise)
    - > Promiseを使いたい理由は、非同期/コールバック的なスタイルのコードに対して、同期処理の書き方でエラーを取り扱うことができるからです。
        - なるほど
    - > エラーが起きた場合、後続のcatchにジャンプします(そして途中のthenはスキップします)
    - >  同期処理のエラーについても同様に、最も近い後続のcatchで捕捉されます
- Promise.then
    - return xすると、xをvalueにもったresolved promise objectが返される
- Promise.catch
- Promise.all/race
    - これ便利だな
    - Swiftでこれ実装しようとして苦労した覚えある
    - allがAND, raceがORか

- async
    - 別スレッドで非同期的に動く関数ですよという宣言
    - async funcはPromiseオブジェクトを返すので、async_func().then(~~)みたいな書き方ができる
        - async funcの返り値はPromise Valueとして帰ってくる
- await
    - .thenのチェーンが辛いので、同じ階層でフラットに書けるようにしたやつ
    - async func内でしか使えない
        - それ以外だとメインスレッドが止まっちゃって困るってことか
    - [[top-level await]]でも使える<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
        - 例
            - [[ESModule]]の中
                - 自分のページの`script.js`はESModuleで読み込まれるので、↓のように直に書いても動く
js

```javascript
const res = await fetch("なんか読み込む");
const text = await res.text();
// ...
```

            - [[開発コンソール]]
        - これが使えない環境([[Classic Script]]や[[Node.js]])では`(async () => { /* ... */ })()`で囲んで使う

資料
- [Promise, async/await](https://ja.javascript.info/async)
    - とてもわかりやすいのでおすすめ<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
- [イベントループ(event loop): microtask と macrotask](https://ja.javascript.info/event-loop)
    - Promiseが動く仕組みを知りたいときに読む
- [プロミスの使用 - JavaScript | MDN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Guide/Using_promises)
