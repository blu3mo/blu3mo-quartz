---
title:
 'useEffect()'
---

from [[React入門チュートリアル]]
useEffect()
[React入門チュートリアル (6) 副作用 | Hypertext Candy](https://www.hypertextcandy.com/react-tutorial-06-effect)
- Reactの都合に合わせて他の処理も動かすための[[useEffect()]]
    - > useEffect に渡したコールバック関数は、必ず、レンダリングが完了した後に実行されます。そのため、そのコールバック内であれば安全に DOM を参照できます。
    - タイミングは第二引数でうまいこと調整できる
        - > このように、useEffect は、「この変数が更新されたらこの処理を実行したい」というパターンにも利用できます。
    - useEffect内で変なものを返すとまずい（クリーンアップ関数を返すべき場所なので）
- [[Javascriptの非同期処理]]
#React
