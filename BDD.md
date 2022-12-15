---
title: BDD
---

* 二分決定*グラフ*

* *論理関数* = 0/1の組み合わせに対して0/1を返す物

* 論理関数をBDDで表せる
  
  * ![image](https://gyazo.com/ce01d2c01a9cfc4de3b0b783ed39203d/thumb/1000)
    * [https://ja.wikipedia.org/wiki/二分決定図](https://ja.wikipedia.org/wiki/二分決定図) より
* BDDで、AND, OR, XORなどが表現できる
  
  * 変数の数nに比例する大きさのBDDになる
  * 最後の出力の0と1を置き換えてあげれば、NAND, NORなども表現できる
* BDDは、変数の順序によってもサイズが大きく変わる

* BDDは、*簡約化*・*圧縮*できる
  
  * ![image](https://gyazo.com/c0107b3ace7dd8cb5c73b3a71f27a463/thumb/1000)
    * [https://www-alg.ist.hokudai.ac.jp/~thomas/publications/sigfpai06imz.pdf](https://www-alg.ist.hokudai.ac.jp/~thomas/publications/sigfpai06imz.pdf) より
    * 左が*論理関数*をそのまま木(BDT)にしたもの、それを真ん中の図(BDD)のように圧縮できる
    * 右はZDD（後述）
* [\[ZDD\]](ゼロサプレス型BDD)
  
  * 通常の[BDD](BDD.md)と少し違う圧縮方法
    * 少し違うというか、BDDより多くのものを圧縮する
  * BDDの圧縮基準に加え、1の場合に最終出力0に向かう場合もその変数自体を消しちゃう
    * つまり、何が*冗長*か、の定義がBDDと違う
    * 上の図の右の*グラフ*
  * 最終出力が1の場合のみ気にしたい場合に有効
    * ex: 商店の購買データ
  * 疎な集合（ほとんどの到着点が0）の場合に著しい効果が出る（コンパクトに表現できる）
* 一言でいうと
  
  * BDD: Dont'careを省略、密な論理関数に向いてる
  * ZDD: 負の出現を省略、疎な論理関数に向いてる
* 論理関数からBDD(もしくはZDD)を作りたい場合
  
  * BDTを作ってから圧縮すれば、当然作れる
  * ただ、この圧縮を毎回やってると*計算量*/*メモリ量*が大変なことになる
  * なので、直接*論理式*から圧縮されたBDDを生成したい
  * やりかた
    * *ボトムアップ*方式: 各変数を小さいBDDとして、二つのBDD同士をAND,NOT,OR演算で組み合わせて最終的なBDDを作る
    * *トップダウン*方式: BDTを作る過程で、（1を使った回数を数えたりして）作りながら圧縮していく
      * *フロンティア法*
* [離散構造処理](%E9%9B%A2%E6%95%A3%E6%A7%8B%E9%80%A0%E5%87%A6%E7%90%86.md)技術のフレームワーク上では、BDD,ZDD等の*決定グラフ*は「索引構造」にあたる
  
  * 論理演算、数え上げ、線形関数最大化、サンプリングなどの「基本演算」のやりかた
    * shannon decompositionで分解して、常に1/0を返す$f$にたどり着くまで再帰的に演算していく
    * Shannon Decomposition: $f_a = (\lnot x_i \land f\_{a0}) \lor (x_i \land f\_{a1})$
      * 要は、二分木の一分岐を数学的に表したもの
      * $f_a$と$f\_{a\prime}$の演算を、decompositionした上で*再帰*的にうことができる
* 応用先
  
  * 初期は集積回路の設計問題のためのアルゴリズム
  * 最近は処理能力の向上によって、めちゃでかい[BDD](BDD.md)が扱えるように
    * 経路探索
    * スーパーマーケットの売り上げデータから良く売れる商品パターンを探す
    * *交通事故*データーから危険な要素の組み合わせを調べる
  * [組み合わせ爆発お姉さん](%E7%B5%84%E3%81%BF%E5%90%88%E3%82%8F%E3%81%9B%E7%88%86%E7%99%BA%E3%81%8A%E5%A7%89%E3%81%95%E3%82%93.md)問題の解法も*ZDD*を使う
    * <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>n=26までの世界記録を争う話がすごい楽しそうw
      \#離散アルゴリズム
      <img src='https://scrapbox.io/api/pages/blu3mo-public/情報科学の達人/icon' alt='情報科学の達人.icon' height="19.5"/>
