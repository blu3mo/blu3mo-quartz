---
title: ViewBuilder
---

[SwiftUI](SwiftUI.md)のやつ
[https://llcc.hatenablog.com/entry/2020/03/22/151751](https://llcc.hatenablog.com/entry/2020/03/22/151751)
.swift

````
VStack {
    Text("AAA")
    Text("BBB")
}
````

.swift

````
VStack.init(content: {
    ViewBuilder.buildBlock(
        Text("AAA"),
        Text("BBB")
    )
})
````

上の二つは同じ
