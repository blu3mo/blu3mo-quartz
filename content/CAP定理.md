---
title:
 'CAP定理'
---

<img src='https://scrapbox.io/api/pages/blu3mo-public/情報科学の達人/icon' alt='情報科学の達人.icon' height="19.5"/> [[データベース]](NoSQL)の講義

- CAP特性
    - C: Consistency [[一貫性]]
    - A: Availability [[可用性]]
    - P: Partition Tolerance [[ネットワーク分断耐性]]
- CAP定理: 「システムはCAP特性のうち二つしか保証できない」
- 例
    - [[リレーショナルデータベース]]
        - C,Aを保証している
            - --> [[ACID特性]]
    - [[NoSQL]]: 場合による
        - AとPを保証している時
            - --> [[BASE特性]]を持つ
