---
title: ScrapboxでApple Pencil使う用iPadアプリ
---

* Scrapboxを*GoodNotes*とかに代わりに出来ないかなーと

* *PencilKit*なり[SwiftyDraw](SwiftyDraw.md)なり使えば描画部分は楽そう

* 今のScrapbox標準draw機能の問題
  
  * シンプルに機能不足
  * 一度書いたものを動かしたり、サイズ変えたりできない
  * 色も少ない
  * なんかガタガタ
* これを、PencilKitに頼ることで充実させる
  
  * これ↓
  * ![image](https://gyazo.com/d7c7310b94c51db6b107f6fd69efe157/thumb/1000)
* 機能が充実すれば、GoodNotesの代わりにScrapboxでノート保存できそう
  
  * GoodNotesの不便さを解消できそう
    * やばいPencilの充電切れた、って時にgoodnotesにタイピングが辛い（タイピング機能が乏しいので）
    * これ書くよりタイプの方が良いなって場合でも、GoodNotesだと大体手書きでやる気がする
  * タイピングと手書きがスムーズに切り替えられるような実装がいいな
* PencilKitで書いてアップするだけなら今でもできる

* 問題は、再編集が難しいこと
  
  * *json*なり*base64*なりでページ上に記録しつつ、最新版を画像としてもみれる様にするって感じの仕様になるかな
  * 意外と実装できそう
  * scrapbox.io/files使うとか
    * *Scrapboxのファイルアップロード*
  * ファイルのAPIの仕様がよく分からないので、code blockにjsonを記録するとかの方が良さそう
* 蛍光ペンでハイライトしたところが*OCR*で読み込まれて、リンク/ハッシュタグとして記録されるとか欲しい

実装

* WKWebView
  * Scrapboxは*SPA*だからlaodイベントが呼ばれない
    * [https://qiita.com/yo1106/items/b2ef5d2a2182de6800b9](https://qiita.com/yo1106/items/b2ef5d2a2182de6800b9)
    * これで解決
* *Scrapboxのファイルアップロード*

\#実装しないアイデア

* なんかモチベが消えたので、一旦お蔵入り
* 気が向いたら取り組むかも
* Twitterで供養しとく
