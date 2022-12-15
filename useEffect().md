---
title: useEffect()
---

from [React入門チュートリアル](React%E5%85%A5%E9%96%80%E3%83%81%E3%83%A5%E3%83%BC%E3%83%88%E3%83%AA%E3%82%A2%E3%83%AB.md)
useEffect()
[React入門チュートリアル (6) 副作用 | Hypertext Candy](https://www.hypertextcandy.com/react-tutorial-06-effect)

* Reactの都合に合わせて他の処理も動かすための[useEffect()](useEffect%28%29.md)
  * 
     > 
     > useEffect に渡したコールバック関数は、必ず、レンダリングが完了した後に実行されます。そのため、そのコールバック内であれば安全に DOM を参照できます。
  
  * タイミングは第二引数でうまいこと調整できる
    * 
       > 
       > このように、useEffect は、「この変数が更新されたらこの処理を実行したい」というパターンにも利用できます。
  
  * useEffect内で変なものを返すとまずい（クリーンアップ関数を返すべき場所なので）
* [Javascriptの非同期処理](Javascript%E3%81%AE%E9%9D%9E%E5%90%8C%E6%9C%9F%E5%87%A6%E7%90%86.md)
  \#React
