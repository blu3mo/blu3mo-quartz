---
title: kakeruの画像の背景に色をつけるCSS
---

* [kakeru](kakeru.md)の画像は透過背景
  * ダークモードだと、文字が見えなくなってしまう
* *東大1S1数理科学基礎:線形代数 > 626a212579e11300001acddd*みたいなところで、画像背景に色をつけたい

style.css

````
img[src^="https://i.kakeru.app"] {
	background-color: lightgray;
}
````
