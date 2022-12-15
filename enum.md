---
title: enum
---

\#iOSアプリ設計パターン入門

* enumが思ったより奥深かった
* assosiated valueを使って、ある条件の時のみ必要な変数を綺麗に作れる

enum.swift

````
enum State {
	case inputting(validationError: Error?)
	case sending
	case sent(Message)
}
````

* この場合だと、sentの時だけMessageの値を保持したいからこれが良い
