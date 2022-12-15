---
title: Redux
---

[HookとRedux ToolkitでReact Reduxに入門する | Hypertext Candy](https://www.hypertextcandy.com/learn-react-redux-with-hooks-and-redux-starter-kit)

* コンセプトとしては、
  
  * stateの*バケツリレー*が辛いから、stateをコンポーネントの階層構造から切り出す
  * その上で、カオスにならないようにstateの操作方法に[制約](%E5%88%B6%E7%B4%84.md)をつける
* って感じかな

* もの
  
  * state
    * 状態のオブジェクト
  * action
    * 状態の更新を指示するオブジェクト
    * 更新内容自体ではなく、reducerに飲ませるラベルしか持たない
  * reducer
    * actionオブジェクトを受け取って実際にstateを操作する関数
  * action creator
    * actionを生み出す関数
* 直接state操作するのではなくstate操作をwrapのはわかる
  
  * 制約が生めるので
  * でも、actionオブジェクト + reducerを挟む必要性が分からん
    * action creatorの位置にある関数がstate操作したら何がまずい?
  * 1回より2回分割&抽象化した方が良いだろ、みたいな話?
    * 違う気がするな
* とりあえず物作って学ぶ方優先したいので、バケツリレーが辛くなってきたら学ぼうかな
  \#React
