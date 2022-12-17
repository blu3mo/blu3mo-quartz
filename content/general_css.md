---
title:
 'general_css'
---

`[(Generalな|全体に導入する)(スタイル|CSS)]` [[(Generalなスタイル)​]] [[(GeneralなCSS)​]] [[(全体に導入するスタイル)​]] [[(全体に導入するCSS)​]]
- [[Scrapboxのcss／scriptを別プロジェクトで管理]]をやめて、このプロジェクトにcssを置く
    - [[general_css]]: 全体に導入して損は無さそうな無難なcss
    - [[personal_css]]: 癖があるけど個人で使いたいcss

 style.css

```
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
```


[[プレゼンテーションモードを良い感じにするCSS]]
[[Streamにアクセスするボタン]]
[[テーブル記法を見やすくするCSS]]
[[バレットを常に表示させるUserCSS]]
[[画像のサイズを調整するCSS]]
[[箇条書きを控えめにするCSS]]
[[装飾記法CSSいろいろ]]
[[ピン留めされたページを独立した段に表示するCSS]]
[[コードの行番号を表示するCSS]]
[[プランバッジを隠すCSS]]
[[のびのびドロップダウン]]
[[展開された正規表現リンクを小さくするCSS]]
[[kakeruの画像の背景に色をつけるCSS]]
