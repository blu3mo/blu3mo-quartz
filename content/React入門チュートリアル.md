---
title:
 'React入門チュートリアル'
---

[React入門チュートリアル (1) Reactとは何か | Hypertext Candy](https://www.hypertextcandy.com/react-tutorial-01-what-is-react)
- [[仮想DOM]]
- [[コンポーネント指向]]

- [[CodePen]]、テストに良いな
    - 使い方も説明されてる

- [[ReactDOM]]も[[JSX]]も普通にjavascriptファイルとしてインポートできるのね
    - JSXとかどういう仕組みで成り立ってるんだろう
        - Javascript文法ガン無視の記述をどういう仕組みで成り立たせてるんだろう
    - JSXという文法で成り立ってると考えればおｋだと思う<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
        - TypeScriptやCoffeeScriptとおなじ
        - transpileすると生のJSに戻る
            - `<div>...</div>`が`React.createElement("div", null, ...)`みたいなのになる
        - なるほど<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

- JSXでループとか書いて複数生成する場合は、各要素の独自性を示すためのkeyが必要
    - 処理最適化のためにあった方が良いぞ、と

- Reactコンポーネントは、React要素を返す関数として作る
    - 入出力はcreateElementと同じような感じ
    - それをJSXがうまいこと繋いでくれる、と

- Reactを使わないDOM操作より[[宣言的]]にかけるのが嬉しいポイント

- JSXで <X> <Y /> </X> と書く場合、
    - Xのfunctionの中でchildrenプロパティを拾って返さないと、Yはrenderされない
        - なるほど<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - React.Fragmentとか、HTMLに元からあるタグの仮想DOMとかには、これが元から実装されてる感じかな

- 今のところの感想として、JSX気持ち悪〜〜という気持ち<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - まあ慣れでしかないんだろうけど、xmlとjavascriptが入り混じるのがすごい読みづらい
    - なんか名詞と動詞が入り混じってるみたいな?
        - [[手続き型言語]]と[[宣言型言語]]が入り混じってるってことかな
    - とりあえず、
        - html風の何かはどこに書いても良い
        - html風の何かの中にjsを書く場合は{}
        - みたいな、htmlの方が強く効く(?)イメージをもつの大事そう
    - {}の中身は最終的にオブジェクトって意識大事だな
        - `\`text${object}text\``の亜種だと考えるとしっくり来るかもしれない<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
            - これも`{}`の中が常に(object|premitive)

jsx

```
const element = (
  <ul>
    {members.map(member => (
      <li key={member.name}>
        {member.name} plays {member.instrument}
      </li>
    ))}
  </ul>
);
```

- いまいちこれがわからん
    - mapでmembersの各要素についてcreateElement("li", ~~)をしてるけど、それがどうulのchildになる?
        - mapだからchildの配列が生成されるんか、なるほど

[React入門チュートリアル (3) 属性と状態 | Hypertext Candy](https://www.hypertextcandy.com/react-tutorial-03-props-and-state)
- classではなくclassNameなのは、classがjsの予約後だから
- > 本質的には、フックが実行される回数は、レンダリングごとに同一でなければならないということです。
- >  なぜなら、React は内部で、呼び出し順によって state の値を管理しているからです。
    - 結構危うい仕組みなんだなw
    - まあ結局のところ、魔法とか別レイヤーのシステムじゃなくてjavascriptの関数でしかないからまあそうなるか

[React入門チュートリアル (4) フォームとイベントハンドリング | Hypertext Candy](https://www.hypertextcandy.com/react-tutorial-04-form-and-events#セレクトボックス)
- 要は子は親を知らないって事だな
    - [[依存関係逆転の法則]]（子が上位なので）
    - コンポーネント指向なのでそりゃこうなる
- onChangeとかは、changeする前なのね
    - webで言うかは知らんけど、iosでいうwillXXXみたいな?
    - というかイベントをちゃんと処理しないとそのchangeが残りすらしないから、willですらないか
    - まあiOS（swiftUI以前）のdid/willイベントとは違う感じなんだろうな
- なんでJSXの{}内でif文が使えない..?
    - [https://reactjs.org/docs/jsx-in-depth.html#props-in-jsx](https://reactjs.org/docs/jsx-in-depth.html#props-in-jsx)
        - expressionじゃ無いからダメらしい
    - でも、mapが許されて、React要素を返すif文が許されない理由がいまいちわからん
        - if文を内包する即時関数なら良いのね
        - じゃあもう本当にオブジェクトそのものが{}の中に入ってるべきってことか
    - でもじゃあ三項演算子がセーフなのも分からんな
        - [https://qiita.com/smicle/items/7d3b9881834dc0142fb7](https://qiita.com/smicle/items/7d3b9881834dc0142fb7)
            - > condition ? expr1 : expr2
            - 三項演算子は確実にexpr1か2のどっちかのexpressionを返すから、{}に突っ込めるってことか
            - 「Expression」が何なのかの詳細説明欲しいな
- Eventって結局どうなってる?
    - [Event - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Event) 抽象的なプロトコルがあるのね
        - e.targetは共通なのか
            - event出したオブジェクトを返す
            - iOSでいうsenderか
        - [FormDataEvent - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/FormDataEvent)
- 問題2
    - passwordのstateはpasswordコンポーネントに閉じ込めとくべきだったな
- [[Clonedle - Wordleクローン]]
- なぜ[[jsでfunction文ではなくconstで関数を宣言]]している?
    - [【JavaScript】varとfunction"文"は使わずにletとconstを使って欲しい（切実） - Qiita](https://qiita.com/mejileben/items/b8502173216aebae8d36)
    - なんだその仕様
    - さすがJavascript(?)

[React入門チュートリアル (5) ToDoアプリを作ってみよう | Hypertext Candy](https://www.hypertextcandy.com/react-tutorial-05-wrap-up-with-todo-app#タスクの完了状態を切り替える)
- Swiftに慣れてると、やっぱ型が厳密じゃないの気持ちわり〜という気持ちになる
    - 早くTypeScriptに移行したい
    - 関数の引数が曖昧なまま関数を受け渡しできるのが一番気持ち悪い
- あとEnumないの不便
jsx

```
// ❌ この書き方だと、関数を渡すのではなく実行してしまう
<Comp onSomething={doSomething(123)} />
// ✅ アロー関数でも OK
<Comp onSomething={() => doSomething(123)} />
// ✅ bind を使う
<Comp onSomething={doSomething.bind(null, 123)} />
```

- なるほど〜<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- [[Javascriptのthis]]
- <a>の[[onClick]]で[[e.preventDefault()]]すると、hrefに飛ぶのを止められる
    - [[Minecraftプラグイン開発]]を思い出すな

- [[useEffect()]]
- [[Hooks]]

[[Reactの開発環境]]

> 本連載は「入門」チュートリアルと銘打ちましたが、基礎の理解が何よりも重要です。実際、React ライブラリそのものに関しては、さらに学ぶべき内容はほとんどありません。本文でも触れましたが、Router や Redux などの周辺技術の知識や、何よりも、JavaScript の言語仕様への理解があれば、本格的な開発を始めることができるでしょう。
- お〜〜<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

- その先
    - from [React入門チュートリアル (8) Reactプロジェクトを始める方法 | Hypertext Candy](https://www.hypertextcandy.com/react-tutorial-08-how-to-start-project)
        - [[React Router]]
        - [[Redux]]
    - これ終わったら調べたい事
        - [[React+Firebase]]
        - [[React使う時のアーキテクチャ]]
            - [[iOSアプリ設計パターン入門]]のweb版みたいなのがあれば読みたいな
            - [[コンポーネント指向]]の時のアーキテクチャ、あんまりまだイメージが掴めてないので
            - [[ステート管理]]方法と呼ばれているみたい
        - [これからReactを学んでいくためのロードマップ](https://zenn.dev/ksyunnnn/articles/90fb2bbfd51dc1)

自分がReact学んだときとおんなじやつだ<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
- かなりわかりやすいチュートリアルだった覚えがある
- （[[React学習#60c61ae91280f00000a26bd3]]で知りました、ありがとうございます🙇‍♂️<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>）
    - よかったです<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
    - そしてすでにおすすめしていたことを完全に忘れてた()
