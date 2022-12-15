---
title: generics
---

[https://qiita.com/ktaguchi/items/fc260a0af506f258177d](https://qiita.com/ktaguchi/items/fc260a0af506f258177d)
generics.swift

````
func makeTuple<T: Comparable>(a: T, inout _ b: T) -> (T, T) {
    if b < a {
        b = a
    }
    return (a, b)
}
````

TをComparableという[protocol](protocol.md)に制限することで、比較を可能にする

* whereでさらに制限も可能
  * [https://qiita.com/shoheiyokoyama/items/31eca0d4b27bc9608eb8](https://qiita.com/shoheiyokoyama/items/31eca0d4b27bc9608eb8)
