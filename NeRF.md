---
title: NeRF
---

* *HyperNeRF: A Higher-Dimensional Representation for Topologically Varying Neural Radiance Fields*の理解のために調べる

* [解説スライド NeRF: Representing Scenes as Neural Radiance Fields for View…](https://www.slideshare.net/KentoDoi/nerf-representing-scenes-as-neural-radiance-fields-for-view-synthesis-230911610)
  
  * 解説
* [三次元空間のニューラルな表現とNeRF | ALBERT Official Blog](https://blog.albert2005.co.jp/2020/05/08/nerf/)
  
  * 解説
  * 関連技術の系譜とか、前提知識（カメラの数学的モデルとか）含めて説明していて良い
    * [HyperNeRF解説](HyperNeRF%E8%A7%A3%E8%AA%AC.md)もこんな感じの目指したい
  * Radiance Field
    * これは、volume densityとemitted radianceが空間の各座標に紐づいた場、みたいなことかな
    * これをニューラルネット訓練してうまいこと近似する、と捉えられる
  * ![image](https://gyazo.com/89f03db8a338318f2f128394e58717bb/thumb/1000)
    * t_n(nearest)とt_f(farest)の間で、色(c)と密度(σ)を積分する
      * そのときに、位置t_n(nearest)から位置nの密度の分色と密度を減衰させたいので、T(t)を掛ける
    * これを離散化したやつは、*誤差逆伝搬*できるオペレーターで表現できるので、ニューラルネットワークが訓練できる
      * \#区分求積法
  * 細かい工夫
    * coarseとfineなrenderingを分ける工夫
      * tの分割が粗いレンダリングをまずやる
      * その上で物体がありげなところにてfine renderingする
      * 二つは別のニューラルネットワークを訓練してrenderする
    * positional encoding
      * 
         > 
         > 各点の色・密度 {\bf c}, \sigmac,σ は {\bf x, d}x,d の微細な変化に対してめまぐるしく変化するわけですが、実はニューラルネットワークはこの手の高周波な関数の近似が苦手なのです。
        
        * これはまあなんとなくわかる
        * ぐわんぐわんしてるグラフは近似大変そう
      * 
         > 
         > そこで本論文では著者らが positional encoding と呼んでいる手法を使って {\bf x, d}x,d を高次元の空間に埋め込んでいます。この埋め込み表現が高周波であれば、ニューラルネットワーク自体は低周波な関数を近似するだけでよい、というのがみそです。
        
        * うーん?
        * ![image](https://gyazo.com/dcb9f85f7b02bb7149685e1ee24ed00f/thumb/1000)
        * 2/3次元ベクトルx, dの次元を高める代わりに、次元一つ一つの周波数は下げる、という感じかな
        * phaseが異なるたくさんのsin/cos関数にpを突っ込めば、数(次元数)のおかげで十分な情報量を持てる、みたいな感じ?
          * [Transformer](Transformer.md)の技術なのね
          * まともな基礎を持たずに無理に読んでるとこういうところが厳しい
        * [解説スライド NeRF: Representing Scenes as Neural Radiance Fields for View…](https://www.slideshare.net/KentoDoi/nerf-representing-scenes-as-neural-radiance-fields-for-view-synthesis-230911610)
          * 高周波成分も学習してもらうための変換らしい
          * まあ高次元にマッピングしたら元々学習されづらかった物も学習される、ってのは納得は行く
        * やっていることの気持ちは理解できた気がする
    * 実験
      * positional encodingのLとか、*区分求積法*の分割の細かさとか、いろいろなパラメータを弄って計算量とか質がどう変わるかを実験してる
        * なるほど、nn系の研究ってこういうことするのね
* アブスト
  
  * 
     > 
     > Because volume rendering is naturally differentiable, the only input required to optimize our representation is a set of images with known camera poses.
    
    * *ボリュームレンダリング*が*微分可能*ってのが大事
      * レンダリング後に出力された画像と、教師データの画像を比べた上で、*誤差逆伝搬*できるので
      * その最適化をうまいことやる方法を見つけたよ、という研究?
* [https://www.matthewtancik.com/nerf](https://www.matthewtancik.com/nerf)
  
  * 
     > 
     > Our algorithm represents a scene using a fully-connected (non-convolutional) deep network, whose input is a single continuous 5D coordinate (spatial location (x, y, z) and viewing direction (θ, φ)) and whose output is the volume density and view-dependent emitted radiance at that spatial location.
    
    * input
      * 3d座標
      * 視点の角度
        * 視点で色とか明るさ変わるもの（鏡面とか）もいけるよってことか
    * output
      * volume density: これは*ボリュームレンダリング*でいうボクセルの透明度ということかな?
      * emitted radiance: 放射輝度、ある方向における明るさみたいな
* 一般向け記事
  
  * [VRで注目、新技術「NeRF」の衝撃 様々な視点の画像を美しく合成：日経クロストレンド](https://xtrend.nikkei.com/atcl/contents/technology/00007/00026/)
  
  * 
     > 
     > 具体的には、ある3次元点の位置（x,y,z）と視線方向（θ,Φ）を入力すると、その点の輝度と不透明度を出力するニューラルネットワークである（図2 （a）、（b）参照）。例えば、学習済みのNeRFに物体表面の座標と視線方向を入力するとその位置に対応した輝度と不透明度を出力する。また、物体の存在しない空気中の点の座標と視線方向を入力すると、その位置が無色かつ透明であるという情報を出力する。このように、輝度と不透明度を考慮した「場」を用いて画像を合成するというのがNeRFの基本的なアイデアであり、独創的な点である。
  
  * 
     > 
     > 複数の視点の画像から、新たな視点の画像を合成して作り出す「Novel View Synthesis」というタスクがある。VRやスポーツの自由視点映像などには不可欠な技術だ。
  
  * 
     > 
     > 　このNovel View Synthesisで驚異的な性能を達成したのが、本記事で紹介する「NeRF」という手法である。NeRFは合成する画像の圧倒的な美しさもさることながら、アルゴリズムもこれまでの研究とは全く異なる独創的なものになっており、非常に見どころの多い研究である。本記事ではその面白さを少しでも伝えることができればうれしい限りである。
  
  * 要は、
    
    * 一つの[ニューラルネットワーク](%E3%83%8B%E3%83%A5%E3%83%BC%E3%83%A9%E3%83%AB%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF.md)で一つのシーンを表現する
    * そのNNは、inputで位置と視線方向をとって、outputで輝度と不透明度を出す
      * その情報が学習できれば、あとは古典的*ボリュームレンダリング*で画像が生成できる
* 動画
  
  * [https://www.youtube.com/watch?v=JuH79E8rdKc&t=4s](https://www.youtube.com/watch?v=JuH79E8rdKc&t=4s)
  * すごいよく作られた映像だなw
    * 既存手法との研究とか丁寧に違いを示している
  * というかすげえな
  * 反射もちゃんとrenderされている
  * ガラスによる光のゆがみも
