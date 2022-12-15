---
title: Kinetoの弾性同期アルゴリズム
---

\#pKineto #弾性同期

* *離散アルゴリズム*
  * 
     > 
     > 離散構造は組み合わせ爆発起こしがち
  
  * なので、生徒間の関係を*グラフ*と捉えて離散系のアルゴリズムを用いる

*DAG*: 有向非巡回グラフ

* 時系列のものに多い?

* \#ブロックチェーン

* [自然言語処理](%E8%87%AA%E7%84%B6%E8%A8%80%E8%AA%9E%E5%87%A6%E7%90%86.md)的アプローチ
  
  * 書き込みの感情が近い/遠い人と繋ぐっていう考え方ありかも (minervaの人の提案)
* [自律分散システム](%E8%87%AA%E5%BE%8B%E5%88%86%E6%95%A3%E3%82%B7%E3%82%B9%E3%83%86%E3%83%A0.md)?でやるのが良いかもと
  
  * [引き込み現象](%E5%BC%95%E3%81%8D%E8%BE%BC%E3%81%BF%E7%8F%BE%E8%B1%A1.md)みたいな考え方
  * 指揮者なし
  * なぜ?
    * [コミュニケーション](%E3%82%B3%E3%83%9F%E3%83%A5%E3%83%8B%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3.md)の形に沿っているので自然な実装
    * それぞれの生徒が*予測不能*な動き（突然スローになったり、exitしたり）をする
      * なので、それを中央で管理しようとするより、ある程度の予測不能さ前提で各デバイスが自分の頭使って動く方が良さそう
    * あと実装が楽
      * バックエンド慣れてない
      * これなら、ローカルの頭を使って、情報をfirebase realtime dbで共有すればいいだけ
    * あと実装が面白そう
      * 地味にこれが一番かもしれんw
  * *自己組織化*という言葉もある
  * 簡単な実装として、*蔵本モデル*を使うとか
    * いや、でもそんなに意味がないな
* longitudinal waveの考え方をいれる
  
  * 映像にlongitudinal waveを置いて、隔点に向かって力が働くようにする
  * 力が働いた時の物理を定義したい
