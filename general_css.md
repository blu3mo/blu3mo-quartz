---
title: general_css
---

`[(Generalな|全体に導入する)(スタイル|CSS)]` *(Generalなスタイル)​* *(GeneralなCSS)​* *(全体に導入するスタイル)​* *(全体に導入するCSS)​*

* *Scrapboxのcss/scriptを別プロジェクトで管理*をやめて、このプロジェクトにcssを置く
  * [general_css](general_css.md): 全体に導入して損は無さそうな無難なcss
  * [personal_css](personal_css.md): 癖があるけど個人で使いたいcss

style.css

````
@import "../プレゼンテーションモードを良い感じにするCSS/style.css";
@import "../Streamにアクセスするボタン/style.css";
@import "../テーブル記法を見やすくするCSS/style.css";
@import "../バレットを常に表示させるUserCSS/style.css";
@import "../画像のサイズを調整するCSS/style.css";
@import "../箇条書きを控えめにするCSS/style.css";
@import "../装飾記法CSSいろいろ/style.css";
@import "../コードの行番号を表示するCSS/style.css";
@import "../プランバッジを隠すCSS/style.css";
@import "../のびのびドロップダウン/style.css";
@import "../展開された正規表現リンクを小さくするCSS/style.css";
@import "../kakeruの画像の背景に色をつけるCSS/style.css";
.page-list-item[data-page-title^="_"]
  {display: none !important;}
````

*プレゼンテーションモードを良い感じにするCSS*
*Streamにアクセスするボタン*
*テーブル記法を見やすくするCSS*
*バレットを常に表示させるUserCSS*
*画像のサイズを調整するCSS*
[箇条書きを控えめにするCSS](%E7%AE%87%E6%9D%A1%E6%9B%B8%E3%81%8D%E3%82%92%E6%8E%A7%E3%81%88%E3%82%81%E3%81%AB%E3%81%99%E3%82%8BCSS.md)
[装飾記法CSSいろいろ](%E8%A3%85%E9%A3%BE%E8%A8%98%E6%B3%95CSS%E3%81%84%E3%82%8D%E3%81%84%E3%82%8D.md)
*ピン留めされたページを独立した段に表示するCSS*
*コードの行番号を表示するCSS*
*プランバッジを隠すCSS*
*のびのびドロップダウン*
[展開された正規表現リンクを小さくするCSS](%E5%B1%95%E9%96%8B%E3%81%95%E3%82%8C%E3%81%9F%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%8F%BE%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E5%B0%8F%E3%81%95%E3%81%8F%E3%81%99%E3%82%8BCSS.md)
[kakeruの画像の背景に色をつけるCSS](kakeru%E3%81%AE%E7%94%BB%E5%83%8F%E3%81%AE%E8%83%8C%E6%99%AF%E3%81%AB%E8%89%B2%E3%82%92%E3%81%A4%E3%81%91%E3%82%8BCSS.md)
