---
title:
 'コードの行番号を表示するCSS'
---

[/scrasobox/コードの行番号を表示する](https://scrapbox.io/scrasobox/コードの行番号を表示する)
style.css

```
/* コード記法の行番号を表示 -- ウィンドウ幅768px以上で適用 */
@media screen and (min-width: 768px) {
  .section-title, .code-block-start { counter-reset: codeline }
  .code-block code > span:not([class]) { counter-increment: codeline }
  .code-block code > span:not([class])::before { 
    content: counter(codeline); 
    position: absolute; display: inline-block; left: -4em; z-index: 10; 
    min-width: 50px; text-align: right; vertical-align: bottom;
    
    /* ↓行番号のフォントとか色とかの指定はここ */
    font-family: Menlo,Monaco,Consolas,"Courier New",monospace; color: grey }
  
  /* カーソル行の行番号を濃く表示する */
  .code-block code > span:not([class])::before { opacity: .5 }
  .cursor-line .code-block code > span:not([class])::before { opacity: 1; font-weight: bolder } }
```
