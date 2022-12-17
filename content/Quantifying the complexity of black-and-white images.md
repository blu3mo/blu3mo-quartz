---
title:
 'Quantifying the complexity of black-and-white images'
---

[https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0207879](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0207879)
- Complexity([[複雑]]さ)についてのいろんな分野(cs, bio, etc)のいろいろな話が書かれている
    - 定量的評価難しいけど、できたらいろんな分野で価値大きいよね、と言う話
    - [[エントロピー]], [[乱雑さ]]とも関連づけ

- この研究は画像でやるけど、[[ヒストグラム]]とかその他配列化できるものならなんでも理論上応用できるよと

- 方法
    - 白黒画像のいろんな位置（範囲）でgray levelのヒストグラムを作って、その分散の平均を取る
        - [[カーネル]]みたいな考え方
    - ヒストグラム作る範囲によって分散の平均は変わってしまうので、さまざまな解像度(=さまざまな相対的カーネルサイズ）で試す
        - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>これは、スライド/黒板という用途に絞るなら事前に解像度決めちゃっても良さそう #情報科学の達人映像処理研究
    - "typical scale"という言葉が使われている（複雑さが見える長さみたいなイメージ？）
    - あと、全部を加味したcomplexity indexというのも定義されている、これも使えそう?
![image](https://gyazo.com/8dd456880875acc29641cf8df108f224/thumb/1000)
![image](https://gyazo.com/2d957c700ec9490b9a10656d4581deb9/thumb/1000)

