---
title: Wikichase実装ログ
---

* このページは実装ログのみ
  * *上に追記していく形式のページ*

[https://wikichase.vercel.app/teeth-those/runner](https://wikichase.vercel.app/teeth-those/runner)

* なぜ止まってるのか確認

* ゴール判定と時間制限判定をしたい
  
  * スタート時に、ゴールと終了時間を記録すれば良いかな
* 最初のページの生成、プレイページのuseEffect(, )の時だと複数回走る可能性があるので、ルーム作成時に変えた

* mediawikiとwikipedia、レイヤー分けて扱ってたけど結局密結合で分離きつそうなので諦めるか
  
  * いや、htmlの取得とフィルタはuseMediaWikiとMediaWikiPageでやる感じでちょうど良いな
* css
  
  * モバイルのurl
    * `https://ja.wikipedia.org/w/load.php?lang=ja&modules=ext.cite.styles%7Cext.relatedArticles.styles%7Cext.wikimediaBadges%7Cmediawiki.hlist%7Cmediawiki.page.gallery.styles%7Cmediawiki.ui.button%2Cicon%7Cmobile.init.styles%7Cskins.minerva.base.styles%7Cskins.minerva.content.styles.images%7Cskins.minerva.icons.wikimedia%7Cskins.minerva.mainMenu.icons%2Cstyles&only=styles&skin=minerva`
    * `https://ja.m.wikipedia.org/w/load.php?lang=ja&modules=startup&only=scripts&raw=1&skin=minerva&target=mobile`
  * pcのurl
* *自動マッチメイキング*をしたい
  
  * とりあえず最低限の実装で良いが、*ベストプラクティス*とかあるのかな
  * [https://www.strixengine.com/strix-matchmaker/](https://www.strixengine.com/strix-matchmaker/)
  * [https://doc.photonengine.com/ja-jp/server/current/applications/loadbalancing/matchmaking-and-lobby](https://doc.photonengine.com/ja-jp/server/current/applications/loadbalancing/matchmaking-and-lobby)
  * [マッチメイキングシステムの形態について考えてみる - Qiita](https://qiita.com/oreo367/items/dbc76084f966c5c9097b)
    * 有益
    * とりあえずルームベースで作るかな
  * まあとりあえずfirebaseに突っ込むか、より良い実装とかは後で良い
  * ルームid、衝突回避できるまでランダム生成する雑実装でとりあえずいいや
    * 万が一人増えたら直せば良い
* firebase realtime dbのhooks、使おうかと思ったが、hooks内の関数で使う方法が掴めなかったので後で

* ランディングページを作った
  
  * ![image](https://gyazo.com/0348f0e7848e571f8356a2492f0e97a3/thumb/1000)
  * こういうデザイン良いな〜と思っていたのでやってみたが、むずい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * それはそう、シンプルなものほどデザインの技術必要そう
  * 絶対説明は足りんが、詳細は触ってみればわかるようにしたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * とりあえず何を目指すのかだけは伝えた✅
* *弾性同期Youtubeプレイヤー > 6211f07579e1130000619a52*の知見をほとんど忘れて、同じことを再度調べていた
  
  * *useInterval*、便利
* 逃げ側の縛り
  
  * 目次より上?
    * ダメなケースもあるな
      * [https://ja.wikipedia.org/wiki/単位時間#:~:text=科学における単位時間と,10m%2F秒）である%E3%80%82](https://ja.wikipedia.org/wiki/単位時間#:~:text=科学における単位時間と,10m%2F秒）である%E3%80%82)
      * これとか
  * 最初のn行とかが無難かな
    * でも納得感は目次区切りより低いかも
  * とりあえず後回しで
* データベース
  
  * :gameId
    * chaser
      
      * userId: string
        * とりあえずはセッション毎ランダム生成で
          * デバイス固有の値を後で入れれば、一度落ちても復帰可能になる
        * 空欄ならoffline
      * pages:
    * evader
      
      * userId: string
      * lastJump: date
        * クールタイム判定は逃げ側がやる
      * isAlive: bool
        * クールタイムオーバーもしくは捕まったらこれがfalseになる
* やりのこし
  
  * ![image](https://gyazo.com/72ad082eae5cf6f5721db3c57ee88a7b/thumb/1000)
    * こいつら消す
  * 遷移時のロード
  * ずるいやつ
    * 「英語」とか「国際発音記号」とかのリンク
* 改めて実装する事整理
  
  * 同じゲームに二人入れる
    * これはとりあえず同URL同roomでよさそう
  * 二人はお互いの遷移を確認できる
* WikipediaのCSSを引っ張ってきたい
  
  * 権利的にOKなやつはどこだろう
* xss的なやつの対策として、wikipedia以外のページに飛べないようにすべきだな
  
  * wikipedia自体は編集できるので、wikipediaから飛ぶ外部リンクも開けて表示される実装だとまずい
* [GitHub - remarkablemark/html-react-parser: HTML to React parser.](https://github.com/remarkablemark/html-react-parser)

* Wikipedia API叩いたら*CORS*エラーに引っかかった
  
  * [javascript - Wikipedia API + Cross-origin requests - Stack Overflow](https://stackoverflow.com/questions/23952045/wikipedia-api-cross-origin-requests)
  * なんだそれ、ようわからん使用だな
* htmlを返してくれるapiがある?
  
  * [javascript - Is there a way to embed and style a Wikipedia article in a website? - Stack Overflow](https://stackoverflow.com/questions/26577292/is-there-a-way-to-embed-and-style-a-wikipedia-article-in-a-website)
  * [API:Get the contents of a page - MediaWiki](https://www.mediawiki.org/wiki/API:Get_the_contents_of_a_page)
  * 一週間前に別件で見た時は誰がこんなapi使うのかと思ったけど、今とても欲しい
  * これよさそう
  * ![image](https://gyazo.com/725c7afa687e293470b17c41569dd597/thumb/1000)
    * パクったcssとAPIから取ったhtmlでWikipedia表示できた
  * *MediaWikiコンポーネント*を作ろう
* まって、リンククリックイベント取るのむずくないか
  
  * ああ、locationの変化だけ拾えばいいのかt
  * [javascript - iFrame src change event detection? - Stack Overflow](https://stackoverflow.com/questions/2429045/iframe-src-change-event-detection)
    * いや〜〜、厳しいな
    * というか取れない理由がわからん
    * geoguessrとかどうやってるんだ?
      * apiあるのか
* [javascript - iframe wikipedia article without the wrapper - Stack Overflow](https://stackoverflow.com/questions/61902/iframe-wikipedia-article-without-the-wrapper)

* とりあえずMVPを作ろう
  
  * 必要な物
    * お互いのページが見れる
    * 鬼側の制約
      * リンク遷移の制限（once per 15sec)
      * 概要の文だけ
    * 捕まえた判定
    * お互いのリンク飛びログ
