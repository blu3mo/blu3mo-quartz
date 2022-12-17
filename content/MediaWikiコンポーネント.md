---
title:
 'MediaWikiコンポーネント'
---

from [[Wikichase実装ログ]]
- つくる

- リンク遷移がちゃんと成り立つようにすべきだな
    - formsみたいな感じでイベントハンドラをpropsで持てば良いのか
        - EventHandlerを継承すると良いことあるのかな
            - 継承というか、既存のを使う感じか
            - [any型で諦めない React.EventCallback - Qiita](https://qiita.com/Takepepe/items/f1ba99a7ca7e66290f24)
    - .replaceってやつでいけそう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - [https://kray.jp/blog/react-html-parser/](https://kray.jp/blog/react-html-parser/)

- いい感じにできたらnpmとかで公開したいなと思ってたけど、これMediaWikiに正確に対応するの辛いな
    - MediaWikiの仕様を理解しないといけない
        - Wikipediaさえそれっぽく表示できればいいので、そこまでのモチベはない

- [API:Parsing wikitext - MediaWiki](https://www.mediawiki.org/wiki/API:Parsing_wikitext)
    - 色々paramsあるな（[[Github Copilot]]の推薦で気づいた）

- useMediaWikiHTML()を作る
- WikipediaをMediaWikiに一般化
    - 継承とかではなく、関数コンポーネントを入れ子にする形でspecializeしろと
    - [コンポジション vs 継承 – React](https://ja.reactjs.org/docs/composition-vs-inheritance.html)

- MediawikiのCSSを使いたい
    - [https://yamory.io/blog/about-gpl-license/](https://yamory.io/blog/about-gpl-license/)
    - コードに組み込むなら派生物もGPLライセンスにしないとなのね
        - `https://ja.wikipedia.org/w/load.php?lang=ja&modules=ext.cite.styles%7Cext.uls.interlanguage%7Cext.visualEditor.desktopArticleTarget.noscript%7Cext.wikimediaBadges%7Cjquery.makeCollapsible.styles%7Cmediawiki.page.gallery.styles%7Cskins.vector.styles.legacy%7Cwikibase.client.init&only=styles&skin=vector`
        - から引っ張ってこれるな
            - 良いのかな
    - [mediawiki/resources/src at 130b9b05fcd7ee8830ebb55b01ed5c7a814042a5 · wikimedia/mediawiki · GitHub](https://github.com/wikimedia/mediawiki/tree/130b9b05fcd7ee8830ebb55b01ed5c7a814042a5/resources/src)
        - ここにcssあるな
        - [[MediaWikiコンポーネント#6213c0ce79e1130000943836]]のurlはこれらをbundleしてる感じかな?
            - modulesが
 _

```
ext.cite.styles
ext.uls.interlanguage
ext.visualEditor.desktopArticleTarget.noscript
ext.wikimediaBadges
jquery.makeCollapsible.styles
mediawiki.page.gallery.styles
skins.vector.styles.legacy
wikibase.client.init
```

                - 5,6行目は[https://github.com/wikimedia/mediawiki/tree/130b9b05fcd7ee8830ebb55b01ed5c7a814042a5/resources/src](https://github.com/wikimedia/mediawiki/tree/130b9b05fcd7ee8830ebb55b01ed5c7a814042a5/resources/src) を参照してるな
                - `wikibase.client.init`はこれか
                    - [Extension:Wikibase Client - MediaWiki](https://www.mediawiki.org/wiki/Extension:Wikibase_Client/ja)
                - というか`skins.vector.styles.legacy`だけで良いみたい?
                    - 他のmoduleのcssは何なんだろう、わからん
                        - 「あれ、これwikipediaと違う」となったら調べればいいか
                    - mediawikiページだと`skins.vector.icons,styles`だ
                        - `skins.vector.styles`だけでもいけるな
                        - ようわからんけどlegacyじゃ無いほうが良いだろう
                - で、結局ソースは?
                    - [[MediaWiki]]のSkinが何なのかを把握しよう
                        - あ〜〜、Vectorという名前のSkinがあるのね
                        - [https://www.mediawiki.org/wiki/Skin:Vector/en](https://www.mediawiki.org/wiki/Skin:Vector/en)
                            - > GNU General Public License 2.0 or later
    - Vector CSSの上に、Wikipediaのcommon.cssも重なってるのか
        - [https://en.wikipedia.org/wiki/MediaWiki:Common.css](https://en.wikipedia.org/wiki/MediaWiki:Common.css)
        - 言語によって細かい違いがあるな
            - 出典不足のラベルのサイズが違うとか
            - とりあえず面倒なので雑にjaのcssを読み込んでおく
                - webpackとか使ったちゃんとした読み込み方は後で考える
    - まあ細かいparamsとかは置いといて、Vector + Wikipedia Common.cssでWikipediaっぽくなる
        - wikipedia.orgのmoduleで`site.styles`を指定するとcommon.css他がもらえる
    - つまり`https://wikipedia.org/w/load.php?lang=ja&modules=skins.vector.styles|site.styles&only=styles`で欲しいcssは取得できる
    - ただ、問題はこれが権利的にどうなのか
    - CSS自体はGPL Licenseっぽい
        - [https://www.gnu.org/licenses/gpl-faq.en.html](https://www.gnu.org/licenses/gpl-faq.en.html)
        - > When we say “copy code,” we mean just that: you're taking a section of code from one source, with or without modification, and inserting it into your own program, thus forming a work based on the first section of code. “Use a library” means that you're not copying any source directly, but instead interacting with it through linking, importing, or other typical mechanisms that bind the sources together when you compile or run the code.
            - use a libraryはコピペとは別扱いなのね
        - あ〜、でも派生物も[[GPL]]で公開しないと?
    - というかWikipediaの内容自体にも権利あるか
        - [Wikipedia:ウィキペディアを二次利用する - Wikipedia](https://ja.wikipedia.org/wiki/Wikipedia:ウィキペディアを二次利用する)
        - [[CC BY-SA 3.0]]か
            - Credit表記すればセーフ
        - 画像は違う場合もあるよ、と
            - え〜〜、
            - あーでも基本二次利用可な画像か
                - [Wikipedia:画像利用の方針 - Wikipedia](https://ja.wikipedia.org/wiki/Wikipedia:画像利用の方針)
            - でも保証は無いよな、大丈夫なのだろうか
                - Wikipediaに権利的にまずい画像が載ると、巻き添えをくらう