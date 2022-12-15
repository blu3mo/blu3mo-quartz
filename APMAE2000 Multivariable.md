---
title: APMAE2000 Multivariable
---

*APMAE2000 Multivariable 難しい問題メモ*
[Multivariable 試験対策](Multivariable%20%E8%A9%A6%E9%A8%93%E5%AF%BE%E7%AD%96.md)

* Div TheoremとGreens Theoremで計算が違うのがしっくりきていない
  * Greens Theoremのfluxが、Div Theoremのdivなのはなぜ?

![image](https://gyazo.com/c1c837e789ea617b92f96de27dfcb995/thumb/1000)
![image](https://gyazo.com/d54f16b3833036d1e92601c23816da1e/thumb/1000)

* 二つ組み合わさってやっと意味を理解した<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

  * $d\vec  S$と$dS$の違いなど
  * $dA$まで変換して、やっとu, vのdouble integralができる

![image](https://i.kakeru.app/dfcc63ca066d43e01f9127e375a7447f.svg)
![image](https://i.kakeru.app/896eb51061473ab0001ad3b998dbad5d.svg)

* そもそもpartial derivが計算できない時も、smoothではない

* これは、normal vectorが存在するかと同義なのか

* surface area
  
  * tangent vectorらのcross productを取れば、微小量のpallarelogramの面積が得られる
* surface integral
  
  * areaと同じく、normal vectorの長さ(= pallarelogramの面積)を掛ける
  * vector integralの場合は、normal vectorの向きも関わってくる
    * orientable: 表裏を定義できるという感じかな
    * というか3dだとorientableじゃないsurfaceが存在するのか
      * *メビウスの輪*的なやつ
      * この時、vector surface integralは定義できない

greens theorem

* [この動画](https://www.youtube.com/watch?v=8SwKD5_VL5o)で完全に理解
  * curlのdouble integralやったらそれがちょうどline integralになるよねという主張
  
  * もっと分解すると、
    
    ````
      - これ確認したいな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    ````
  
  * curl先教えるべきでは

Conservative Fields

* 常にその位置でのpotential functionの傾きが最大な方向に向いているvector
* なぜconservative?
  * どんなルートでline integarlをとっても値が同じ = energyなどがconserveする、ということかな?
  * 検証は、f_xy=f_yxを使う
  * ここ、物理のところの理解と繋げたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* Fからfを作る計算
  * g(y)は、∂F/∂xを取る時に消える項を見出すため

Line Integral

* Arc Length のintegralする時に、f(r(t))の値もかけてあげれば出来る
  * ==independence of parameterization==は確認、複数選択問題ででそう
  * vector fieldだとしても、r' のunit vector をかけてあげればr'方向の成分を足し合わせられる
* Hw9 2(a) 例えばθが0 to piで、dxでintegrateする時、x'(t)=-sinθをかける
  * ここでnegativeをかける意味は納得いく、x逆方向にintegrateしているので
* F drを F * T dsに変える変換、問題解いて直感得るべき
  * ==TはFではなくrのtangent vector==
* Hw9 Q3は有益なので解くべきだな
  * rをシンプルに保った方が良いとかの知見が得られる
    * いや、でもrangeも0-n以外だと後の計算が大変だわ
    * その辺りの直感が得れるので大事

Vector Field

* まあ自明
* F(vector -> vector)のpotentialはf(vector -> scalar)という理解、大事そう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

Double Integral

* ![image](https://i.kakeru.app/6b9214977508e937d07eb514d5b259c4.svg)
* ![image](https://i.kakeru.app/823efeb083a50b0455a43e1e177f5734.svg)
  * 内側のdyのintegral、xの式はあくまでもyの値

Lagrange Multipliers

* f(x,y)=~~がある時

Topology

* ![image](https://i.kakeru.app/c389117f2385ffab6f2482f740ce2667.svg)
* All points are interior => Open Set
* All boundary points are included -> Closed Set
  * open setと定義の仕方が違う<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* Theorems
  * local extremum of f occurs at an interior point P => P is a critical point
  * Extreme Value Theorem: if set D is closed & bounded, $f:D\to R$and R is continuous, global maximum/minimum exists?
  * TODO: 当たり前な気がするので条件外での反例を探したい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

20221018

* ![image](https://i.kakeru.app/efebebce9b4ae83901169596d1c9b7cd.svg)
* term:
  * maximum: f(x)
    * ==NOT x itself==
  * maximizer: x
* Def: critical point
  * when:
    * case 1. function is not differentiable
      * =𝑓𝑥(𝑥0,𝑦0)or𝑓𝑦(𝑥0,𝑦0) does not exist.
    * case 2. ∇f(x)=0, x is critical point
    * 二つ条件がある
    * 例えばlocal max/minは、critical point
      * ただそれ以外にもある
  * saddle point: not local max/min but ∇f(x)=0
    * inflextion point的なやつ
    * ただ2dのときのパターン以外にもこれはあって、x方向だとmaximumだけどy方向だとminimumみたいな場所も
  * max/min/saddle pointの検証
    * $D=f\_{xx}f\_{yy}-(f\_{xy})^2$というのを使う
    * 条件分岐は分かったが、理由がイメージできない

2022101?

* [https://openstax.org/books/calculus-volume-3/pages/4-6-directional-derivatives-and-the-gradient](https://openstax.org/books/calculus-volume-3/pages/4-6-directional-derivatives-and-the-gradient)

* 授業は飛ばしたが、これを読んでとても直感が生えた

* ∇fは、$f_x(x,y)\hat i+f_y(x,y)\hat j$というベクトル
  
  * このベクトルの向きが、傾きが最大になる方向
* uは、$\cosθ \hat i + \sinθ \hat j$というベクトル

* $∇f\cdot u$は、u方向の傾き
  
  * ある方向で傾き$∇f\cdot u$の値が最大になる = uの方向と∇fの方向が一致する = $∇f\cdot u=|∇f||u|\cos(Φ)$が$Φ=0$で最大になる
  * ==この三つが同じこと==という理解が重要
* ∇f

* 
   > 
   > Theorem 2. The gradient vector ∇f has the following properties:

* 
   > 
   > 1. The gradient is orthogonal to level sets.
  
  * これ、==三次元のf(x,y,z)とかでも成り立つ==という意識大事
    * level set planeのnormal vectorが生える
* 
   > 
   > 2. It points in the direction of greatest change.

* 
   > 
   > 3. Its magnitude is the amount of greatest change.

20221013

* Differential
  * x方向とy方向を足すだけで良いのか、まだ直感がない
* Chain Rule
  * これもx方向をy方向のpartial derivを足す
* Chain Rule with two variables
  * これもそう

20221011

* Differentiability
  
  * f(x)がx=pでdifferentiableか知りたい時:
    * その時、$f(x)-L(x)=E(x)(x-p)$の形に落とし込めるなら、differentiableと言える
      * ここで、$x \to p \implies E(x) \to 0$
      * $L(x)$はlinear function、$a_0x_0+a_1x_1+...+k$みたいな形
    * つまり、日本語で書けば、f(x)をlinear functionで近似して、x→pの時に誤差→0なら、f(x)はdifferentiable
      * x=pで誤差=0と書かないのは、そこの値が存在するか分からないからか
  * これをvectorでやる場合:
    * 基本的に同じノリ、==Tangent Planeを計算して、x→pの値が存在するかを見る==
    * L(x)がtangent plane、なるほど<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    * ==Differentiableか調べる問題解くべき==
  * どんな時にnot differentiable?
    * 普通なら、$(x,y)\to(x_0,y_0)$にしたらpartial derivativeの項はE→0になる
      * ただ、$\lim\_{(x,y)\to(x_0,y_0)}f(x,y)≠f(x_0,y_0)$の時とかはE→0にならないのでnot differentiable
      * これがContinuity of First Partials Implies Differentiabilityか
  * 理解すべきtheorem<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * [https://openstax.org/books/calculus-volume-3/pages/4-4-tangent-planes-and-linear-approximations](https://openstax.org/books/calculus-volume-3/pages/4-4-tangent-planes-and-linear-approximations)
    * Differentiability Implies Continuity
      * これはまあ自明
      * ただ、==逆は真とは限らないのが大事==
        * vectorの場合は、contunuousだけどdifferentiableじゃないケースがある
          * continuousに関しては、一つの方向からのx,y→0,0がx,y=0,0と同じ値であれば良い?
            * ここ確認必要<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
          * ただ、differentiableであるためには全方向からのx,y→0,0がx,y=0,0と同じ値である必要がある
    * Continuity of First Partials Implies Differentiability
* Chain Rule
  
  * 前提として、f(g(x))であれば、gのoutputとfのinputの次元が合っているべき
  * 各変数のpartial derivativeでchain ruleをやって、足せばOK
    * ==Q. なぜ足せばOK?==
    * 証明追いたい
  * [微分演算子](%E5%BE%AE%E5%88%86%E6%BC%94%E7%AE%97%E5%AD%90.md)を使えば簡単にかける
* 応用として、Implicit differentiation
  
  * $F(x,y)$がある時、$y'(x)=-\frac{F_x}{F_y}$

20221004

* tangent planes and linearization
  * tangent plane
    * tangent lineを全方向で出して、そのlineを全て含むplaneを作れば良い
      * 簡単そうに思えるけど、意外とvectorの定義の仕方などトラップあるので問題解かないとまずい
    * そんでもって、それを計算するとシンプルな形のtangent planeの式が得られる
      * よく見れば結構自明なplaneの式
      * 元々の方法でtangent lineを出していたのは本質的にはpartial differentiationだったので、それを計算する
      * こっちを覚えるべきかな
  * linear approximation
    * tangent planeと基本的に同じ
    * tangent planeに別の点をsubstituteすれば近似できる
    * [テイラー展開](%E3%83%86%E3%82%A4%E3%83%A9%E3%83%BC%E5%B1%95%E9%96%8B.md)の高次元版の
      20220929
* partial derv/
  * f_xy=f_yx under certain condition
    * f_xy, f_yx exists and are continuousなら一緒

20220927

* Scalar Fields = 複数変数のfunction
  * domain/image
    * rangeではなくimage
  * ![image](https://openstax.org/apps/archive/20220815.182343/resources/cb4e08360e6224623cfd0a774715855e75ee622c?.png)
  * domainは、関数に√とかあるならその制約を変形して得る
  * rangeは
* 形の理解
  * f(x)=zと置いて、ゴリゴリ式変形をして、z=何かの時にこういう形をすると掴んでいくイメージ
    * 等高線もこれで描ける
    * elispc
* Limit
  * x,yがapproachする方向によってlimitの値が変わることがある
    * 
       > 
       > Check the ”cardinal” directions:
    
    * 
       > 
       > That is, check limx→a f(x,b) and limy→b f(a,y). If they don’t match or either doesn’t
    
    * 
       > 
       > exist, the limit as a whole does not exist.
  
  * ![image](https://gyazo.com/819aeb2cb9d75b29b48b77274fe405f7/thumb/1000)
  * 方法は5つあって、
    * plug-in
      
      * 一番シンプルなやつ
    * cardinal
      
      * これで、そもそもlimitが存在するかをチェックできる
    * other direction
      
      * y=0とかy=xとかy=x^2を代入してみる感じ
      * 無限通りあるので、これを続けたところでlimitが存在することを証明はできない
    * squeezing
      
      * $|2xy|≦x^2+y^2$を知ってないといけない
    * polar
      
      * 忘れがちなこと: 変えたら(x,y)→(0,0)がr→0になる
        * 変数が一つになっているので嬉しい
    * コツ
      
      * 分母≠0にするのが大事、分子は後で良い
  * そもそもlimをちゃんと理解してないな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * $f(x)=x$の時、$\lim\_{x\to0}f(x)=0$になる理由がわからん
      * あ〜、理解
      * x≠0だけど、f(x)≠0ではないのか
        * 定義を見ればわかる

20220922

* arc length
  
  * 線積分ってやつかな?
  * vector integralをする時に毎回長さを取ればいける?
    * $\int^a_b |\vec r(t)|dt$こんな?<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    * 違うか、|r(t)|のベクトルはarc lengthではなく原点からの距離
  * $\int^a_b |\frac{\vec r(t)-\vec r(t+dt)}{dt}|dt$こんな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * そんで、実はこれ中で微分しているので、
    * $\int^a_b |\vec r'(t)|dt$と同値
    * 確かに、r'(t)はtangentだからそれを足していけば良いのか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
  * 計算する時は|r'(t)|を√x^2+y^2の形に展開して積分する
    * 面倒だな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* Arc-Length Parameterization
  
  ````
    - すると、ある距離移動した先の位置がわかる
  ````

* Curvature
  
  * イメージ: positionの二階微分でどのくらい傾きがなめらかに変化するかをみる
  * ただ、注意すべきなのは$κ=|\frac{d}{ds}T(s)|$
    * tではなく、arc-length parametrizationをして得たsがパラメータ
    * Tはunit tangent vector
  * ただこれだとsとか絡んで計算めんどいので、より楽な式がある
    * $κ=|\frac{T'(t)}{r'(t)}|$
  * 円のcurvatureは1/Rであるとかの証明は追うべき<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * ![image](https://i.kakeru.app/94bb22a79157337bab2dd22422a0465e.svg)
    * できた、これ自力で0からできればOKかな
  * あとは、==暗記推奨==と言われていたやつ:
    * Helix: $(acost, asint, bt)$のcurvatureはconstantで$\frac{a}{(a^2+b^2)}$
      * スパイラルのやつか
  * [r(s)の場合も理解大事](https://math.libretexts.org/Bookshelves/Calculus/Supplemental_Modules_(Calculus)/Vector_Calculus/2%3A_Vector-Valued_Functions_and_Motion_in_Space/2.3%3A_Curvature_and_Normal_Vectors_of_a_Curve#:~:text=about%20the%20unit-,tangent,-vector%20when%20the)

ℝ20220920

* vector integral
  * $\int^a_b \vec r(t)dt=(\int^a_b x(t)dt, \int^a_b y(t)dt, \int^a_b z(t)dt)$
    * 結局微分もそれぞれの次元でやったので、積分もそれぞれでやれば良い
* 具体的application: 力学
  * $\vec v(t)=\vec v(t_0)+\int^t\_{t_0}a(t')dt'$
  * $\vec x(t)=\vec x(t_0)+\int^t\_{t_0}v(t')dt'$
  * まあ結局ベクトルになっても各次元で独立に計算するので何も変わらない
    * 今まで二次元の問題を別々に解いていたのと一緒だな

20220915

* Line/PlaneとPoint/Planeなどの距離の計算など
  * これは今までxから垂線おろしたところを計算したりして距離を計算していた
    * けどこれはprojにちかい操作なので、projを使って計算できる
* point $\vec x$とline $l=\vec p+λ\vec v$の距離:
  * $d=(\vec x - \vec p)-proj\_{\vec v}(\vec x-\vec p)$
  * x-pと、それをdirection vectorにprojしたものの差が距離、なるほど<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* point $\vec x$とplane $(\vec r - \vec p)\cdot \vec n= 0$の距離:
  * もっとシンプルで、$comp\_{\vec n}(\vec x-\vec p) = |proj\_{\vec n}(\vec x-\vec p)|$
    * position vectorを差し引いた上でnormalにprojして距離を取ればそれは答え
    * normal vecがposition vecから生えてるので、position vecを差し引く必要がある
* two skewed lineの最短距離
  * line $l=\vec p+λ\vec v, m=\vec q+ω\vec r$
  * とりあえず二つの線のdirectionのnormalを取る
    * $\vec n = \vec v \times\vec r$
  * あとは、normalに$\vec p - \vec q$をprojすれば最短距離が出る
    * ここで、normalに関しては距離情報は意味がないが、p-qは意味があるというイメージ

---

* vector limits and derivatives
  * parametricなcurveについて考える
    * $\vec v = (f(t), g(t), h(t))$
    * （ここでf,g,hがlinear functionならlineになる）
  * 微分すると、
    * $r'(x)=\lim\_{h\to0}\frac{\vec r(x+h)-\vec r(x)}{h}$
    * あくまでもこれはsingle variableな微分で、関数がvectorなだけ
  * ここで、vectorの微分でもchain ruleとかproduct ruleは効く
    * dot productでもcross productでもいける
      * へ〜、なぜ?<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
      * [https://openstax.org/books/calculus-volume-3/pages/3-2-calculus-of-vector-valued-functions](https://openstax.org/books/calculus-volume-3/pages/3-2-calculus-of-vector-valued-functions)
        * 証明はあったが、直感が生えない
  * ここは復習必要<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
  * Unit-tangent vectorを、$\frac{\vec r'(t)}{|r'(t)|}$とする
    * せやな、という定義<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    * スカラーxの微分の場合はyが左辺にあるけど、三次元の場合はx,y両方右にあるから微分するだけでtangentが取れる
    * ![image](https://i.kakeru.app/c24c852febbeabe29819f79cd94d424c.svg)
      * この左右の違いはなんだろう
      * 単純に、左例におけるf(x)が、右例のf(x)のyベクトルに入っているという感じか

20220913

* Lineの定義
  * 知っている話
  * 二つのlineがparallelかどうかを考えるときに、色々考え方はある
    * $\vec a = \lambda \vec b$かどうかとか
    * $|\vec a \cdot \vec b|=|\vec a||\vec b|$かどうかとか（a, bはdirectional vector）
      * これは$\vec a = \lambda \vec b$と同じ..?
    * 二つの交点があるかとか
* Planes
  * 知っている話
  * normal vectorと(position vector - x)のdot productが0になるxの集合

---

* proj/comp
  
  * とりあえず理解した、また忘れても↓あたりを読めばすぐ理解できそう
    * [https://web.ma.utexas.edu/users/m408m/Display12-3-4.shtml](https://web.ma.utexas.edu/users/m408m/Display12-3-4.shtml)
  * $proj_xa$の時、xは方向情報にしか意味はない（距離情報はどうでも良い）という意識が大事そう
    * 意味を考えてもそうだし、計算をみてもdistanceで割られるので距離情報が消える
* dot/cross product
  
  * 大体はまあ既知
  
  * 可換か, 線型かなどは異なるので注意
    
    * ![image](https://gyazo.com/889e29972b25f0d6df31047e82f4c014/thumb/1000)
  * $|\vec a\times \vec b|$でaとbでできたparallelogramの面積が得られたり、Parallelepipedの面積もその延長で得られたり

---

* 教科書、どっちかで良い

* hw, completion + correctness

* multivariableのcalcをやるよ、と
  
  * 名前のまま
* locus
  
  * 式で定められるset of points
* vector
  
  * これは二つの座標の差分しか持たない（どこが始点終点かは分からない）
  * magnitude: $|\vec V|=\sqrt {{v_1}^2+{v_2}^2+{v_3}^2}$
  * linear combination たぶん*線型結合*
    * $a\vec v + b\vec v$
    * これを定義するのにscalar multiplication, vector additionが必要（定義は自明）
* 感想
  
  * 今後がむずそうではあるが、*数理科学基礎*ほどではなさそう
