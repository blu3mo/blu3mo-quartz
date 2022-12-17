---
title:
 'Hooks'
---

from [[React入門チュートリアル]]
Hooks
[React入門チュートリアル (7) カスタムフック | Hypertext Candy](https://www.hypertextcandy.com/react-tutorial-07-custom-hook)
- Hooksってのは要はデータ変化で呼ばれるイベントみたいなもんかな
    - それは[[useEffect()]]だけか
- `use`の意味（何が何をuseするのか）をいまいち掴めていない
    - [フック早わかり – React](https://ja.reactjs.org/docs/hooks-overview.html)
    - Reactの物を、Reactでない物がuseする?
- 意図としては、[[関数コンポーネント]]でもReactの物を使えるようにしようと言う事かな
    - そこのuseかな?
    - [[クラスコンポーネント]]より、[[関数コンポーネント]]+[[Hooks]]の方が良いのでは、という感じか
        - [最近Reactを始めた人向けのReact Hooks入門](https://sbfl.net/blog/2019/11/12/react-hooks-introduction/)
        - > Hooksは違います。ひとつの機能は、ひとつのHooksの中で完結します。「値の読み取りと値の更新」や「ストリームの購読と購読解除」など、関心事を単一のHookの中にまとめてしまっているのが特徴です。
        - >  「書けるところに書く」で無秩序に複雑化するクラスコンポーネントに比べ、「ひとつの機能は、ひとつの場所に」を実現する関数コンポーネントとHooksは、まさにReactを救うヒーローとも言えます。
    - [/villagepump/React Hooks](https://scrapbox.io/villagepump/React Hooks)
    - useXXXのXXXはReactが持つから、それをuseする感じ?
        - XXXはReactに依存してる
- 外界とのやりとりの処理をwrapしたい時にHooks（use___）を作るって感じかな
    - 外界: 非同期通信するAPIや、Reactのstateなど
    - 値の更新等のイベントを受け取ったり
    - 値をsetしたり
#React