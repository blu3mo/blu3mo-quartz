---
title: RustにNullは無い
---

from [Rust入門](Rust%E5%85%A5%E9%96%80.md)
[Rust](Rust.md)に*Null*は無い

* 返り値何も無いならnullではなく空タプル(unit)
  * Unitは
* [Enum](enum.md)のOption<T>、要は*Swift*とかのoptionalとやってることは同じ?
* optionalをunwrapする綺麗な書き方は、こんな感じか
  rust

````
match i32_bag.item {
    Some(v) => println!("found {} in bag!", v),
    None => println!("found nothing"),
}
````

````
- optional bindingに似ている
````

* swiftの!みたいなのは無いのかな
  * .unwrapがあるのね
    * まあ当然非推奨
    * 失敗するとerrではなくpanicなのか
