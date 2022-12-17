---
title:
 'プレゼンテーションモードを良い感じにするCSS'
---

- cssで凸版ゴシックを使うようにした
    - [[フォント]]ない環境([[mac]]以外)だとダメだと思うけど、まあ多分自分の環境でしか動かさんからいいかな
    - 別にフォント違っても見れないわけじゃないし
    - ![image](https://gyazo.com/cdc9b24d32019d45b99a512a5c921213/thumb/1000)

style.css

```
 @import url("https://fonts.googleapis.com/css?family=Kosugi Maru");
 .app.presentation .line.section-title {
 	font-family: "Toppan Bunkyu Midashi Gothic";
 	font-size: 5vw;
 }
 .app.presentation .line.line-title {
  	font-family: "Toppan Bunkyu Midashi Gothic";
  	font-size: 6vw;
 }
 .app.presentation .line {
 	font-family: "Toppan Bunkyu Gothic";
 	font-weight: bold;
 	color: black;
 	line-height: 160%;
 	font-size: 2.3vw;
 }
```


style.css

```
.app.presentation .line .dot {
    width: .8vw;
    height: .8vw;
    top: calc(.8em - .25vw);
    right: 1vw;
}

.app.presentation .line .indent-mark .dot {
  background-color: #dfdfdf;
}

.app.presentation .deco-\# {
	top: 25vh;
    position: relative;
}
.app.presentation .deco-\* {
	font-family: "Toppan Bunkyu Midashi Gothic";
}

.app.presentation .deco-\~ {
	font-family: "Toppan Bunkyu Midashi Gothic";
}
.app.presentation .deco-\+ {
	font-family: "Toppan Bunkyu Midashi Gothic";
}
.app.presentation {
  --page-bg: #fff;
  --body-bg: #ffffff;
}
html[data-display-style*=presentation] body {
	background-color: #fff;
}
```


