---
title: バレットを常に表示させるUserCSS
---

*番号付きリスト*の*バレット*を表示させる*UserCSS*

 > 
 > ![image](https://gyazo.com/6e769a44abdc0a20a839c153501dd82a/thumb/1000)
 > from [/scrapboxlab/番号付きリストのバレットを表示させるUserCSS](https://scrapbox.io/scrapboxlab/番号付きリストのバレットを表示させるUserCSS)

* これを少し改変して、formula-lineでも表示されるようにした

style.css

````
.line.number-list .dot {
    display: block !important;
}
.line.formula-line .dot {
    display: block !important;
}
````