* *\<文献ログ> 結合振動子における集団引き込みと複雑ネットワーク*
  
  * 位相(phase)モデルで記述
  
  * ![image](https://gyazo.com/ca7b00c32800d77fe78d3a697c34acf1/thumb/1000)
  
  * てか、振動子である必要はないから、単純に$φ_2-φ_1$を速度に加えればよいのでは?
  
  * 蔵元モデルの振動じゃない版を作れば
  
  * 引き込み力(K)を生徒別で変えた方が良い?
    
    * 他人と今どのくらい繋がりたいか、ということベースで
    * 頻繁に会話している場合はK強めとか
  * 強制引き込み
    
    * 相互作用じゃなくて、何かの上の力で引き込みをすること
    * 周期的な外圧を加えるとか
      * 授業映像ベースで、同期ポイント作れたら良い
    * ペースメーカー
* 縦軸: 現実の時間, 横軸: 映像の時間, という表現でグラフでわかりやすく洗わせることに今更気づいた
  
  * むしろ、今までなぜ気づかなかったのかが分からない
* シミュレーション一回したい
  
  * swift playground?
  * 実装: *時間発展*する関数
    * [https://qiita.com/yotapoon/items/653776362a3db0f91f1e](https://qiita.com/yotapoon/items/653776362a3db0f91f1e)
    * [オイラー法](%E3%82%AA%E3%82%A4%E3%83%A9%E3%83%BC%E6%B3%95.md)
  * [オイラー法](%E3%82%AA%E3%82%A4%E3%83%A9%E3%83%BC%E6%B3%95.md)を複数の関数受けれるような形にした
    * *複数関数受けれるオイラー法のコード*
  * 微分関数（dxdt(x,t)）の中身を色々試した
    * Trial 1
      * シンプルに全部の平均値に近づいていくような仕組み、遠いほど強い重み
      * 傾きは、1+(-0.1~0.3)の範囲の制限がかかる（下がる方は遅くなりすぎて欲しくないので、上がる方より制限強めに）
      * ![image](https://gyazo.com/c56442a9709364a992fdd1477d4503ee/thumb/1000)
        .py

````
def dxdt(x, t):
    gradients = []
    k = 5
    for i in range(len(x)):
        gradients.append(1 + min(0.3, max(-0.1, (sum(x) / len(x) - x[i]) / k)))
    return gradients
````

````
    - Trial 2
        - 自分以外の線に引き寄せられる、近いほど強い重み（逆数関数を使ってる）
        - 傾きは、それぞれの引き寄せに(-0.1~0.3)の範囲の制限がかかる（下がる方は遅くなりすぎて欲しくないので、上がる方より制限強めに）
            - 上下に振れちゃう問題をどうにかしたい
        - k = 1.3
            - ![image](https://gyazo.com/91018ed9e7361e1ee646b1834d48157a/thumb/1000)![image](https://gyazo.com/1c2058d47bfc73608f5015819ddbefb4/thumb/1000)
        - k = 0.2
            - ![image](https://gyazo.com/02950b7967645d5ab539542679289e22/thumb/1000)![image](https://gyazo.com/dc1f25776bd2ec9b8197e4b2037675b1/thumb/1000)
                - もうちょっと緩やかなカーブがいい（1/xのかんすうをつかってるのでこの場合仕方がない）
````

.py

````
def dxdt(x, t):
    gradients = []
    k = 1.3 #天井とか床にぶつからない程度の弱さが良い
    for x_i in x:
        gradient = 1
        for x_j in x:
            if abs(x_i - x_j) > 0.1: #近づきすぎるとflipして逆方向に飛んじゃうので、0.1以下なら放置
                gradient += (k / ((x_j - x_i)))/len(x)
        # 0.3, -0.1は、傾きの制限
        # 下がる方は遅くなりすぎて欲しくないので、上がる方より制限強めに
        gradients.append(min(1.3, max(0.9, gradient)))
    return gradients
    
````

* シグモイド曲線
  * 色々ある、シグモイド関数とか*正規分布*とか
  * 
     > 
     > 多くの自然界に存在する事柄は、このようなS字曲線を取ります。
  
  * シグモイド関数
    .py

````
def sigmoid(x):
    return 1 / (1 + np.exp(-x))

# 微分方程式の関数
# xがこの値の場合に、
def dxdt(x, t):
         gradients = []
         for x_i in x:
             gradient = 1
             for x_j in x:
                gradient += (sigmoid(x_j - x_i) - 0.5) / len(x)
             gradients.append(gradient)
         return gradients
````

````
    - ![image](https://gyazo.com/b94046421a33d48e6204c934c86dbf70/thumb/1000)![image](https://gyazo.com/b945b4f978d3a41d7ca4746e3f6490a0/thumb/1000)
````

* クラスタリング
  .py

````
def dxdt(x, t):
        gradients = [0]*len(x)
        t_0 = t[0]
        np_x = np.transpose([np.array(x)])
        initial_kmeans = kmeans_plusplus_initializer(np_x, 2).initialize()
        instances = xmeans(np.array(np_x), initial_kmeans, ccore=True)
        instances.process()
        clusters = instances.get_clusters()
        print(clusters)
        for cluster in clusters:
            for i in cluster:
                gradient = 1
                for j in cluster:
                    gradient += (sigmoid(x[j] - x[i]) - 0.5) / len(x) 
                gradients[i] = gradient
        return gradients
````

````
- ![image](https://gyazo.com/26090456f7b3276e481564b7ac22d51a/thumb/1000)![image](https://gyazo.com/d3fb8ecbd8984a40c43af2762f01ae3a/thumb/1000)
- 結構うまく行った
- x-meansを使った (k-meansの個数自動版)
- 上二つはグループになったりならなかったりが安定しないので、グラフがガタガタになる
    - これはどうにかすべき
- あと、あんまりエレガントさがない、本当はシンプルな関数だけでできたらもっと嬉しい
````

* DBSCAN的クラスタリングベースのやつ
  .py

````
def dxdt(x, t):
    eps = 5

    gradients = []

    for x_i in x:
        xDifs = []
        for x_j in x:
            xDifs.append(x_j-x_i)
        xDifs.sort()

        upperBorder = x_i
        positiveXDifs = list(filter(lambda x: x >= 0, sorted(xDifs)))
        for i in range(len(positiveXDifs)-1):
            if (abs(positiveXDifs[i+1] - positiveXDifs[i]) > eps):
                break
            upperBorder = x_i + positiveXDifs[i+1] 

        lowerBorder = x_i
        negativeXDifs = list(reversed(list(filter(lambda x: x <= 0, sorted(xDifs)))))
        for i in range(len(negativeXDifs)-1):
            if (abs(negativeXDifs[i+1] - negativeXDifs[i]) > eps):
                break
            lowerBorder = x_i + negativeXDifs[i+1]

        gradient = 1
        xInRange = list(filter(lambda x: lowerBorder <= x and x <= upperBorder, x))
        for x_other in x:
            if lowerBorder <= x_other and x_other <= upperBorder:
                gradient += (sigmoid(x_other - x_i) - 0.5) / len(x)
            else:
                gradient += ((sigmoid(x_other - x_i) - 0.5) / 10) / len(x)
        gradient = max(gradient, 0.8)
        gradient = min(gradient, 1.2)
        gradients.append(gradient)

    return gradients
````

````
- 雑で長い（どうせswiftで書き直すのでとりあえず雑に作った）
- 仕組み
    - DBSCAN的なクラスタリングをした
        - クラスタ内なら普通にsigmoidで引き寄せ
        - クラスタ外なら弱めに引き寄せ
    - あと制限もつけた、0.8~1.2
    - epsの値は悩む
- 以下ランダムにジェネレートした実行例 (eps=5)
    - ![image](https://gyazo.com/83bf23f3b9d5cc4040818cf3c2c71ced/thumb/1000) ![image](https://gyazo.com/02411fe88e47425a40e3b040f093f7fe/thumb/1000)
    - ![image](https://gyazo.com/d4eb7cebc41085ba6d369ab9a2463b95/thumb/1000) ![image](https://gyazo.com/6f0a40bc30b7261c691534c186268f51/thumb/1000) ![image](https://gyazo.com/f257a0189adde426ee6fefc528541d1b/thumb/1000) ![image](https://gyazo.com/d770a92d0e0aa29968447f5057bfd77c/thumb/1000)
    - ![image](https://gyazo.com/45a4fa1c5606e3d794db4d053633ef61/thumb/1000)
- 結構理想系ではある
- 問題点
    - 人数がめっちゃ大量になると、全部一つのクラスタになってしまう
    - なにかしらのlimitはつけるべき
    - sigmoidでaverageによってくモデルもありかも(TODO)
    - さまざまなepsでクラスタリングやって、小さいepsで含まれるやつほど重み強めとかもありかも
````

* 実装
  * KinetoWatcherで見たやつ
  * ![image](https://gyazo.com/ec9f408cf3b24f3ea930369884c857ab/thumb/1000)
    * これは、ただの平均値吸い寄せモデル(Trial 1)
