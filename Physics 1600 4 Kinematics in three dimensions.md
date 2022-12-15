---
title: Physics 1600 4 Kinematics in three dimensions
---

from *Physics 1600 復習プラン*

* [Physics 1600 4 Kinematics in three dimensions](Physics%201600%204%20Kinematics%20in%20three%20dimensions.md)
  4 Kinematics in three dimensions 95
  4.1 Vectors . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 95
  4.1.1 Basic definitions and notation, inner product . . . . . . 95
  4.1.2 Cross product . . . . . . . . . . . . . . . . . . . . . . . . 99
  4.1.3 Basis vectors . . . . . . . . . . . . . . . . . . . . . . . . . 101
  4.1.4 Vectors in two dimensions . . . . . . . . . . . . . . . . . 104
* V=|V| Vhatと書くことが、polar coordinateの第一歩なのか
* velocityを出す
  * $\dot {\hat V}$が厄介なので、さらにdirectionとmagnitudeに分解する\]
    * magnitude$|\dot {\hat V}|\approx \dot θ$が導ける
    * direction: $\hat k \times \hat V$
      * kの定義は何由来なんだろう?
    * 結果、$\dot{\hat V}=\dot \theta \hat \theta$
* accを出す
  * $\hat {\dot \theta}$が厄介なので、例によってdirectionとmagnitudeに分解して考える
    * mag: $\dot \theta$
    * dir: $\hat k \times \hat \theta = -\hat r$

4.1.5 Vectorderivatives......................105

* $\[\\hat V\]$=1、確かに
* ここの計算、自分で図とか書いて説明できるようにしておきたい
  * $\dot θ( \hat n \times \hat V)$、nもVもunit vectorなのでそのproductもunit vectorというロジックか
  * normalの向きの直感も生やしたい
    4.1.6 Vectorderivatives,reprise .................109
    4.2 Locationsandpositionvectors...................112
    4.3 Velocityandaccelerationvectors .................114
    4.4 Speed,distance,Euclideanmetric.................117
    4.5 Separable systems in Cartesian coordinates . . . . . . . . . . . 119
* 確認: separableじゃない場合とは?<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

  * [https://math.libretexts.org/Courses/Monroe_Community_College/MTH_211_Calculus_II/Chapter_8%3A_Introduction_to_Differential_Equations/8.3%3A_Separable_Differential_Equations](https://math.libretexts.org/Courses/Monroe_Community_College/MTH_211_Calculus_II/Chapter_8%3A_Introduction_to_Differential_Equations/8.3%3A_Separable_Differential_Equations)
  * a_x(x,t)=~~~で、xとtが両方関わる式の場合は解けない?
  * TODO: Recで確認<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    4.6 Motioninaplaneusingpolarcoordinates . . . . . . . . . . . . 121
* $\vec a$の定義
  * $\hat r$の値にΘ成分が入る理由、分かってきた
    * $\hat r(..)$の中身は、rのaccerelationという意味ではなく、r方向のaccerelationの和
    * なので、仮にr=constantだとしたら、円運動を維持するためのaccerelationをかける必要がある
      4.7 CoordinateTransformations ....................126
      4.7.1 Translations .........................126
      4.7.2 Rotations...........................127
