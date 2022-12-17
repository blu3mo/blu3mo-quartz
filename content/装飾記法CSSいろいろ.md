---
title:
 '装飾記法CSSいろいろ'
---

小さい文字 `[. 小さい文字]`
style.css

```
.deco-\. {
	font-size: 60% !important;
}
```


~~重要青~~ `[~ 重要青]` で出ます
style.css

```
 .deco-\~ {
   color: #fff;
   background-color: #1976d2;
   padding: 0.1em 0.2em 0.1em 0.2em;
 }
```


==蛍光ペン== `[+ 蛍光ペン]` で出ます
style.css

```
.deco-\+ {
  background: linear-gradient(transparent 60%, rgb(255 247 57 / 45%) 40%);
} 

```


薄く表示 `[( 薄く表示]` で出ます
style.css

```
.deco-\( {
  opacity: 0.5;
} 
```


インライン引用
- from [/scrasobox/拡張記法がきた！#59e5376896b9040000af691a](https://scrapbox.io/scrasobox/拡張記法がきた！#59e5376896b9040000af691a)
style.css

```
.deco-\" {
  	border-radius: .2em;
  	padding: 0 .4em;
  	background-color: rgba(128,128,128,0.1); 
  	font-size: 95%;
  	font-style: italic;
}
.line:not(.cursor-line) .deco-\"::before { 
  	color: #a0a0a0;
  	font-size: 85%; 
  	/* font-family: 'FontAwesome'; */
  	font-family: 'Font Awesome 5 Free';
  	font-weight: 900;
  	content: '\f10d';
    position: relative;
    top: -0.5em;
    left: -0.2em;
}
```

