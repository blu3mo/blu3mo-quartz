---
title:
 'Physics 1600 試験対策'
---


end term
- 7.5とか自習必要そう

- office hour
    - 聞きたいこと
        - newton laws does not work when mass change
        - kinetic energy when galilean transformation

- practice final
	- logのintegrationのlimit注意
	- F=-dU/dxとtaylor expansionで得られるharmonic motion、でそう
	- dm/dtがrateであって、Δmはrateではないの、注意
	- momentum of inertiaって書いてあっても避けない、neglibibleかも

- pset 10 5:35-
    - q1
        - COM frameから考えるの大事
        - external forceがない
    - q2 なぜvがconstantならどちらもinternal frameなのかを考えるの大事
        - external forceはあるが、そもそもground frameのgallilean transformationなので問題ないということか
        - この場合では、ΔKの値はframe変えると変わるが、それは移動距離も変わってwork doneが変わっているから
            - もっと根本的な原因としては、car frameだと元々なかったexternal forceが生まれているのか
            - そこの変換してあげれば辻褄はあう
        - あとはdの例もなぜintertialなのか
            - こっちは、external forceがないのでCOMを考えればintertial
            - この場合では、ΔKの値はframe変えても同じなので辻褄があう
    - q3
        - p=p0の時に、massで割る式がareaで割る式に置き換えられる式変形、大事
            - p0が分子分母両方のintegralにあるので、constantとして取り出して消せる
            - ここ忘れていると本番混乱しそう
    - q4
        - めちゃくちゃ教育的問題
        - case 1
            - ここではForceは考えずに、accerelationのみを考える
                - Forceはaccに辻褄が合うように色々な方向に働くイメージ?
            - ここで、velocity change = accerelationはr hat方向しかない
                - ので、angular momentumがconservedと言える
                    - これは、angular velocityがconservedであることと同義
        - case 2
            - いや、やっぱ分からんな
                - only radial acc = only radial force = 0 torque = radial momentum conservedでは
                    - 違う、一つ目が偽だ
                    - polar coordinateのaccは複雑なので

midterm 2
- grav acc: $\frac{-GMm}{mr^2}=\frac{-GM}{r^2}$
    - mが打ち消し合うのでmassによって変わらない
- electrostatic acc: $\frac{-GQq}{mr^2}$
    - mが打ち消し合わないのでmとqにdependent!

- pset 6、良い問題が多いので復讐すべき
    - q4, polarだとaccerelationのr projectionとr dot dotは一致しないとか
    - q5, dot Θはspeedにならない
        - これ危ない
- pset 7 知見
    - vとベクトル方向違うとenergyに加算されないの、ちゃんと直感得たい
- pset 8 知見
    - ω = v/R
    - 関係をちゃんと把握したい、W=KではなくW=ΔKとか

- やること
    - notes読む
    - mock解く
- 暗記
    - polar acc. 絶対
    - √g/lとかを覚えておきたい
- 考えること
    - line integralの所、分からないまま
    - forceがF(x)でなくてもconserveするのなぜ？

midterm 1
- やること
    - [[Physics 1600 復習プラン]]で読み返す
        - 色々な式変形とその結果を理解して、何もみずに説明できるのを目指したい
        - 自力で説明したいこと
            - SHMみたいなやつ、positiveとnegative
            - cartesianとpolarでvelocityとaccerelationを導出
    - 過去問が出るらしいので解く
        - [https://drive.google.com/file/d/0B8i-tU4xFJ25Ul9tam5oQ3R5a3c/view?resourcekey=0-HxPMIBfo23DF0YqbbELMHg](https://drive.google.com/file/d/0B8i-tU4xFJ25Ul9tam5oQ3R5a3c/view?resourcekey=0-HxPMIBfo23DF0YqbbELMHg)
            - 1.22確認したい
    - 過去のpsetを見直す
        - 多分これが一番効果ある気がする
        - pset 3,4は解けなかったやつあるので再確認
    - 20221012
        - -1100 Polar Coordinateやる
        - -1200 その他見直し
        - 洗濯物取り込み
        - pset見直し・あらためてとく
    - 余裕あれば
        - 4.1.6議論読む
- コツだなと思ったこと
    - 当たり前ではあるが、グラフを想像するのと次元を確認するのは大事<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - ミスに気付ける
