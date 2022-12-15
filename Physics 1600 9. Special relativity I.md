---
title: Physics 1600 9. Special relativity I
---

* *相対性理論*〜
  * テスト
* 
* Galilean Transformation
  * new frame of referenceを考える、みたいな話
    * constant galelilan velocity
  * これは、vector algebraとしてまあ自明な計算
* ただ、これが実は崩れる
  * [![](https://i.kakeru.app/00ffec286231f5753fbcb91fa4ea38b0.svg)](https://kakeru.app/00ffec286231f5753fbcb91fa4ea38b0)
* 別の視点だと、Electro MagneticのLaws
  * *Maxwell Equations*
    * 式の項に$c$ = speed of lightが入る
  * これは、Newtonianにおける「Frame変えてもLawは変わらない」という原則（*Galillean Relativity*）と矛盾している
    * なるほど〜！
  * これを治すために*Lorenz Transformation*とかが作られた
    * が、その理由や背景の理論は分かってなかった
* => Einstein: *Galillean Relativity*は*Maxwell Equations*でも成り立つ
  * i.e. *光速度不変の法則*か
  * その理由を示した
* Frameのtransformation
  * 前提として、Linear Transforamtionである必要がある
    * 一度変えて戻したら同じframeに戻る、みたいな
  * $t'=At+Bx;; x'=Ct+Dx$ のもとで、導ける事を考える
    * この式を立てたのはどんな理由がある？
      * x^2に依存するみたいな可能性を排除できたのは何故だろう
    * Gallilean Transformationの条件 $x = v_G t$から、これらが導ける
      * ![Screenshot 2022-12-13 at 10.56.40 AM.png](Screenshot%202022-12-13%20at%2010.56.40%20AM.png)
      * ![Screenshot 2022-12-13 at 10.59.17 AM.png](Screenshot%202022-12-13%20at%2010.59.17%20AM.png)
    * $c$がtransforamtionしても不変という観測事実から、これが導ける
      * ![Screenshot 2022-12-13 at 11.08.22 AM.png](Screenshot%202022-12-13%20at%2011.08.22%20AM.png)
      * Cとcの違いに注意
      * お〜、おもろ
    * 結果、==B, C, DをAによって表すことができる
      * $t' = A(t-\frac{v\_{B}}{c^2}x)$
        * $v_B$ってなんだっけ #疑問
      * $x' = A(t-v\_{G})$
    * その上で、Condition 4: $t'' = t$を考える
      * 変換して、逆変換したら元に戻らんとおかしいというcondition
    * 最終的に、Lorentz Transformationができる
      * ![Screenshot 2022-12-13 at 11.27.58 AM.png](Screenshot%202022-12-13%20at%2011.27.58%20AM.png)
    * ## B: Boost
