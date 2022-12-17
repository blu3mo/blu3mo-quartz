---
title:
 'CRDT'
---

- [https://crdt.tech/](https://crdt.tech/)
- [/sgg-fairy/CRDT](https://scrapbox.io/sgg-fairy/CRDT)
- [https://qiita.com/everpeace/items/bb73ec64d3e682279d26#pn-counter](https://qiita.com/everpeace/items/bb73ec64d3e682279d26#pn-counter)
- [https://misreading.chat/2020/10/31/89-conflict-free-replicated-data-types/](https://misreading.chat/2020/10/31/89-conflict-free-replicated-data-types/) <img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>

- [[Kineto]]では、このあたりを雑に実装していた
    - 消しゴムは要素の削除ではなく、透明化インク(?)の上塗りでやっていた
    - ふせんの文字の編集は、単純にタイムスタンプが遅い編集の結果でoverrideみたいな
    - まあ原始的なCRDTをやっていたとも言える
    - ただ、[[Kineto]]の様な独立した時間軸がある所でCRDTをやるのはおもろそう
        - 一般的なCRDTのユースケースでは、全員同じ時間を共有していることが前提となっていそう
            - その上で、遅れたアップロードとかに対応するためのCRDT
        - ただ、[[時間軸]]上を移動できる共同編集エディタでCRDTをやると、時間軸上を過去に移動してやったエディットがその後にも反映されるみたいなことが起きるはず<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - おもろそうだし、何か便利な環境が生まれるかも