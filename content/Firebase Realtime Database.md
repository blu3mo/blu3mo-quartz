---
title:
 'Firebase Realtime Database'
---

- [[Firebase]]
- [[Google Cloud Platform]]

- [https://qiita.com/1amageek/items/b350ee5ef0c9b2406583](https://qiita.com/1amageek/items/b350ee5ef0c9b2406583)
    - Firebase Realtime Databaseは一貫性を犠牲にすることで、可用性と分断耐性に優れたクラウドシステムである。
    - 一貫性を犠牲にすると言っても、トランザクションの機能は提供されている。
    - Firebaseは緩やかな一貫性の上に成り立っている

- [https://qiita.com/1amageek/items/64bf85ec2cf1613cf507](https://qiita.com/1amageek/items/64bf85ec2cf1613cf507)
    - 冗長になってしまうのは割り切る
        - 相互参照の構造
    - ウェブとMobileの性質の違い
 firebase
| Mobileの性質 | ソリューション |
| -- | -- |
| ネットワークは不安定 | Realtime・AutoSync・Offline |
| リソースに制限がある | Realtime・AutoSync |
| 表示領域に制限がある | Realtime・AutoSync |
| 開発速度が速い | Realtime・AutoSync・Schemaless |
    - 設計のコツ
        - Modelは並列に構成する
        - Model名は単数形の名詞にする
        - ModelのKeyはSortできるキーをセットする
        - Modelは_updatedAt _createdAtを保持する（バグ解決に役立つ）
        - Model内に配列を保持しない
        - Model内のプロパティにAccessKeyを含める

- [https://firebase.google.com/docs/database/ios/structure-data?authuser=0](https://firebase.google.com/docs/database/ios/structure-data?authuser=0)
