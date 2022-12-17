---
title:
 'Softmax'
---

- ![image](https://i.ytimg.com/vi/lvNdl7yg4Pg/maxresdefault.jpg)
- なぜこれ？
    - 出力の合計が1になるようにしたいので、総和の分数として表現する
    - また、入力のzの値がなんであっても正になってほしいので、$e^z$にする
- 結果は[[One-hot]]ベクトルと同じフォーマット
    - one-hotベクトルは、softmaxの出力としてみれば実質一つの確率が100%だと言っているので
