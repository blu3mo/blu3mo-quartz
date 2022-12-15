---
title: ScrapBubble
---

<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>が作ってるやつ

* [/programming-notes/ScrapBubble@0.2.0](https://scrapbox.io/programming-notes/ScrapBubble@0.2.0)

* <img src='https://scrapbox.io/api/pages/daiiz/daiiz/icon' alt='/daiiz/daiiz.icon' height="19.5"/>さんの*ScrapScript*がベース

* ![image](https://gyazo.com/d81a7a2fa6fa793a3990031cf075d6a8/thumb/1000)

* リンクを吹き出し表示する + リンクホバーでページの内容を表示する、を組み合わせたもの
  
  * 表示されているページのリンクをホバーでさらに先のページまで見れる
  * しかも他プロジェクトのリンクにも飛べる
    * 0.2.0では飛べるプロジェクトをホワイトリスト方式で制限しました<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

---

* Reactの概要を理解したので、改めてコード読んだ上で最新版を導入しようかな
  * 理解した上で導入しておきたい
  * ちなみにReactとは型定義が若干異なります<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

    * ReactではなくPreactを使っている
    * 型定義以外はほぼ一緒です
* [GitHub - takker99/ScrapBubble: Show n-hop link destination pages beyond projects](https://github.com/takker99/ScrapBubble)
  * 思ったよりでかかったw
  * directoryで階層構造を作るのをやめたらこうなった<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
  * だいたい1ファイル1関数で書いているので、ファイルサイズはそんなに大きくないはずです
    * なるほど<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* そもそもScrapboxのhoverとかのイベントをどう拾ってるんだ?
  * `handlePointerEnter`で呼ばれるコードが見つからない
    * `usePromiseSettledAnytimes`が理解できないな
  * あ〜、わかったかも
    * `waitPointerEnter`はPromiseを返す
    * そのPromiseをresolveさせる関数は、`usePromiseSettledAnytimes`の`res`stateが持つ
    * その上で、その`res`stateは`handlePointerEnter`に代入される
    * だから、
      * `handlePointerEnter`を呼ぶ
      * -> waitPointerEnterというPromiseがresolveされる
      * -> await waitPointerEnterで止められてた処理が再開する
    * ってことか
    * そんでもって、waitPointerEnterでせきとめられるループがずっと回っていると
    * なぜ`event = await waitPointerEnter();`ができる?
      * handlePointerEnterの引数にeventを持たせておけば、Promise.resolve(event)ということになる
      * Promise.resolveの引数はconst x = await Promise()で代入できる
      * なるほど〜〜<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
  * 仕組みは理解<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * 不思議な実装だな
      * ループのせき止めを解除する形でEventに反応するのはなぜ?
      * Promiseを挟むのはなぜ?
    * 今回このような実装をするメリットはほとんど有りません<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

      * じゃあなんでこんな事したかと言うと、\[/miyamonz/async awaitで何かを待つような処理を同期的に書く\](https://scrapbox.io/miyamonz/async awaitで何かを待つような処理を同期的に書く)に感銘を受けて真似っこしたくなっただけ……
      * 一応一点だけ利点っぽいものがあります
        * ループが一度に一つしか実行されない
          * `event = await waitPointerEnter();`以降のループを処理している間にきた`pointerenter`は全て無視される
          * 普通に`addEventListener("pointerenter", async (e) => {/*...*/})`としてしまうと、以前のcallbackが実行し終わる前に次のcallbackが実行し始めるかもしれない
        * ただこのprogramでこんな保証を取る必要があるかというと疑問だったりする……
        * なるほど🙏<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
  * このあたりを参照<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

    * [/takker/async-awaitでeventを同期的に書いてみる](https://scrapbox.io/takker/async-awaitでeventを同期的に書いてみる)
    * [/takker/getPromiseSettledAnytimes](https://scrapbox.io/takker/getPromiseSettledAnytimes)

---

* *UserScript*でそこまでやるか..!というツール
  
  * *React*みたいなのをUserScriptで動かしているという理解でいいのかな
    * ですです<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
    * 軽量版Reactの*Preact*をUserScriptにぶちこんでいます
      * 無印のScrapBubbleの方は、この辺も自力で実装してて辛かった
  * Scrapboxの各要素（コードブロックとかGyazo表示とか動画表示とか）を全部自力で再実装している..?
    * 自力ですね<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
    * JSXっぽいやつで簡単にUIを構築できるのでそんなに難しいことじゃないです
      * CSSの調節がちょっと面倒かも
* コードベースが自由参加できる[/programming-notes](https://scrapbox.io/programming-notes)なのが怖いなーという気持ち
  
  * \[/takker/UserScriptをbundleするDeno script\](https://scrapbox.io/takker/UserScriptをbundleするDeno script)でまとめて自分のprojectにコピペすれば、それ以降悪意のあるコードが混入することはありません<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

    * それ以前に混入してたら……どうしようもない
    * なるほど!!<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

      * （至れり尽くせり、すごい）
* 今の所特にスマホ/iPadで使いたいとは感じていないので、TamperMonkeyでメインPCに導入した
  
  * どんなプロジェクトでも動くように改変した（自分のプロジェクト除外判定を省いた）
