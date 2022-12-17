---
title:
 'HyperNeRF解説'
---

HyperNeRF
- > HyperNeRF: A Higher-Dimensional Representation for Topologically Varying Neural Radiance Fields
- > (Park et al., 2021)
- SIGGRAPH Asia Technical Papers


✨ HyperNeRFで出来る事
- [https://www.youtube.com/watch?v=qzgdE_ghkaI](https://www.youtube.com/watch?v=qzgdE_ghkaI)
- [https://hypernerf.github.io/static/images/teaser.mp4](https://hypernerf.github.io/static/images/teaser.mp4)
    - 視点が動いている動画から、立体モデルを構築

🎥 そもそも「NeRF」とは
- > Representing Scenes as Neural Radiance Fields for View Synthesis
- >  (Mildenhall et al., 2020)
- [https://www.youtube.com/watch?time_continue=92&v=JuH79E8rdKc&feature=emb_logo](https://www.youtube.com/watch?time_continue=92&v=JuH79E8rdKc&feature=emb_logo)
    - 目標: 複数の視点の画像から、新たな視点の画像を生成
    - NeRF以前の考え方:
        - 画像を出力するニューラルネットワークを訓練
        - ❎ 様々な視点から生成させる画像の一貫性にかける
    - NeRF:
        - 画像ではなく、==任意の空間座標の色と密度(透明度)==を出力するニューラルネットワークを訓練
            - 訓練データ: 様々な視点からの画像
            - 入力: 座標x, y, z, 視線角度θ, φ
            - 出力: 色R, G, B, 密度(透明度)σ
            - ![image](https://gyazo.com/47240adc6f3398fccb998cd00cf24a9a/thumb/1000)
        - Radiance Field: 「色と密度」の集合
            - 「色と密度」の集合をニューラルネットワークで近似
            - -> Neural Radiance Field
            - -> NeRF
    - Q. 「色と密度」を元にどう画像を生成する?
        - A. 視点に入る==光の動きをシミュレーション==する (ボリュームレンダリング)
            - 光が通る道の座標それぞれの色を重ねていく
            - 密度(透明度)が高い所を光が通ったら、光を減衰させる
        - ![image](https://gyazo.com/5c211716b78b5f21e68fa88e5ddb10b7/thumb/1000)
            - [https://blog.albert2005.co.jp/2020/05/08/nerf/](https://blog.albert2005.co.jp/2020/05/08/nerf/)
            - 微分可能な関数なので、ニューラルネットワークによって表現可能

📕 NeRFの後
    - ![image](https://gyazo.com/7503646fd373f41d61353cd4883fa686/thumb/1000)
    - ![image](https://gyazo.com/8be4cd63472cd4dc8e432f0d940afbb5/thumb/1000)
- 形状変化のある物体でもNeRFの実現を目指す研究
    - [https://www.youtube.com/watch?v=MrKrnHhk8IA](https://www.youtube.com/watch?v=MrKrnHhk8IA)
    - [https://www.youtube.com/watch?v=lSgzmgi2JPw](https://www.youtube.com/watch?v=lSgzmgi2JPw)
    - ❎ トポロジー変化を含む形状変化が苦手
        - i.e. 連続的では無い変化の表現が難しい
        - 例:「口の開け閉め」「紙を半分に破る」「両手で拍手する」
            - 「口が閉まる瞬間」「紙が分裂する瞬間」「手が触れる瞬間」に非連続的な変化が起きる
        - [https://hypernerf.github.io/static/images/teaser.mp4](https://hypernerf.github.io/static/images/teaser.mp4)

⭐️ HyperNeRF
- 考え方：非連続的な形状変化も、より高次元には連続的形状変化として捉えられる
    - 非連続な形状変化：
        - ![image](https://gyazo.com/f831344f572272d6bc8ab9bbc4af44c9/thumb/1000)
    - 高次元には連続的形状変化：
        - [https://hypernerf.github.io/static/figures/level_set/interpolate2.mp4](https://hypernerf.github.io/static/figures/level_set/interpolate2.mp4)
        - [https://hypernerf.github.io/](https://hypernerf.github.io/)
- NeRFとの違い:
    - 入力: 座標x, y, z, 視線角度θ, φ, ==高次元座標W1, W2 ==
    - 出力: 色R, G, B, 密度(透明度)σ
    - ![image](https://gyazo.com/f6804e02cea8475abb2bcbd0223756f3/thumb/1000)
        - [https://hypernerf.github.io/](https://hypernerf.github.io/)
- ![image](https://hypernerf.github.io/static/figures/architecture.svg)
    - [https://hypernerf.github.io/](https://hypernerf.github.io/)

🔬 評価
- Task 1: 新たな視点の画像生成（未知の座標x, y, z, 視線角度θ, φ）
- Task 2: 新たな形状の画像生成（未知の高次元座標W1, W2）
    - ![image](https://gyazo.com/43d7f67d15c602524a5a261cc35e2fc6/thumb/1000)
    - [https://www.youtube.com/watch?v=qzgdE_ghkaI](https://www.youtube.com/watch?v=qzgdE_ghkaI)


📖 まとめ
    - 視点・形状変化のある動画を元に、新たな視点・形状の画像を生成
    - 何がすごい?
        - 動画中で形状が変化していても、綺麗にレンダリング出来ている
        - 形状のトポロジーが変化していても、問題なくレンダリング出来ている

- 参考文献
    - Deep Learning JP. DL輪読会Data2vec: A General Framework for  Self-Supervised Learning In…. 4 Feb. 2022, www.slideshare.net/DeepLearningJP2016/dldata2vec-a-general-framework-for-selfsupervised-learning-in-speech-vision-and-language-251106954?next_slideshow=251106954. Accessed 13 Feb. 2022.
    - Mildenhall, Ben, et al. “Representing Scenes as Neural Radiance Fields for View Synthesis.” Communications of the ACM, vol. 65, no. 1, Jan. 2022, pp. 99–106, 10.1145/3503250. Accessed 13 Feb. 2022.
    - Park, Keunhong, et al. “HyperNeRF: A Higher-Dimensional Representation for Topologically Varying Neural Radiance Fields.” ACM Transactions on Graphics, vol. 40, no. 6, Dec. 2021, pp. 1–12, 10.1145/3478513.3480487. Accessed 13 Feb. 2022.
    - 山内. “三次元空間のニューラルな表現とNeRF.” ALBERT Official Blog, 8 May 2020, blog.albert2005.co.jp/2020/05/08/nerf/. Accessed 13 Feb. 2022.
