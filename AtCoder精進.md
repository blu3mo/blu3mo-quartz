---
title: AtCoder精進
---

[AtCoder](AtCoder.md) とかを解いて、思ったこととか学びとかを記録する #競技プログラミング

* 精選100問 [https://qiita.com/e869120/items/eb50fdaece12be418faa](https://qiita.com/e869120/items/eb50fdaece12be418faa)
  
  * 18以前は書いてないけど解いた
  * *二分探索*
    * 19 ピザ - Set型を使ってしまって、.insertするたびにO(log N)かかっていた。Vecに変更して解決
    * 20 Snuke Festival - vec<int> a,b,cの3配列から一つづつ選ぶ問題、この場合は真ん中を固定すると楽（典型）
    * 21 射撃王 - 問題を言い換える、発想力必要。固定して問題をシンプルにできるか考える
  * *深さ優先探索*
    * 24 ALDS1_11_B - DFSの基本、再帰関数で実装した。テンプレできちゃえば楽
    * 25 島はいくつある? - GridグラフでDFS、四方向じゃなくて八方向なのがポイント
    * 26 Ki - DFSはまあまあ計算量あることに注意、累積和的な考えで記録してから足す。
      * POINT: 木じゃなくて、一次元配列だったらどう解くか考える
  * *幅優先探索*
    * 28 ALDS_11_C - queueで普通のBFSを実装
    * 29 幅優先探索 - 普通にグリッドBFSを実装
    * 30 チーズ - 各工場に順番にBFS
    * 31 イルミネーション - 六角形だから偶数列と奇数列でdx,dyを変える
* Educational DP [https://qiita.com/drken/items/dc53c683d6de8aeacf5a#c-問題---vacation](https://qiita.com/drken/items/dc53c683d6de8aeacf5a#c-問題---vacation) #動的計画法
  
  * 1 Frog 1 - 二つ前と一つ前を見る、DP
  * 2 Frog 2 - Frog 1を一般化するだけ
  * 3 Vacation - ひとつ前以外は影響しないことに気付けるかがポイント
  * 4 Knapsack - *ナップサック問題*、添字の*次元*を必要に応じて増やしていくのがポイント
  * 5 Knapsack 2 -
