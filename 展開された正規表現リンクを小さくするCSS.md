---
title: 展開された正規表現リンクを小さくするCSS
---

from [/villagepump/展開された正規表現を小さくするCSS](https://scrapbox.io/villagepump/展開された正規表現を小さくするCSS)
style.css

````
.line:not(.cursor-line) .deco-\, {
   font-size: 0px;
}
.line:not(.cursor-line) .deco-\,::before {
	font-size: 13px;
    content: '[ ]';
    background-color: #fbebdd;
    color: #f17c00;
}
 .dropdown-menu a[href*="%E2%80%8B"] {
 	font-size: 12px;
 	line-height: 22px;
 	color: gray;
 	
 	/*height: 10px;*/
 	/*display: none !important;*/
 }
````
