---
title:
 'PHYSUN1601 Physics I： Mechanics and Relativity'
---



[[Physics 1600 復習プラン]]
[[Physics 1600 試験対策]]
受け方
- 式を写しながら話を聞いた方が良さそうだな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - 手書きノートの方が式やgeometryの細部に意識が向いて良さそう
    - 基本kakeruに書くスタイルでやってみるかな

Final Summary
- binomial expansion、逆に忘れてたな
- a=kxの形式のやつ、ぱらめーたの関係を暗記しておきたい
- polar coordinate accerelation
	- $\dot{\dot{r}}=r{\dot{θ}}^2$
- 3DにおけるEnergyのintegrationなど、まだあやしいところあるな
	- line intetgralで良いの?
- separableじゃない3D mechanicsは解けない
- classical turning point
	- E=K+Uで、if E=U(r) then K=0, v=0
		- なるほど〜〜、理解した
- inertial frame、分からん
	- あ〜、別に物理はどんなframeでも成り立つが、同じintertial frameならForceの値が一緒だということか
- Mass Flow
	- Δtを扱ってそれをinfinitesimalにするやつ、復習必要だな
APplication of Energy
- 実際にx=f(t)の式を解かなくても、Forceとvelocityの式からenergyの式を導出すれば動きのイメージが持てるのが嬉しいところ
    - turning pointとかを見れば色々分かるので嬉しい

