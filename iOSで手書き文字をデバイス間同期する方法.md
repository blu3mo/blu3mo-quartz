---
title: iOSで手書き文字をデバイス間同期する方法
---

* [Kineto](kineto.md)でやった方法

* 純正の*PencilKit*周りを使うだけだと、自由度低くてストロークを単独で取ることすらできない
  
  * （iOS14以降ならできるようになったんだっけ）
* より自由度の高い代わりのものとして、[SwiftyDraw](SwiftyDraw.md)という[OSS](OSS.md)がある
  
  * [https://github.com/Awalz/SwiftyDraw/tree/master/SwiftyDraw](https://github.com/Awalz/SwiftyDraw/tree/master/SwiftyDraw)
  * これならストロークをそれぞれ個別に扱うことができる
  * Kineto開発時にストロークをencode/decodeできるような機能を追加したので、今はストロークを文字列に変換することができる
    * PR: [https://github.com/Awalz/SwiftyDraw/pull/40](https://github.com/Awalz/SwiftyDraw/pull/40)
    * （CGPath, UIBezierPath等の仕様がややこしくて結構大変だった）
* ストロークを文字列に変換できれば、Firebase Realtime DB等で同期できる
  
  * drawItemsの中身を同期
  * 気づけない程度のラグ
