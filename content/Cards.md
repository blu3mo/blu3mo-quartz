---
title:
 'Cards'
---

with <img src='https://scrapbox.io/api/pages/blu3mo-public/axokxi/icon' alt='axokxi.icon' height="19.5"/>
[/collab/遅延コミュニケーション探求](https://scrapbox.io/collab/遅延コミュニケーション探求)

- [[時間軸指向のコミュニケーション]]に注目して、
    - [[時間軸指向]]ではない形のコミュニケーションを目指す、陣地玉入れのようなチャットアプリ
- [[時間軸への依存からの脱却]]を目指す
    - [/villagepump/時間軸への依存から脱却するためには](https://scrapbox.io/villagepump/時間軸への依存から脱却するためには)

実装方針
- アーキテクチャ
    - [[MicroViewController]]、気になる
    - とりあえず[[Clean Architecture]]だけ意識して、細かい所は自分で考えてやってみたら面白そう
        - のちに大崩壊しても大きな問題はないので（自分が大変なだけ）
        - ![image](https://gyazo.com/4f40c15befb2b2f3ed8c16a73b1ffcbe/thumb/1000)
        - こんなとか?（左は現状の理解の[[MVP]], 右はこんなかんじでどうだろうという形）
            - まあ ①すでに名前がついている ②なにかしら問題がある のどちらかだと思うけど、せっかくなのでこれでやってみる
    - UseCase
        - GetとPostするやつ
        - 今の仕様では一度送ったら編集できないけど、もし今後変えるとしたらUseCaseを追加する形になる
- データの持ち方
    - 人
    - カード
        - 時系列順に参照することより、ネットワークを辿って参照することの方が多そう
        - [[グラフデータベース]]とか気になっている
            - まあいらんか
        - Githubのコミットみたいな構造のデータを持つ場合ってどういうのがいいのかな
        - 結局[[Firebase Realtime Database]]が最適なのかな
- UI
    - [/collab/Cards UIデザイン0524](https://scrapbox.io/collab/Cards UIデザイン0524)
    - [[Fluid Interface]]っぽくしたい
    - [[Hero]]
- 作る物リストアップ
    - LINEログイン
    - ホームのスクロールUI
    - 編集画面
    - Firebaseもろもろ
- [[小さくても成り立っている物を作る]]のは大事
    - 土曜の終わりの時点で動くようにしたい
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/axokxi/icon' alt='axokxi.icon' height="19.5"/> <img src='https://scrapbox.io/api/pages/icons/ありがと/icon' alt='/icons/ありがと.icon' height="19.5"/>
- Viewが欲しい物
    - ホームに表示するカードの情報
        - 時系列順に並べたり
        - idからカードの情報が欲しい
        - 新着かどうか知りたい
    - 友達ユーザーの情報

