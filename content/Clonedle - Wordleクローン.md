---
title:
 'Clonedle - Wordleクローン'
---

from [[React入門チュートリアル]]
[[Wordle]]クローン作る

- やりたい事
    - Firebaseとの連携
    - canvasとやら
    - アニメーションっぽいこと

- [[Hooks]]を切り出す
    - Reactらしくかきたいので
    - Clonedleの場合、何がHooksになるべき?
        - useGame?

- ✅ファイル分割

- [[TypescriptでReact]]に書き換えよう
    - DONE✅

- [[Github Pages]]にデプロイしよう
    - 無料で出来るの素晴らしいな
    - [React GitHub Pagesにデプロイ - create-react-appで作ったReactプロジェクトをGitHub Pagesにデプロイしてみましょう。](https://dev-yakuza.posstree.com/react/github-pages/)
    - [https://web-begginer-log.com/create-react-app-gh-pages/](https://web-begginer-log.com/create-react-app-gh-pages/)
        - これで行けた、yarnはnpmに変えたけど
        - package.jsonは[https://github.com/blu3mo/clonedle/blob/master/package.json](https://github.com/blu3mo/clonedle/blob/master/package.json)
    - ✅[https://blu3mo.github.io/clonedle/](https://blu3mo.github.io/clonedle/)

- 最初のログ
    - > Parsing error: JSX value should be either an expression or a quoted JSX text. (19:18)
        - <x y="_">もしくは<x y={_}>なら良いのね
        - <x y=0>が許されないのがいまいちよく分からんけど、まあそういう物なのかな
            - HTML文法として間違っているからとか？<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
            - あ〜〜、なるほど！<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                - [HTML height Attribute](https://www.w3schools.com/tags/att_height.asp)
                - 数値も""で括ってるのか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - jsのclass周りが分からんのでとりあえずシンプルに作るけど、多分ゲームロジックと表示は分離すべきだな
    - できた
        - ![image](https://gyazo.com/bf6de99d4db760d4c37eb910c300dfaf/thumb/1000)
    - CSSも頑張った
        - ![image](https://gyazo.com/f5ffdff5e8db250a4de29d8f9a2fda32/thumb/1000)
        - おお～それっぽい<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>