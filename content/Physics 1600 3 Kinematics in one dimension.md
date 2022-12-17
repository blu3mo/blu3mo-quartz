---
title:
 'Physics 1600 3 Kinematics in one dimension'
---

from [[Physics 1600 復習プラン]]
[[Physics 1600 3 Kinematics in one dimension]]
- 3.1 Foundations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 69
- $x(t)=x(t_0)+\int^t_{t_0}dt'v(t')$だし、$v(t)=v(t_0)+\int^t_{t_0} dt' a(t')$
        - それはそう、基本
        - 高校物理ではintegralの代わりに$x=v(t-t_0)$と書いていた
            - ==しかし、それはvがconstant かつ x(t_0) = 0の時だけ==<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
            - もしくは$〈v〉=\frac{1}{Δt}\int^t_{t_0}dt'v(t')$とaverage vを定義して、それ$x=〈v〉Δt$とかもいえる
        - なので、definite integralの上限下限とかをちゃんと意識せいというのが言いたそう
            - 確かに結構今まで曖昧に数学でやってたかも
            - 実際first order differencial equationとかで下限雑にやると間違える<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- 3.2 One-dimensional kinematics: examples . . . . . . . . . . . . . . 71
- 3.2.1 Constant acceleration . . . . . . . . . . . . . . . . . . . . 71
    - $y=y_0+v_0t-\frac{1}{2}gt^2$
        - ==Integrationの結果としてこれがある==という意識、大事そう
- 3.2.2 Oscillating acceleration . . . . . . . . . . . . . . . . . . . 73
- 3.2.3 Drag acceleration (linear) . . . . . . . . . . . . . . . . . 75
    - $a=-g-bv$とかの時、a=0になるvがある → terminal velocityがある、と理解できる<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- 3.2.4 Drag acceleration (squared) . . . . . . . . . . . . . . . . 78
- 3.2.5 Instantaneous changes in velocity . . . . . . . . . . . . . 82
- 3.3 Second-order differential equations of motion . . . . . . . . . . 85
    - a = f(x)の形式のやつを解きたいが、基本無理
        - Energy methodってのはあるらしいが
        - なので、決めうちで試して式を得るしかない
            - $a=±kx$の形式のやつなら出来る
- 3.3.1 Negative form, simple harmonic motion . . . . . . . . . 86
    - initial displacement/velocityが0の時のみSHMになる
- 3.3.2 Positive form . . . . . . . . . . . . . . . . . . . . . . . . . 89
- 3.3.3 Uniqueness of solutions to linear second-order equation of motion . . . . . . . . . . . . . . . . . . . . . . . . . . . 91
- 3.3.4 Non-homogeneous linear second-order equation of motion 92
