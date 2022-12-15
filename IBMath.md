---
title: IBMath
---

* GDC
  
  * 面積をもとめるとき
    * インテグラるで入力するより、ぐらふ書いた方が楽
  * 連立の解を求めるとき
    * 機能を使うべき、圧倒的に楽＆安心
  * d/dx=0を求める時
    * 真面目に計算せずに、gdcに任せるべき
* IBMathP1
  
  * 多少時間があまるとはいえ、難しい問題にこだわるのはよくない
  * ある程度考えて分からんかったら飛ばして、最後に時間を残す方が良い
    * 時間置くと思いつくことも多いし
* IBMathP2
  
  * 時間が無いので、テキパキ解くことを意識
  * "exact"に注意
    * ある場合はGDCまずい
* IBMathP3
  
  * 新形式
  * 解いていて一番楽しい
  * 時間は結構きつい
    * 初回は数問解けず
    * 回答の厳密さよりは速度を意識すべき
  * 注意点
    * 証明問題で無ければ、めちゃくちゃ厳密に説明する必要はない
      * 三角形の辺とかに厳密に言及する必要はない
    * 解答は必要な数式さえあればoKというスタンスっぽい
      * 逆に、数式はできる限りstepを細かく書いた方が良さそう
      * x/2=a, x=2aくらいの細かさ（余裕あれば）
    * どのくらい書けば良いか掴めないなと思ったら、文字は少なく数式多くを意識したい
  * 最後の問題を解くコツ
    * 分からない場合は、前提条件をちゃんと確認する
  * [自作IB Math P3](%E8%87%AA%E4%BD%9CIB%20Math%20P3.md)
* 回答のコツ
  
  * 計算プロセスをやみくもに細かくすれば良いわけではないっぽい
  * 何かが等価であることみたいな、何かの関係を数式で示すことが点になることが多そう
  * 得点を意識して、本当に正しい解法かをチェックすべき
    * 確率系の問題は特にそう、6点なのにシンプルすぎる解法だったら疑うべき
* 勉強プラン
  
  * とりあえず不安なトピックを練習して解消
  * その後はP3をたくさん解きたい
    * 一番練習が必要&短時間でできる&比較的楽しいので
* 不安なトピック
  
  * vector
    * これは練習不足が主な理由
  * probability系
    * これは昔できたことを思い出せればok
  * むずい積分
    * 練習不足
* 試験準備
  
  * Q. I found past papers of “Further Mathematics HL” and “Mathematics HL”, which should I use  to prepare for Math AA HL?
  * 
     > 
     > Mostly Math HL. Some question types might be found in Further math.
  
  * 
     > 
     > For example integration by parts, macluarin series and differential equations

* 高2期末以降の範囲を復習・問題解き
  
  * やること
    * 教科書に移した問題あれば解く
    * Kognityのexam style Qs
  * 範囲
    * Oblique FunctionとStatistics
    * Calculus
  * 思った事（大事なことのみ）
    * Statistics、細かいミスが怖いなー
      * varianceを求めてると思ったらSDだったり
        * 表とか見て脳内でvarianceが直感で分かるようになれば強いかも？
    * 計算機の使い方が分かってきたなーと感じている
      * 表を作る時のvariable nameをつけ方とか
        * xとかyだと衝突するので、名詞の頭文字にする、squareは文字二つで表現、frequencyはfに名詞の頭文字つける
* 凡ミス書き出し
  
  * integrationで、丁寧に途中式を書いてないからごっちゃになる
    * 特にby partsとかは、表とかの書き方を身につけた方が良さそう
    * 係数に掛けるのを二度やっちゃう事多い、注意

---

* exam準備する未来の自分へのメモ
  * 問題を見て、部分点がどういう付き方をするのか推測できる能力大事かも？
    * 特に[数学的帰納法](%E6%95%B0%E5%AD%A6%E7%9A%84%E5%B8%B0%E7%B4%8D%E6%B3%95.md)とか点を全部拾えないと悲しい
      * これは必要な項目をリストアップしたい
  * 証明問題の解答を丁寧にかこう
    * そこまで凝らないとしても、せめて順番ぐちゃぐちゃのを矢印で繋ぐみたいなのはやめたい
    * そもそも丁寧に書こうとする意識を全くしていなかったので、ちゃんと意識さえすれば問題ないレベルにはなると思う<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    * 数式番号を振れば、矢印でぐちゃぐちゃになるのを防げるかもしれません<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

      * $\cdots①$や$\text{\textemdash}①$を末尾につける
      * 使うときに「$①$に$n=k+1$を代入して」「$①$の両辺を微分して」「$①\land②$より」などと参照して使う
  * mathematical induction、自分流のひょうきが本番でもokなのか改めて確認したい
    * "P(n) is true"は正しい表記なのかな？
    * 問題ないと思いますよ<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

      * もう少し数学よりにするなら$P(n)\iff\top$とかかな
      * 証明論の記号を使うなら$\vdash P(n)$だけど、先生によっては読めない可能性がある
      * $\therefore P(n)$が一番無難かな？
  * 最後の中間以降のトピックは結構不安なので、夏休みあたりにちゃんとやりたい
    * Integration周り