Energy
- ![image](https://i.kakeru.app/d06320d6871c97db3dea76de48df3f5d.svg)
- forceがfunction of positionの時、↑が成り立つ
    - = あるxにおけるforceが常に同じな状況
    - ex: gravity, SHM, etc
    - a(x) = kxみたいなやつなら該当するね
- TODO
    - energy conservationの導出確認
    - ==conservative force==の意味、確認
    - F=-dU/dxのminus signの意味を確認
    - arbitrarynessを確認
        - それなのにE=mc2が成り立つの、不思議
        - 一応relativityでここの説明はあるらしい

Applying Newtonial Mechanics
- ある状況にapplyする時、constraintがありがち
    - 例えば、机に置かれた物は$y > 机の高さ$という条件がある
    - 例えば、紐に繋がれているボールには紐の長さより遠くに行けないという条件がある
- そして、constraintがある時、それらには絶対assosiated forceがある
    - normal force, centrepetal forceなど
    - Ex: Normal Force:
        - 前提: surfaceがあるとき、$\vec v \cdot \hat n=0$
        - ここから、$\vec a \cdot \hat n=0$, $\vec Σ(F \cdot \hat n)=0$
            - なので、足し合わせて0にならない分を補うのがNormal Forceになる
            - なるほど〜<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - Ex: Tension Force
        - lengthがconstantというconstraintから、二つのTension Forceの存在が導ける
            - $m_{rope}a=\vec F_{T1}+\vec F_{T2}$
            - その上で、ropeがmasslessという仮定から$\vec F_{T1}+\vec F_{T2}=0 \implies |F_{T1}|=|F_{T2}|=T$が導ける
                - あ、ropeがmasslessだから、どんなにropeがaccerelateしていても二つのforceが0と言えるのか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                    - じゃなかったらropeのaccerelationのforceが他に影響してしまう、確かに
    - Ex: sprint
        - [- $\ddot{ x} = -kx$というconstraint?]
        - 違うか、$F_s=-ky$というのは$F_g=-mg$みたいな感じで導入する感じなのね
            - これはconstraint forceではない
            - これをtransformした結果、$ma=-ky$という式が得られる
        - これは、gravity forceがかかっても同じ挙動をするのが導ける
    - Constraint Forceは観察から導き出すものなのね
- 現実的な話として、Constraint ForceはLimitがありがち
    - 紐は切れるし、机も割れる
    - frictionだとこれをexplicitに扱う
- Procedure
    - constrantを書き出す
    - Free-body diagramを描く
    - Newton's second lawで力とaccerelation（=constraint）の関係を書き出す
    - 計算が楽な座標軸を決めて、それぞれの方向に関して整理する
        - この時に、constraint forceを消せるなら消す

Galilean
- Principle of relativity
    - newtons laws holds on all intertial frames (transformed galileanly)
        - あくまでもlawが成り立つだけ
            - F, aの値は一意に定まる
            - けど、velocityのmomentumの値はframeによって異なるよな
            - でもΔvやΔp=Impulseは一定か、だからFやaの値から一意に導けるのね<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - 反例っぽい奴
            - $F=-mbv$ (drag forceがvと関係してしまっている）
            - ただ、これは実は不正確
                - どのframeでも成り立つようにするなら$F=-mb(v-v_0)$（v_0=空気の速度）
                    - 空気がoriginに対して移動しないと仮定した時のみ、F=-mbvと書ける
                - ==どのinterntal frameでも成り立つ式を書くなら、Fと関わるのはΔvであってvではない==
                - なるほど〜〜<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

Impulse
    - ![image](https://i.kakeru.app/f19919fbe3d32406a7254c7be71a98d7.svg)
        - $Δp = I(t)$
        - それはそう、Forceの面積がpの差分


Newton's Law
- 前提として、
    - Inertial Frame: frame where v = constant when there is no interaction with other paticle
        - これは、あるparticleにつき無限にある（garrelian transformationをしてもacc.は変わらないので）
    - Inertial Frameの中でのみNewtons Lawsが成り立つ
        - 今までnewton law 1だと思ってたのは実は成立条件だったのか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - newton's lawがpolar coordinateで成り立たない理由はこれ
- その上で、Forceというstate variableを考える
    - 数学から物理を構築している感じがある<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - $\vec F=m\vec a$
        - Fとaいうstate variableは比例する、constantはmというstate variable
        - ここでのFは、interaction with other particleの合計のnet force?<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
            - ![image](https://gyazo.com/10c6baad004f015b7010ef330056eb4a/thumb/1000)
            - 単純に全4タイプのForceのベクトルの合計取るのは違う、と
                - え〜〜〜〜<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                - relativity考えると厳密にadd upできるのは、electromagnetic forceだけだと
                    - oh<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                - ただ、newtonian physicsであれば、gravitational & electromagneticはadd upできる
                    - 今まではこれをやっていたが、approximationであるのは知るべき<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - Third Law: $F_{21}=-F_{12}$
- これらは現実のobservationから導くhypothesisかな
    - そうみたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- Law 2
    - ![image](https://i.kakeru.app/dc64267cea87b6d8c9eddbba86a1f8cd.svg)
    - F=dp/dt自体は相対論でも成り立つ
        - pの定義が相対論だと変わるので、F=maは成り立たなくなる

Translation
- ![image](https://i.kakeru.app/e06a2bb94191cd1ba95a1de65345fca1.svg)
    - galilean space: 等速でoriginが移動するspace
        - 上の式の通り、そのspaceにおけるaccerelationは変わらない
    - ここで、どのoriginでもtは変わらないと言う前提がある
        - それが崩れるのがspecial relativityの話か、なるほど<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

Plane Polar Coordinates
- x=rcosΘ, y=rsinΘ
- まだnewton lawsの話はしていなくて、positionの記述の話しかしていないから、どんなcoordinateを使おうと何も話は変わらないのか
    - newton lawで、「ものは一定velocityで動き続ける」とか言い出すと、それはcartesianでしか言えなくなるのかな
- 例によって微分して$\vec v$を出したい
    - $\vec v = \dot r\hat r+r\dotθ\hatθ$になる
- これを微分してaを出したい
    - 仮にr=Rでconstantとすると、constant magnitudeのaccerelation（$\hat r$と反対方向）が得られる
        - $\vec a = -Rω^2\hat r$
        - あ、これ知ってるやつじゃん<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - 一般化すると、
        - ![image](https://i.kakeru.app/25705ff8a20f1572c1f661c374437eee.svg)
        - これのそれぞれに直感を持ちたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - 例えば、回転するボールをlet goした時に、accerelationがないのはどう説明できる?

    - ここの一連の流れ、復習して自力で説明できるようになりたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

Vector Accrelation
- 実はaccerelationをanalyticallyに解くことはできない
    - $a_x(x,y,t)とa_y(x,y,t)$があっても、xを出せないということかな
    - $a_x(x,t)とa_y(y,t)$であれば、separableなので解ける
        - まあでも限定的ケース、
        - 逆に言えば、今までxとyに分解して物理できてたのはそういう限定的ケースだったからなのか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - この時は、x=f(t)とy=f(t)が取れるので、うまく変形すればy=f(x)が作れる
            - trajectoryの関数がわかる
    - $a_r(r,θ, t)とa_θ(r,θ, t)$に分けるのはできる?

Metrics
- 実は、三平方の定理で距離が取れるのは特別なケース（この世界）のみ
    - それベースでvectorのdot productも定義されてるので、違う世界ならvector productも違う
- ここの式変形追いきれなかったので復習<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

Curve Distance
- [[APMAE2000 Multivariable]]でやったのと同じ話
    - $ds=|d\vec r|=|\vec v|dt$
    - なので、$s=\int^{t_b}_{t_a}|\vec v|dt$
        - これを $s=⨐^{t_a}_{t_b}ds$、と書く

Poisition
- 原始的な定義として、affine space
    - ただ点が複数ある状態
    - 基準がないのでpositionの足し算はできない
    - ただ、点同士の差分=距離は取れる
- arbitaryなoriginを定義する
    - すると、position vector (positionとoriginの差分)が作れる
    - やっとvectorが得られたので、足し算などが出来る

Plane Normal
Vector Derivatives
- Vectorと、他のある基準vectorのΘの変化
    - Important: 基準次第で値は変わるが、Θの増加は常に左回転を意味する
        - （right handed coordinateにおいて）
- component別に書くやり方(x,y,z)を微分しても、肝心な距離・角度情報がないのでビミョい
    - ので、$\vec v =|v|\hat v$を微分したい
        - $\frac{d}{dt}\vec v=\dot{|v|}\hat v+|v|\dot{\hat v}$
            - これは、directionしか変化しない/magnitudeしか変化しないケースを考えればわかりやすい
                - 一定の方の項は、derivative=0なので消える

        - $\dot{\hat v}$について:
            - $\dot{\hat v}=\dot θ \cdot (\hat n \times \hat v)$
            - unit vectorのderivativeは、unit vectorではない<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                - これは次元考えればそうで、そもそもd/dt unit vectorの単位は1ではなく1/timeになる
                - ![image](https://i.kakeru.app/6817a4562840ad88baa4f40a99a006ee.svg)
            - 結果として、$\hat v$のderivativeは、vとperpendicular = 向きしか変えない
                - 分かりやすい

3.n 3D Kinematics
- Vectorをただの複数の数字の束と捉えるのは良くない
    - あ、そう捉えていた<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - なぜ..?
- 大事な事: starting pointはなく、差分しか表さない
    - それはそう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- 矢印とかは、Vectorのrepresentationの一つ
- $\hat V$は、Vのunit vector $= \frac{V}{|V|}$
    - 大事なのは、これはdimentionless
    - すなわり、$\vec V=|V|\hat V$と表す時、|V|のdimentionは$\vec V$と同じ<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - これちょっと非自明かも
- Cross product
    - $n=v_1 \times v_2$を考える
        - cross productの結果の角度のイメージ、v1からv2の角度が正なら、平面からのnormalの角度も正（つまり前に飛び出てくる）、みたいなイメージを持てばright hand ruleとかいらない
    - $n=\hat v_1 \times \hat v_2$なら、$|n|=\sin\theta$
        - もしΘ=90なら、$n=\hat v_1 \times \hat v_2 = 1$で、また新しいunit vectorが出来る<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
            - xとyのunit vectorのcross productをとると、zのunit vectorが生える

3: 1D Kinematics
- とりあえずxというstate variableの一次元を考える
    - `[x] = length`
- 0の位置とか座標系の選択はarbitaryであって、それによって物理は変わらん
    - そりゃそうだけど、それを数学的に示せるの大事そう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- そこから微分してv, 2回微分してa
    - そりゃそう
    - $f(x)=3x$
    - なので、$x(t)=x(t_0)+\int^t_{t_0}dt'v(t')$だし、$v(t)=v(t_0)+\int^t_{t_0} dt' a(t')$
    - それもそう、基本
    - 高校物理ではintegralの代わりに$x=v(t-t_0)$と書いていた
        - ==しかし、それはvがconstant かつ x(t_0) = 0の時だけ==<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - もしくは$〈v〉=\frac{1}{Δt}\int^t_{t_0}dt'v(t')$とaverage vを定義して、それ$x=〈v〉Δt$とかもいえる
    - なので、definite integralの上限下限とかをちゃんと意識せいというのが言いたそう
        - 確かに結構今まで曖昧に数学でやってたかも
        - 実際first order differencial equationとかで下限雑にやると間違える<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- Drag Accerelation
    - $a =-kv$とか、$a =-g-kv$とすると、vはterminal velocityで収束するという話
        - first order dif eqで解くと、$v=v_0e^{-bt}$になる
    - 復習<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - quadratic dragの話、授業で扱ってないので復習すべき
        - -gがあるときのdrag accerelationの計算
    - 計算すると、初期のvがなんであろうと同じterminal velocityに収束する事が分かる
- 2nd Derivative
    - $a=\frac{d^2x}{dt^2}=f(x)$（f(t)ではない）
    - ここからaをtで表現したい時、右辺をIntegrateはできない
        - tの関数ではないので
    - これは、energy methodを使うと楽にとけるが、それは後でやるらしい
- 2nd Derivativeの特殊ケース$a=+Kx$,$a=-Kx$を考える
- $a=-Kx$
    - 復習<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - 色々式変形をしているのを改めて追う
        - これに合う唯一の式を考えると、x=asin()+bcos()になる
            - 変形すると、simple harmonic motionになる<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
            - SHMを逆から導出していたのか
- $a=+Kx$
    - これはe^xの形になる
        - 実はこれをhyperbolyc sin/cosで表すと-Kxと同じ様な形になる
            - すげ〜<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

20220913
- この授業、内容を自分で自由度高いノートで整理するのが良さそうなのでgoodnotesで書く..?
    - いや、そもそも元のが強いからいいか


20220908

20220906
- 初回前
    - [[ファインマン物理学]]をよんでこい、と

- coordinate transformations and symmetries, approximationあたりを大事にしていそう
- 本質理解大事にしているみたい
- >  While I am very familiar with the complexities of being an
- >  undergraduate in college, I beg you, please do not allow yourself to evolve
- >  into a mode where you are starting and trying to complete reading or problem
- >  sets at the last minute. If you allocate time each day to read and work through
- >  the material in the notes and start the homework before recitations so you
- >  can take maximal advantage of the interaction with the TAs, I have every
- >  confidence that you can succeed in the class. However if you do not dedicate
- >  the required time and attention, no matter how effective I am and/or the TAs
- >  are, it will be difficult for you to succeed.
    - はい...

- 課題
    - Fri -> Next Sunday 9日ある

- 教科書
    - kleppner and kolenkerのやつがある
    - berkeley physicsとmitのもある
    - course notesを一応mainのやつとして扱う
- 計算機
    - 授業/試験ではいらない
    - 宿題でいるかも?

- point particles
    - $N_{DOF}$
    - チョークとかprotonとかはpoint particleではないが、そう仮定することは当然ある
    - electronとかは本当にpoint particle
        - へ〜〜<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

- 物理で扱うquantities
    - physical constant
        - なぜか決まってるやつ
    - state variables
        - 大体物理はこれらの関係を扱う
    - それ以外のやつがstate variableとどう違うのか分からん<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- term
    - coordinate vs position
        - coordinateはvaried、positionは特定の一つ
        - [[coordinate vs position]]
