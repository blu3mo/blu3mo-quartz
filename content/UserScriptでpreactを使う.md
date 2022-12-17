---
title:
 'UserScriptでpreactを使う'
---

- [/villagepump](https://scrapbox.io/villagepump), [/programming-notes](https://scrapbox.io/programming-notes), [/takker](https://scrapbox.io/takker)の先人の知恵/ソースコードがとても役に立った
    - [https://github.com/takker99/scrapbox-katex-previewer/blob/main/App.tsx](https://github.com/takker99/scrapbox-katex-previewer/blob/main/App.tsx)
        - これとかシンプルで理解しやすいな
        - もちっとシンプルなの作りたいな<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>


script.js

```javascript
import {html, render} from 'https://scrapbox.io/api/code/programming-notes/htm@3.0.4%2Fpreact/script.js';

(() => {
	const root = document.getElementById('app-container');
	render(html`<p>Hello</p>`, root);
})()
```


- 最低限のrenderはこんな感じかな
    - スタイル加えるとこうなる
        - ![image](https://gyazo.com/d1580bd01fafc61e07ff4149c5486f67/thumb/1000)
    - preact、後で自分でbundleしよう

- [[JSX]]記法のところは「html``」で括る必要がある感じか
    - JSX記法ではなく、[タグ付きテンプレート](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Template_literals#%E3%82%BF%E3%82%B0%E4%BB%98%E3%81%8D%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)を用いてJSXもどきを生のJSだけで書けるようにしたやつです<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
    - [https://github.com/developit/htm](https://github.com/developit/htm)
