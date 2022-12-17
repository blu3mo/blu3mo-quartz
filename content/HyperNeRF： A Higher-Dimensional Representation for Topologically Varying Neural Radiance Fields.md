---
title:
 'HyperNeRF： A Higher-Dimensional Representation for Topologically Varying Neural Radiance Fields'
---

#HyperNeRF

- [[未踏Jr]]動画用発表:
    - [[HyperNeRF解説]]
    - [[HyperNeRF解説原稿]]

#SIGGRAPH_Asia_2021
[https://hypernerf.github.io/](https://hypernerf.github.io/)
[https://arxiv.org/pdf/2106.13228.pdf](https://arxiv.org/pdf/2106.13228.pdf)
- [https://www.youtube.com/watch?v=qzgdE_ghkaI](https://www.youtube.com/watch?v=qzgdE_ghkaI)

- [[NeRF]]とかのあたりから勉強する必要が有りそう
    - 発表聞いて気になっていたので、調べる良い機会

- [[未踏Jr]]のYoutube企画で、これを7分くらいに纏めたい
- これを選んだ理由
    - [[高次元]]を扱うよう発想面白〜と思った
        - 空間の[[次元]]と、それ以外の次元を一緒に扱うの、次元に着目して一般化感(?)
        - [[階層高い事を考えたくなりがち]]
    - [[トポロジー]]っぽいの面白そう（よく分かっていないけど）
    - 色々面白そうだけどよく分かっていないので、分かりたい

- [https://hypernerf.github.io/](https://hypernerf.github.io/) で論文の内容がinteractiveにvisualizeされているの、良いな
    - 紙や[[pdf]]ではできないことをやっている感じがあってよい

- [[高速で論文がバリバリ読める落合先生のフォーマット]]の問いとか意識しつつ読みたい

- [DL輪読会 A Higher-Dimensional Representation for Topologically Varying …](https://www.slideshare.net/DeepLearningJP2016/dla-higherdimensional-representation-for-topologically-varying-neural-radiance-fields)

- [https://twitter.com/KeunhongP/status/1436505902387843072](https://twitter.com/KeunhongP/status/1436505902387843072)
    - [[Google Colaboratory]]のデモがある、つよい


以下は論文読んだまとめ
- abstract
    - dynamic scenes（物動いたり）でNeRFやるためのextension的workが色々ある
        - ただ、[[トポロジー]]に変化あるタイプは苦手、と
        - この問題を、NeRFを高次元に引き上げる事で解決した
            - 次元高めちゃえばトポロジーが異なってたやつも
            - それをhyper-spaceと呼ぶ
    - 目指す事（evaluationするtask）

            - これは[[NeRF]]はやってない

            - これは[[NeRF]]もやってる事だな
        - 要はt軸の位置変えても、x/y/z/視点の位置を変えても、元々存在しなかった画像を生成(interpolate)できるようにしたいって事だな
    - そんでもって、この人たちが前やってた[[Nerfies]]よりもerror rate少なくいい感じにできるよ、と
- Intro
    - 現実のものの変化、topological change多いよと
        - ものが割れたりとか
        - 表情の変化（口の開け閉めとか）もよく考えればtopological changeある
    - これはcontinuousな変化ではない（トポロジーが変化するdiscontinuousなタイミングがあるので）
        - なので既存のシーン間interpoalteするアルゴリズムで扱うのが難しかったと
    - この解決策として、[[レベルセット法]]ってのがある
    - このpaperは、ざっくり言えばNeRF x レベルセット法
    - classicalな[[レベルセット法]]との違い
        - classicalなのは次元一つしか増やさないけど、HyperNeRFは何次元でもいけるよと
        - ambient dimensionを増やすっていってる
            - [[ambient space]]ってなんだ?
        - [[トポロジー]]の知識がないのでよくわからんけど、とりあえず[[ユークリッド空間]]に限っていないってのは分かった
        - non-euqlidianなのを[[ニューラルネットワーク]]で表現してるらしい
    - Hyperdimentional NeRFでHyperNeRF
    - [[正則化]]の代わりにoptimization strategy、らしい
        - よくわからん
        - 人の手が少ないって事なのかな..?
- Related Works
    - Non-rigid reconstruction
        - [[マルチレンズ]]とか[[デプスセンサ]]（[[LIDAR]]とか）を使ったのはあるけど、デバイスセットアップ大変
        - ただのレンズ一つの時の既存手法も指摘してるけど、その仕組みを理解してないので問題点も理解できない<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
            - [[HyperNeRF： A Higher-Dimensional Representation for Topologically Varying Neural Radiance Fields#62026b6d79e11300004e3006]]
                - これと同じ話っぽい
            - とりあえず飛ばすか、そのうち理解できたら嬉しい
        - [[Nerfies]]にあったトポロジー変化時の問題を解決したのがHyperNeRF
    - Nerual Rendering
        - ~2019、imageからimageを生成するニューラルネットワークを訓練する研究がいろいろ
            - ただ、いろいろな視点の画像生成したときに整合性取れない問題が
        - その後、NeRFみたいなニューラルネット自体でシーンを表現する物が出てきたと
            - これならgeometricな整合性を保てる
        - NeRFの問題として、物動いてると困る
            - そりゃそう
            - その解決策として、二つのアプローチがある
                - deformation-based
                    - continuousなdeformation fieldで動いている物を表現?
                        - Radiance Fieldと同じように、Deformation Fieldも近似する
                        - NeRDFだな(?)
                    - これにはtopological changeやtransient effects(火など)を表現できない弱点がある
                - modulation-based
                    - latent（潜在）code
                    - あまり仕組みは理解できず
                    - topological changeなどもカバーできる
                - HyperNeRFは、二つの両方を融合したようなアプローチ
                    - deformation fieldでシーンの変化をモデル化する


---
以下はサイト読んだまとめ
- Motivation
    - [[レベルセット法]]という物が元の考え
        - これは、変化する何か（ex: 二次元図形）を、一次元高い物（ex: 三次元立体）のsliceととらえるみたいな?
        - [https://hypernerf.github.io/static/figures/level_set/interpolate2.mp4](https://hypernerf.github.io/static/figures/level_set/interpolate2.mp4)
- Architecture
    - ![image](https://hypernerf.github.io/static/figures/architecture.svg)

