---
title:
 'React学習'
---

- 202202 再開
    - 確か以前はReactの公式チュートリアルを走ったあたりで止まったはず
    - [[React入門チュートリアル]]をやってみよう

[/mrsekut-p](https://scrapbox.io/mrsekut-p)を参照してみるのもおすすめです<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
- ReactとTypeScriptの学習メモが充実している
- <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>🙏

---
- さくっとwebで動くものを作れる様になりたいなと

- 一応小五の時に[[javascript]]をそれなりに触っていた
- ただまあ世界が完全に変わっているよう
    - [https://note.com/erukiti/n/n38495d44386a](https://note.com/erukiti/n/n38495d44386a)
    - >  「持ってる全てのHTML/CSS/JSの知識と経験、常識をゼロリセットしろ。もっと分かりやすくいうとウェブ技術を全て例外なく忘れろ。そして公式ドキュメントを全部読んで[[アンラーン]]しろ」
    - > 実際にその頃のJavaScript（つまりES5以前）を触ったことがある人は何かしらJavaScriptには不満があったでしょう。RubyやScalaやGoといった他の言語よりも、明確に劣る言語だと認識していたでしょう。それは何も間違っていません。
    - [https://note.com/erukiti/n/n38495d44386a](https://note.com/erukiti/n/n38495d44386a)
    - > ウェブフロントエンドは元々DOMを直接操作したり、おもちゃのようなスクリプトをやっていればそれで良いだけの世界でしたが、すでにそのような時代ではありません。石器時代とは異なり、仮想DOMなどといった抽象化が導入されました。

- [[React]]と[[TypeScript]]をとりあえず学ぶかな (20210325)
    - バックエンドは後で考える、[[Ruby On Rails]]を一応それなりに知っているはずだけど使うか迷う
- 本当にただただ[[React]]でアプリを作るなら、[[UserScript]]上で作ることを強くおすすめします<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
    - 1から全部作ろうとすると、本質とは関係ないところでつまずいてわけが解らなくなる
        - Reactを使ってアプリを作りたいだけだったのに、なぜか[[環境構築]]で時間を溶かされる
            - npm/yarnの使い方を学んで
            - package.jsonの書き方を学んで
            - webpackの設定方法を学んで
            - editorのeslintとpretterの設定をやって
            - ここまでやってようやく開発し始められる
            - 一つ一つのステップで絶対設定ミスをおこすので、そのたびに原因をしらみつぶしていく必要がある
    - UserScript上なら、コピペするだけでも動く
        - 例えば、
            - [/programming-notes/Preactを使ったScrapbox UserScriptのDemo (TODO app)#609648cc1280f000004c75b7](https://scrapbox.io/programming-notes/Preactを使ったScrapbox UserScriptのDemo (TODO app)#609648cc1280f000004c75b7)
            - [/pokutuna/プレゼンタイマー](https://scrapbox.io/pokutuna/プレゼンタイマー)
        - を適当なページにコピペしたあと、それを自分のページでimportすればすぐ使える
        - dynamic import構文で開発コンソールに書き込んでも実行できる
        - 中身を書き換えればすぐに自作appを作り始められる
            - Preactのlibraryを外部projectからimportしたくない場合は、それらを自分のページにコピペすればいい
                - file sizeが小さいので簡単にコピペできる
    - アプリの基礎を実装しなくていいのも利点
        - サイトのUIやテキストエディタが用意されている
        - あとはそれに乗っかって自分が欲しい機能を実装するだけ
    - 限界もある
        - Third Party libraryを使うのに工夫がいる
        - linterもformatterもない
            - F5で再読み込みを繰り返して、エラーがなくなるまでやる
            - あとは開発ツールのdebuggerでdebugしまくる
        - TypeScriptで書けない
            - 脳内で型推論するしかない
- 0からアプリを作ってもいいなら、[[CodeSandBox]]がおすすめ
    - 環境構築が不要
    - TypeScriptで書ける
    - Third Party packageを何でも使える
    - 編集するたびに勝手にアプリをbuildし直してくれる
    - GitHubと連携できる
    - Vercelにワンクリックでデプロイできる

- iOSエンジニアとしての最短ルートを通りたいなと
    - [iOSエンジニアがWebフロントエンドエンジニア(仮)になった話](https://zenn.dev/zones/articles/409339c1478e9328e5c8)

- これよさそう
    - [Reactチュートリアル1：犬画像ギャラリーを作ろう](https://zenn.dev/likr/articles/6be53ca64f29aa035f07)
    - [/takker/React入門チュートリアル](https://scrapbox.io/takker/React入門チュートリアル)も良さげだった<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
        - 🙏🙏<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - [[React入門チュートリアル]]
    - [最近Reactを始めた人向けのReact Hooks入門](https://sbfl.net/blog/2019/11/12/react-hooks-introduction/)もよい
        - 他のページも参考になる

- 適当なメモ
    - props と state があって、propsはJSX記法で<tag param=value>と書いたやつを指す
        - `<tag value1={xxx} value2={yyy}>...</tag>`の`<...>`の中に書いた属性のことです<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
            - `<...>`自体はただのHTMLタグ
    - stateに指定(setState)したものは、更新されるとrenderが呼ばれる
        - 実際に全部renderし直すのではなく、[[仮想DOM]]を作った上で比較して必要なところだけ更新するからReactは価値がある
        - ということかな

