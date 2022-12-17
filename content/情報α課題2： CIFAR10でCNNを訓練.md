---
title:
 '情報α課題2： CIFAR10でCNNを訓練'
---

from [[東大1S情報α]]
情報α課題2: [[CIFAR10]]でCNNを訓練
- とりあえず5層くらいで
    - .375
- 12層に増やした
    - .325
    - あれ、悪くなった
- 5層で、パラメータの数60に増やした
    - .410
    - 良くなった
- このままパラメータ馬鹿でかくするとどうだろう?
    - 120とかにした
        - ![image](https://gyazo.com/b084c728f74b09dc1a88cf882e2b47eb/thumb/1000)
        - おお、trainは上がったけど汎化性能は微妙
            - まあそりゃそうか、パラメータ増やせばそりゃ表現できることは増える
            - ここからどう汎化させるかが問題<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- 最後の方のレイヤーはパラメータの数絞ってみた
    - そうすれば最後の方では汎化する圧がかかる?
    - あんまり変わらず
- Convolutionもっとするか
    - あんまりaccuracyは良くないけど、trainとvalidateが大体同じグラフになった
    - つまり、汎化はクリアしているのでモデルの表現力を高めればいい
- Denseを連打してみる
    - ダメだった
    - .35あたりで止まってしまう
- Convも連打してみる
    - うーん、上手くいかん
- activation functionいじってもあまり変わらん
- Convのfilter数が1なのが問題なのでは
    - convのパラメータや出力がこれだと少ない
    - きた<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - これだ
    - やっぱConvのパラメータが増えないことには表現できるものも増えないってことか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - ![image](https://gyazo.com/aa646d219b35b32954238ed35098505b/thumb/1000)
    - その上でdense連打
        - ![image](https://gyazo.com/7850468eae1d91bab7f18b13413ea346/thumb/1000)
        - 予想通り二つが乖離する
            - だんだんわかってきた<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - 色々試したけど、0.7の壁を越えられないな
        - 表現力高めればtrainの方はほぼ1まで近づくけど、validateの方は0.7が天井
        - ![image](https://gyazo.com/10e28342362744f1b13d7dcef42169a3/thumb/1000)

    - レイヤー減らしてみる?
        - 多少良くなったのと、終わるのはめっちゃ速くなった
    - LeakyReLUにしたら多少改善
    - [https://qiita.com/koshian2/items/e66a7ee9bf60ca24c940](https://qiita.com/koshian2/items/e66a7ee9bf60ca24c940)
        - カーネルサイズはだんだん大きくしていく方がよいらしい
            - 確かに、考えたらそうだわ
            - 細部の特徴を得た後に、大きい特徴を得るべき
        - でもあんまり改善せず
    - [[VGG16]]を一部真似してみる
        - convメインな感じの構造なのね、最後にバカでかdenseを二つ持ってくる感じ
        - ![image](https://newtechnologylifestyle.net/wp-content/uploads/2019/02/CNN.png)
            - ↑で、画像の縦横次元を圧縮して一次元にするみたいなイメージを思い出した<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - ![image](https://gyazo.com/05908f5914c60b51fdb272277ed05e7a/thumb/1000)
            - 結構明らかに0.7を越えれた<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
 _

```
  Input(shape=input_shape),
  Conv2D(64, kernel_size=(3, 3)), activation,
  Conv2D(64, kernel_size=(3, 3)), activation,
  MaxPooling2D(pool_size=(2, 2)),
  Conv2D(128, kernel_size=(3, 3)), activation,
  Conv2D(256, kernel_size=(3, 3)), activation,
  MaxPooling2D(pool_size=(2, 2)),
  Conv2D(256, kernel_size=(3, 3)), activation,
  Conv2D(512, kernel_size=(3, 3)), activation,
  #MaxPooling2D(pool_size=(2, 2)),
  Flatten(),
  Dense(2000), activation,
  Dense(2000), activation,
  Dense(output_dim, activation = "softmax")
```

        - Dense(2000)を三つにしたり、Convレイヤーの数やフィルタ数を増やしたら、↓が起きる様になった
            - ![image](https://gyazo.com/8f2a9ce24b276c9fffdb938826b0f5dd/thumb/1000)
                - 授業でやったやつだ
            - 色々いじったけど[[情報α課題2： CIFAR10でCNNを訓練#627faf6e79e1130000a462d4]]より良いのは見つからず
        - バッチサイズ調整
            - [batch_sizeの調整](https://teratail.com/questions/246310)
                - ええ、バッチサイズ減らすとむしろ時間かかるのか
            - 1024とかにしたら多少良くなった
                - なぜだろう?
                - 汎化しづらくなるのではと思ったけど
                - ![image](https://gyazo.com/d08c14ad291f2f974bf7f1933a4c2a93/thumb/1000)
                - 1000: 安定して.75 validate届く
                    - ![image](https://gyazo.com/4a0793a76f7c80826afcb10701e15812/thumb/1000)
                    - ただそれ以上には行かない、という感じ
        - 汎化させたいならData Aug.とかDropoutとかやってみれば良いのかな
            - DropOut
                - .2を三箇所
                    - ![image](https://gyazo.com/56694648b61aa6c542fea9a218b8c94d/thumb/1000)
                    - おお、良さげ
                - もっと増やしてみる
                    - .77あたで止まっている
                - DropOut増やして汎化性能高めたなら、同時にパラメータやレイヤー数も増やして良いのかも?
 _

```

  Conv2D(128, kernel_size=(3, 3)), activation,
  Dropout(.4),
  Conv2D(128, kernel_size=(3, 3)), activation,
  MaxPooling2D(pool_size=(2, 2)),

  Conv2D(128, kernel_size=(3, 3)), activation,
  Dropout(.4),
  Conv2D(256, kernel_size=(3, 3)), activation,
  MaxPooling2D(pool_size=(2, 2)),

  Conv2D(256, kernel_size=(3, 3)), activation,
  Dropout(.4),
  Conv2D(512, kernel_size=(3, 3)), activation,
  GlobalAveragePooling2D(),

  Dense(2000), activation,
  Dropout(.4),
  Dense(2000), activation,
  Dense(output_dim, activation = "softmax")
```

            - これで.8タッチくらい
        - Data Augmentation
            - rotationとflipを入れてみた
            - ![image](https://gyazo.com/e28c33eb69497a60dd3abf35c598fd03/thumb/1000)
            - おお、trainとvalidateが同じ伸びになった
                - 良い<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                - あとはこのepoch数上げたり表現力高めれば
            - data augmentation、上下flipは不要かも?
                - [https://www.cs.toronto.edu/~kriz/cifar.html](https://www.cs.toronto.edu/~kriz/cifar.html) をみている感じ
                - ![image](https://gyazo.com/cd8b443cf3c12ca2116a92edab8eab0b/thumb/1000)
                    - あまり変わらず
            - ![image](https://gyazo.com/ffbc1439df095d5d47612ef21084804e/thumb/1000)
                - ずっと続けるとこんな感じ
        - batch数をさらに上げてみる、2000
            - あんまり変わらん
        - RandomRotationをなくしてみたら、さらに上がった
            - ![image](https://gyazo.com/89f7ea2f035a36b961971e388ee6432d/thumb/1000)
            - ただtrainに追いつかないのも少しある
            - rotationの仕方が悪かったとか?<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                - ![image](https://pytorch.org/vision/stable/_images/sphx_glr_plot_transforms_009.png)
                - 多分この黒い部分がよくなかったのだと思う
                - 治した✅
        - カーネルサイズをだんだん大きくする
            - ![image](https://gyazo.com/4edebe15b22551073e3d353abafef603/thumb/1000)
            - うぉ、60回回したらこんな形に
                - これは線形的な伸びをこの後も期待できる?
                - いや、でも普通に悪化している気もするな
