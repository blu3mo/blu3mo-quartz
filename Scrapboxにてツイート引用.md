---
title: Scrapboxにてツイート引用
---

* 公式で実装されたので、[Tweetを取り込むPopup menu](Tweet%E3%82%92%E5%8F%96%E3%82%8A%E8%BE%BC%E3%82%80Popup%20menu.md)を外していた
* ただ、公式機能に結構不満がある<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* なので、[Tweetを取り込むPopup menu](Tweet%E3%82%92%E5%8F%96%E3%82%8A%E8%BE%BC%E3%82%80Popup%20menu.md)をいじって解決したいなと思った
* いまある不満
  * IDと名前も引用パートに入れて欲しい
    * [Tweetを取り込むPopup menu > 609139451280f0000069b83d](Tweet%E3%82%92%E5%8F%96%E3%82%8A%E8%BE%BC%E3%82%80Popup%20menu.md#609139451280f0000069b83d)をいじれば可能
  * idをリンク/アイコンにして欲しい
    * [Tweetを取り込むPopup menu > 609139451280f0000069b83d](Tweet%E3%82%92%E5%8F%96%E3%82%8A%E8%BE%BC%E3%82%80Popup%20menu.md#609139451280f0000069b83d)をいじれば可能
  * 画像展開して欲しい
    * 無理
  * 引用RT元展開して欲しい
    * 無理
  * リプライツリー展開して欲しい
    * 無理
* [Tweetを取り込むPopup menu](Tweet%E3%82%92%E5%8F%96%E3%82%8A%E8%BE%BC%E3%82%80Popup%20menu.md)で使っているTwitter oEmbed APIだと、画像やRT、replyを取得する事ができない<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

  * あー、なるほど、、<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* これらを取得する方法は以下の通り
  * Twitter APIを使う
    * 登録とかしないといけなくて面倒
  * headless browserでtweet情報をscrapingするserverを立てて使う
    * [/ci7lus/tweet2image-upload](https://scrapbox.io/ci7lus/tweet2image-upload)が使っている方法
  * Twitterのfrontend APIを使う
    * cf. [TwitterのフロントエンドAPIの全てをリバースエンジニアリングした(Python3)｜神瀬来未｜note](https://note.com/kohnoselami/n/nb8ef0eea5831)
    * 「*リバースエンジニアリング*」というフレーズが出ていることから予想がつくように、かなりグレーな方法
      * [robots.txt](https://twitter.com/robots.txt)で許可はされているから気にしなくてもいいかも
      * [https://api.twitter.com/robots.txt](https://api.twitter.com/robots.txt) は禁止されてる。やっぱだめかも
    * 一番簡単な方法がこれ
