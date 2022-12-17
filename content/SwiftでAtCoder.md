---
title:
 'SwiftでAtCoder'
---

[[Swift]]で[[AtCoder]]
理由
- C++を覚え直すの大変だし意義あんまなさそう
- 未開感があって面白そう
- JOIでC++必要なのは本戦以降、本戦が重要になるレベルまで辿り着かない気がするから
    - 本戦に出れるかどうかっていうところかな..?
    - 今後自分が急成長したらまた話は別だけど
- Swift推しなので

やること
- 入出力の整備
- [[STL]]にある様なもので、足りないものを実装
- テンプレ系アルゴリズムを実装
- Swiftの配列操作とかの計算量を把握

- [https://qiita.com/taka1068/items/e487e7becd4b1644ec86](https://qiita.com/taka1068/items/e487e7becd4b1644ec86)
    - > SwiftのLazySequence/LazyCollectionを使ってパフォーマンスを追求しよう
- [https://qiita.com/yum_fishing/items/7592a56f7e9dbeef8e75](https://qiita.com/yum_fishing/items/7592a56f7e9dbeef8e75)
    - > Swift で map, compactMap, flatMap を使いこなそう
- [https://rizumita.medium.com/swiftのfor-inとmapやreduceの速度を比べてみる-21d059c02a85](https://rizumita.medium.com/swiftのfor-inとmapやreduceの速度を比べてみる-21d059c02a85)
    - > Swiftのfor inとmapやreduceの速度を比べてみる

- パフォーマンスのテスト
>  0.00007.998943328857422 //スタート直後
>  0.00024902820587158203 //入力1行目読み
>  0.0002950429916381836 //2行目読み
>  0.0003980398178100586 //...
>  0.0004029273986816406 //最終行読み
>  0.00040793418884277344 //データ処理ループ開始
>  0.00040900707244873047
>  0.0004099607467651367
>  0.00041103363037109375
>  0.0004119873046875 //処理ループ終了
>  0.00041294097900390625 //出力終了
- 一行目を読むまでに時間がかかっている...
    - じゃあ逆にループ回すだけならそんなに問題ないのかな?
