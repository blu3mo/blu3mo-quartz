---
title: ParallelTalk先行研究探し
---

[ParallelTalk](ParallelTalk.md)
[Pragmatics of Computer-Mediated Communication](https://www.degruyter.com/document/doi/10.1515/9783110214468/html#contents)
[Exploration of Possibility of Multithreaded Conversations Using a Voice Communication System | SpringerLink](https://link.springer.com/chapter/10.1007/978-3-540-73110-8_20)

* *Computer Mediated Communication*という概念があるのか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

  * *テクノロジーの膜*で言いたかったことに近そう
  * でも*テクノロジーの膜*は人-人間のコミュニケーション以外も指してるつもり

[https://www.isca-speech.org/archive/pdfs/icall_2004/demol04_icall.pdf](https://www.isca-speech.org/archive/pdfs/icall_2004/demol04_icall.pdf)

[https://www.inkandswitch.com/peritext/](https://www.inkandswitch.com/peritext/)

* ![image](https://www.inkandswitch.com/peritext/static/branching.svg)
* この図をみて思ったが、[CRDT](CRDT.md)にやりたいことの方向性は近いかも
  * 人間のコミュニケーションにおける出力を並列でやって、あとでマージするみたいな
    * 最終的な状態は一意に定まる
  * [ターン制コミュニケーション](%E3%82%BF%E3%83%BC%E3%83%B3%E5%88%B6%E3%82%B3%E3%83%9F%E3%83%A5%E3%83%8B%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3.md)の問題は、conflictと捉えられるな
* ただ人間の脳はCRDTの仕組みそのままでは情報を受け取れないと思うので、そこを上手くやるのが頑張りどころな予感
