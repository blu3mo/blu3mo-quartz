---
title: html-react-parser
---

* [Wikichase](Wikichase.md)に使う

* ElementとDOMNodeがある?
  
  * ElementはDOMNodeの部分集合っぽいな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
  * Element, TextなどのDOMNodeの種類がある
  * tsでElement特有の処理したい時は、`if (node instanceof Element) { }`でElementに指定すれば良い
    * 例えばattribsはElementにしかない
