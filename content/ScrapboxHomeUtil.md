---
title:
 'ScrapboxHomeUtil'
---

- [/akitok/CSSいじり 0212](https://scrapbox.io/akitok/CSSいじり 0212)のやつ
    - > 	scrapboxを生活のホームページにしたい
    - >  		タスクがページ遷移しなくても確認できるようにしたい
    - >  		日付とかどーんと出したい
    - >  	その日の予定が全部見れるようにしたい
- [[React]]([[preact]])をScrapbox Userscriptで試しに使って見たかったので、ちょうど良いタスク
    - 🙏🙏<img src='https://scrapbox.io/api/pages/blu3mo-public/axokxi/icon' alt='axokxi.icon' height="19.5"/>
        - [[pin-diary-3]]、日記に戻して使うのが合理的だなーとずっと思ってたけど週間ビューの方がタスク入れやすい ＆ 毎日１ページ増えるとちょっと一覧で荒れて見えそう なので我儘許してください🙏
            - いまは手動で今日の予定を一番上に持ってきて一覧ビューで見えるようにしてる

- とりあえず今の/akitokみたいな感じのを再現目指す

- トップページ表示検知は[[pin-diary-3]]を参考にできそう
    - pin-diary-4以降は仕組み違うので参考にできなさそう
    - タイマーで繰り返し処理しているのは、ページカードに変更があった時に対応するためか
        - 大変だな
    - 今回はしなくて良さそう？

- [[preact]]を使おう
    - [[UserScriptでpreactを使う]]
- 先にシンプルなdom追加やってからだな

- scrapbox.layoutによって表示非表示のロジック作ってたけど、要らなそう
    - `.app .container [2]`がトップ以外だとhiddenなので、そこに突っ込めばOK

- renderされるタイミングがいまいち掴めないな〜
    - 仕組みもわからん
    - divをrenderすると元々あったdivが消し飛ぶの意味わからないな
        - たぶん差分が誤認識されてるんだろうな

style.css

```
.util {
	background-color: gray;
	height: 50px;
	width: 100%;
}
.util .sub-title {
	color: white;
  	font-size: 10px;
}
.util .title {
	color: white;
	font-size: 20px;
}
```


テスト用[[task source]]

script.js

```javascript
import {html, render} from 'https://scrapbox.io/api/code/programming-notes/htm@3.0.4%2Fpreact/script.js';

const projectName = "blu3mo"
const taskSource = "task source" //後で動的に値返す関数にする 

const getSentencesInPage = async (projectName, pageName) => {
	const response = await fetch(`https://scrapbox.io/api/pages/${projectName}/${pageName}/text`)
    const text = await response.text();
    return text.split("\n");
}

const getTasksInPage = async (projectName, pageName) => {
	const sentences = getSentencesInPage(projectName, pageName);
	sentences.
}

getTasks(projectName, taskSource)
	.then(text => {
		console.log("test");
		console.log(text);
	})

let isListPage = true;
const Util = (props) => {
	return (html`
		<Fragment>
			<div className="util">
				<p className="sub-title">Tuesday 2022</p>
				<p className="title">Feb 26</p>
			</div>
		</Fragment>
	`)
}


handleLayoutChange()
scrapbox.on('layout:changed', handleLayoutChange)

function handleLayoutChange () {
    const app = document.querySelectorAll('.app .container')[2];
	isListPage = (scrapbox.Layout === "list");
	render(html`<${Util} isListPage=${isListPage}/>`, app);
	console.log(isListPage)
}
(() => {
    
})()
 
```

