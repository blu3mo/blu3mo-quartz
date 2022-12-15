---
title: ScrapboxでKeichoを使う拡張
---

* <img src='https://scrapbox.io/api/pages/blu3mo-public/nishio/icon' alt='nishio.icon' height="19.5"/>の[Keicho](Keicho.md)をScrapboxで使える様にしたやつ
* [/takker/選択範囲をKeichoに尋ねるPopupMenu](https://scrapbox.io/takker/選択範囲をKeichoに尋ねるPopupMenu) by <img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

  * UserScriptと、askKeichoのtamperMonkeyを入れれば使える
  * （実装はっや、すご<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>）
  * 例によって開発ツールで通信にらめっこしてたらAPIを見つけたので、試しに作ってみたらできちゃった感じ<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

    * *勝手にAPI*叩いているけど大丈夫だっただろうか？
      * (と、ここに書いておけば<img src='https://scrapbox.io/api/pages/blu3mo-public/nishio/icon' alt='nishio.icon' height="19.5"/>さんから反応が返ってくるはず)
      * 他者のprojectを掲示板代わりに使うのはあまり良くないか
        * （全然<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>は大丈夫です）
        * (ありがとうございます<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>)
        * <img src='https://scrapbox.io/api/pages/blu3mo-public/nishio/icon' alt='nishio.icon' height="19.5"/>何この展開ウケる
      * <img src='https://scrapbox.io/api/pages/blu3mo-public/nishio/icon' alt='nishio.icon' height="19.5"/>まず大前提として僕はScrapboxでKeichoが使えるようになることをすごく面白く感じてます
        * 一方でまったく想定してない使い方だったので今後何をやってるのか読もうと思ってます
        * まあ、よっぽどおかしなことが起きても特定の会話が不整合な状態になるくらいで、他のユーザに影響はしないはずなので問題ないと思う
          * ざっと読んだんですけどWebクライアントがやってることと同じことをやってるだけなので問題なさそう
          * ブラウザ拡張はなんで必要なんですかね？なしでできるならそっちの方が便利そう。
            * scrapbox.ioからkeicho.herokuapp.comにアクセスしようとするとCSPに引っかかってブロックされてしまいます<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

              * 悪意のある外部serverに勝手にデータを送信されないようにするためのセキュリティ対策です
            * それを突破するために*tampermonkey*経由でkeicho.herokuapp.comにアクセスしています
            * cf. [/ci7lus/たのしいScrapboxUserScript#5f63841bae0f140000027cd6](https://scrapbox.io/ci7lus/たのしいScrapboxUserScript#5f63841bae0f140000027cd6)
            * <img src='https://scrapbox.io/api/pages/blu3mo-public/nishio/icon' alt='nishio.icon' height="19.5"/>
                - keicho.netlify.comからkeicho.herokuapp.comにアクセスできてるのでクロスオリジンのアクセス自体はできるんじゃないかな
                - see  [/nishio/Flask-CORS](https://scrapbox.io/nishio/Flask-CORS)
                - サーバ側は対処済みなのでクライアントサイドがcorsモードでfetchすればScrapbox上からでもアクセスできるはず
              
            * scrapbox.io側、つまりclient sideで制限がかかっているので不可能です<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

              * @Chrome
                * ![image](https://gyazo.com/2d1f6f9c63c6a1f552073faf7b0edc4e/thumb/1000)
              * ちなみにFirefoxだと何故かアクセスできました……
              * <img src='https://scrapbox.io/api/pages/blu3mo-public/nishio/icon' alt='nishio.icon' height="19.5"/>ああー、なるほど、Scrapbox側がホワイトリストで通信先を絞ってるのですね
        * 場合によっては専用のAPIを生やす

keicho.json

````json
{"talk": "PJAcJJ3AKxo407IhZDgm"}
````

使用テスト

* Scrapboxで生きるBotのあり方について考えたい

* <img src='https://scrapbox.io/api/pages/nishio/nisbot/icon' alt='/nishio/nisbot.icon' height="19.5"/>その「Scrapbox」は、どんな「Scrapbox」ですか？

* 書き込みによる同期的&非同期的対話が両方存在する場

* <img src='https://scrapbox.io/api/pages/nishio/nisbot/icon' alt='/nishio/nisbot.icon' height="19.5"/>その「対話」は、どんな「対話」ですか？

* 情報のやり取りによって、思考の積み木を積み上げていくみたいな

* <img src='https://scrapbox.io/api/pages/nishio/nisbot/icon' alt='/nishio/nisbot.icon' height="19.5"/>その「積み木」は、どんな「積み木」ですか？

* 思ったこと
  
  * *深さ優先探索*的な探索をKeichoがする以上、それが箇条書きのネストとして表現されたら嬉しい
    * 内部ではそういう情報持ってるのかな?
      * <img src='https://scrapbox.io/api/pages/blu3mo-public/nishio/icon' alt='nishio.icon' height="19.5"/>過去の文章を引用表示するためにキーワード→それが出現した時の入力、の対応づけを持ってるのでそれが使えるかも
  * Scrapbox内の適当な文章にKeichoをかけるの、意外と良いかもしれない
    * 暇つぶしにやってみると良さそう
    * そこから、気が向いたら会話をスタートさせるみたいな
    * こういう事を、[ScrapBot](ScrapBot.md)がやってくれると嬉しい
