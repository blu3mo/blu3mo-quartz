---
title:
 'Decartography'
---

[/tkgshn-private/DeCartography Whitepaper](https://scrapbox.io/tkgshn-private/DeCartography Whitepaper)を読んで思ったこと
- 仕組みの話について:
    - ソーシャルグラフ構築の話も、分散型オラクルの仕組みもおもろい
        - ただ、その二つをくっつけるのには若干疑問を感じた
            - というかこれは分散型オラクルではないのか
            - 分散型オラクルの方向性として、（いわゆる平凡な意味での）[[Social Distance]]みたいなものは存在すると思う<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
            - わかりやすくソーシャルグラフとしているが、どんなものを提供するのがいいのかわからない<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
        - Q. タグ付けの手段として、人力は最適?
            - 感想として、まあなんかちゃんと仕組み作ればそれなりにうまく行く気はするが、エレガントではないなと思ってしまった<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
            - あくまでもラベル付け ≒ データの圧縮がしたいなら、もう少し機械的にする方法もありそうな気がした
                - [[pol.is]]みたいなアプローチ?
                    - 記述ということ？<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>記述方法を自然言語にして、ベクトルで測るみたいなこと？（実際pol.isは同じ言語上でしか動かなかったりしたはず）
                    - あーでも自然言語で書かれたやつに対して、人が投票するんだっけな<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                        - ↑「記述」で指しているものがよくわからない<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                    - 詳しく<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                        - ここで言いたかった違和感は、すぐ下の「思った課題」でより具体的にかけた気がするのでそっち参照<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                            - 「人に自然言語のタグを選ばせる」作業がとても言語に依存しているから、情報が削減されたり恣意性が生まれたりしてよくないよな〜みたいな気持ち
                            - 完全に同意、これは参考にさせてもらいます！ありがとう<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
            - 思った課題
                - 人力タグ選択の課題の一つとして、人間が言葉（=タグ）として解釈できる粒度まで情報量が落とされてしまう問題がありそう
                    - 「Public Goods」のタグをつけてもらう場合、その中の違いは全部削ぎ落とされてしまう
                    - むずいよな、どうするのがいいんやろ<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                    - そもそも[[クラスタリング]]というのは情報量を落とす行為だから、ここでは人間の言葉に依存するというのが良くないということだよね<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                        - そう、言語のラベル付けに依存しない方法ならクラスタリングせずにすむ手段もありそう
                - あと、選択肢のタグの設定が恣意的な問題もありそう
                    - 例えば特定のタグを選択肢から排除することで、DeCartographyでそこのpluralityを判定できないようにするみたいな不正が容易にできる
                    - 上の問題と被るけど、一般的にクラスタリングは[[教師なし学習]]でやることが多いと思っていて、[[k-means]]とか使えば良さそう？<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                        - [https://ja.wikipedia.org/wiki/データ%E3%83%BBクラスタリング](https://ja.wikipedia.org/wiki/データ%E3%83%BBクラスタリング) <img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                        - > クラスタリング（英: clustering）、クラスタ解析（クラスタかいせき）、クラスター分析（クラスターぶんせき）は、データ解析手法（特に多変量解析手法）の一種。教師なしデータ分類手法、つまり与えられたデータを外的基準なしに自動的に分類する手法。また、そのアルゴリズム。
                        - 目的はアドレス間の多様性の評価なので、そもそもクラスタリングをする必要はなさそう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                        - それはそう<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                            - それでいうと、アドレスはクラスタリングされるという暗黙の前提に基づいてるのは危険かもしれない<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
            - 他の手段として思いついたもの
                - 例えば、「二つのアドレスはどの程度似ているか」みたいな質問に群衆に答えてもらって、それを高次元空間にプロットして距離判定、みたいな手段もある気がする?
                    - この場合、言葉の粒度まで情報量が落とされてしまう問題が解決できる
                    - あと、用意するタグの恣意性が入り込まないのでより良い
                    - （[[pol.is]]に近い）
                    - なるほどねぇ、それはあるかも。何回も繰り返せばいわゆる2次元以上の空間にできるイメージ？<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                    - 「二つのアドレスはどの程度似ているか」というのはやはり人間の恣意的な部分が入ってくるから、完全に機械だけで判定するべきかなぁと思った<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                        - [[恣意的]]と[[民主主義]]（的な概念）に対してどんな感覚なのか気になる<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                            - なんかまぁ別という感じか、オラクルに関してはどっちなんだろう。
                        - ようはこれって、人間の言葉で表せられるベクトル空間にマッピングしているということになりそう？<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                        - 機械で目的を達成できるならそれで良いと思うが、「投票における"良い"多様性」を判定するには人間世界の情報がないとできないような気がした（直感）<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                            - なので人間あるいは自然言語モデルとかを使う手段になる?
                            - 人間の自然言語モデルを使うのめっちゃ良いな<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                                - ただ自然言語モデルはそれこそモデルの選択が恣意的なので、それよりは群衆を使う方が良い気はする?<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                                    - 「二つのアドレスはどの程度似ているか」という質問をするよりも、群衆が作った自然言語モデルを使った方が恣意的な部分は減りそうな気がした（直観）<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                                        - ここの論点一般化して「恣意性を排除した自然言語モデルの作り方」、分散システムの方法論（詳しくは知らん）が応用出来そうでおもろそう
                                            - [/tkgshn-private/分散型オラクルは大規模自然言語モデルで代用できる?](https://scrapbox.io/tkgshn-private/分散型オラクルは大規模自然言語モデルで代用できる?)
                                            - +100<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                                    - あと「投票における"良い"多様性」とは？をもっと追求したい<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                                        - それはそう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>x100
                                            - 下に書いた、[[Decartography#636b156f79e1130000b1e256]]
                                        - 本当にそれは良いのか？<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                                - まぁそれに[[メタ]]なんだけど: [/tkgshn-private/DeCartography Whitepaper#6369fb4009c5f20000fd83e1](https://scrapbox.io/tkgshn-private/DeCartography Whitepaper#6369fb4009c5f20000fd83e1)<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
    - Q. そもそもタグ付け情報は何に使う?
        - 「タグが異なる2人の投票の方が、タグが同じ2人の投票より価値ある」とする、ということかな
            - そういうことです<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
        - じゃあソーシャルグラフとは関係ない話?
            - ①ソーシャルグラフによる社会的距離情報 + ②タグ付け情報 で、アドレスの多様性を判定するみたいな感じかな?
- もっと思想的な部分について:
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>の理解:
        - 前提として、[/tkgshn-private/50 actually independent thinkers are worth more than 1000 NPCs who all consume the same media and vote the same way](https://scrapbox.io/tkgshn-private/50 actually independent thinkers are worth more than 1000 NPCs who all consume the same media and vote the same way)の[[vitalik]]的思想
        - それを根拠に、「タグが異なったりソーシャルグラフで遠い2人の投票が、近い2人の投票より重要」という主張をしている
    - まあなんかそう言われればそうかも？という気持ち
    - ただ
        - [/tkgshn-private/50 actually independent thinkers are worth more than 1000 NPCs who all consume the same media and vote the same way](https://scrapbox.io/tkgshn-private/50 actually independent thinkers are worth more than 1000 NPCs who all consume the same media and vote the same way)の根拠の詳細が知りたい
            - 自分は追えていないが、vitalik周辺の人々が色々議論していてstableな土台があるんだろうなと予想
            - この主張/思想の土台、referenceがあるなら知りたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                - 「多様が良いという思想は前提なので、その前提に関しての疑問はそっちを参照してね」というやつ
                - 例えばvitalik（誰でも良いけど）がこの主張の根拠を長文でかいてたりするなら、それがreferされてると良いなと思った<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                    - <img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>それは、結構むずくて[[Ethereum財団]]とかまず見るのがいいのかな？
                        - [https://www.neweconomy.jp/features/audible/164207](https://www.neweconomy.jp/features/audible/164207)
                - クリプトのここ二、三に関しては
                    - NFTサマー（2020）
                    - DeFiサマー（2021）がきた後に若干落ち込んでる
                    - 今まで[[DAO]]とか作られてきたけど、思想面が全く非中央集権になってなかった（組織構造とかも含めて）
                        - そこで、プロジェクトトークンがエクイティ（をただ、トークンにしたもの）みたいなところがあって、「これは単なる証券化では」みたいなのもあった
                        - そこで、どんどん多様化してきて、やっと「もっと人間的にちゃんとしてるっぽいやつの方が良くね？みたいな
                            - 戻ってきた感
                            - [/tkgshn-private/ソーシャルグラフやSoulboundトークンをベースに多次元ID（plural id）を構築し、Quadratic Fundingの脅威である"結託"を防ぐ](https://scrapbox.io/tkgshn-private/ソーシャルグラフやSoulboundトークンをベースに多次元ID（plural id）を構築し、Quadratic Fundingの脅威である"結託"を防ぐ)

            - 何となくそんな気はするが、とても曖昧な主張に感じる
                - 全然ない、やってみないとわからん。だからもっといろんな人からつっこまれたい<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                - やってみてどうだったら、それが良いと言えるのかが知りたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                    - （評価方法が定まってないなら実験をする意味がないので）
                    - 究極、[[人力オラクル]]として「今までは[/tkgshn-private/SAD](https://scrapbox.io/tkgshn-private/SAD)としてQuadratic Fundingに対する[[談合]]を検知する費用も時間がかかっていたものが、この仕組みで早く・安くできるかみたいな<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                        - [/tkgshn-private/Gitcoinがシビル攻撃を防ぐために掛けている費用感](https://scrapbox.io/tkgshn-private/Gitcoinがシビル攻撃を防ぐために掛けている費用感)
                    - あ、Decartographyの目的は[[シビル攻撃]]の防止だった?<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                    - いや、そこからだとユースケースが強そうかなという感じ。実際にGitcoinのチームも興味持ってもらってるなら、すぐに検証できるところでやれた方がいいかなと<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                    - シビル攻撃①談合防止の用途と、②多様な投票を良いとしたい用途は多分別の話だと思うので、後者の評価方法もあるなら知りたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                        - 例えば、つながりのない2人が同じ投票をしたとして、
                            - ①談合防止の目的の場合: 別に良い
                            - ②多様な投票良いとする場合: 同じメディア見たNPCだろうから重み付け下げたい
                            - という理解<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                                - そうだよね〜それは分かるんだけど、まぁなんか疑問とかわからんことあるけどやってみないとわからんくね？というのが一貫した感想かな。むしろどうしたらいいと思ったりしてるのかを知りたい<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                                    - 「やってみないとわからん」は同意、ただやってみて結果が出た後に（特に②の論点に関して）それをどう評価するのかが気になった<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                                        - （例えば学会でAIモデルの研究を発表するなら、モデルを評価するところも含めて論文に書く）
                                        - crpytoの世界だと、結果をフォーラムとかに公開して評価は他の人に任せる、みたいな方法論だったりする?<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                                            - いや〜まぁそれはそんなことないんじゃないかなw<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                                                - 別に評価をしてもしなくてもいいし..
                        - ふむ、あるオラクルのデータソースとしてはまず検証してもらって、それをGitcoinがいい感じに使えるんじゃね？みたいな感じだな今<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                            - まぁそれでいうと、仮説持っていってフォーラムに投げた方がいいのはそらそうか
                                - 流れ
                                - [[Graph API]]的な？イメージで事業者側に使ってもらう



                                    - ぐらいしかわからんわw<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                                    - そこからはコミュニティが評価する（あるいは残念な場合は放置される）みたいな感じか<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                                    - そうそう。本当にわからないし、どこで声かけてもらえるかとかも運だし、でもなんかこっちおもしろくねみたいな感じかなぁ...<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                                        - でも「[[期待値]]は高いし！」みたいなのはある？w
                                        - そこを詳しく知りたい/言語化して欲しい気持ち<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                                            - なぜ期待値を高いと思うのか
                                                - [[オラクル]]は出せば儲かるんじゃね？みたいな雰囲気は感じるw<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                                                    - [/tkgshn-private/オラクル完全理解](https://scrapbox.io/tkgshn-private/オラクル完全理解)
                                            - そこが根拠だと思うので
                                    - [[セレンディピティ]]期待してとりあえず実装展開するのはまあ良さそう、
                                        - ただ、何を評価するために実験するのかのイメージはあった方が、最適な行動が取れる気はする<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                                        - 例えば、「ソーシャルグラフとタグ付けに思想の多様性は表れるのか」みたいなResearch Question
                                            - [/tkgshn-private/ウォレットのトランザクションに対するassumption](https://scrapbox.io/tkgshn-private/ウォレットのトランザクションに対するassumption)という定義でこれは触れている。あと、元のホワイトペーパー下書きについき<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                                    - このあたり、アカデミア的方法論とcryptoの方法論（主語でかいかも）の違いがあっておもろそう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                        - 談合に対する考え方として参考になりそうなのは[[Pairwise]]のリンクかな
                            - [/tkgshn-private/Pairwise coordination subsidies: a new quadratic funding design](https://scrapbox.io/tkgshn-private/Pairwise coordination subsidies: a new quadratic funding design)
                        - シビル攻撃ではない、[[談合]]の防止<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
            - 例えば反例を書くなら、
                - 99%の人はAと考えるが、1%の人はBと考える、みたいな状態があったとして、Bはタグ付けに反映される?
                    - minorityのものを一番反映させたいのだと思うが、それをタグ候補として提示するの、むずくね
                    - （これは反例というより仕組みの欠点の指摘だな、論点が違った<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>）
                        - 「A. 反映されない」基本的に[[permissionless]]自体が[[誰の許可なくforkすることができる]]だったり、論理的なものであれば[[異議申し立て]]のプロセスを設計するのが当たり前感ある<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                        - なので、それらのジャッジがどう動いてるかを透明性持てれば、Gitcoin側にそれは交渉できるようにすればいいんじゃないかな、知らんけど
                - 自分はCryptoの世界の知識ないので、良い反例を指摘するのむずいな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
                    - というかまあ反例は実験しないと指摘できないので、どちらかというと論点の提示をすべきか
                        - Q. ソーシャルグラフとタグ付けに思想の多様性は表れるのか
                            - 究極は[[51%攻撃]]的なものに悩まされる<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                            - が、これはいろんなエコシステムがどんどんウォレットに対して[[POAP]]や[[SBT]]などをdropするので、それらを共有しながら幅広い人たちのタグ付けを取り入れることが可能
                                - （Twitterでいう）いわゆる「ある程度のフォロワーとかツイート内容がないとBotとみなされる」
                            - [[人力オラクル]]であっても、その51%的なものの閾値を[/tkgshn-private/Tx based automatic generated social graph](https://scrapbox.io/tkgshn-private/Tx based automatic generated social graph)で分類してもいい
                            - [https://www.youtube.com/watch?v=MsMsL5v2-Ls&ab_channel=GitcoinMedia](https://www.youtube.com/watch?v=MsMsL5v2-Ls&ab_channel=GitcoinMedia)
                                - これは[[radical x change]]の[[グレン]]、ほとんどのこのプロダクトを指していると思うのでぜひみてほしい
                        - Q. ソーシャルグラフ/タグ付けに恣意性は入りこまないのか
                            - どうなんだろう、これは[/tkgshn-private/think what people think](https://scrapbox.io/tkgshn-private/think what people think)的な仕組みがどこまで生きるかだよな。<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
                        - など
            - ここの論理的つながり/反例への強度がしっかりしていた方がDeCartographyの仕組みに納得出来そう
        - そもそも論として、DeCartographyは資金の分配をするときのQFの変数を求めたいという話だった記憶があって、とあるプロジェクト関係者からだけの投票だと意味が無い<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
            - つまり「投票における"良い"多様性」は投票によって異なるんだろうな<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
                - [[Decartography#636b24b909c5f20000e3aaf7]]
                - DeCartographyの場合は、投票者が関係してるプロジェクトが多様であることが良い<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>

- > [@kanair_jp](https://twitter.com/kanair_jp/status/1589754571353911297): この話、人が恣意的に選んだものよりも、アルゴリズムに選ばれたものの方がフェアだという認識がすでにできつつあることが面白い。信頼されるAI技術をどう作るかというのはよく話題になるが、実はAIの方が信頼される世の中になるのではないか。


思想的な部分に関して、本当に[[ひとり1ID]]は意味があるのかという疑問は残る<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
- +1<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - 過去の議論の文脈を知らんが、物理身体/意識を絶対視する思想は好みではない<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - めっちゃいい話<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
    - [/sgg-fairy/ひとり1ID](https://scrapbox.io/sgg-fairy/ひとり1ID)<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
        - 気になる（問題なければscrapboxのinvite欲しいです）<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - TwitterのDMに送った<img src='https://scrapbox.io/api/pages/blu3mo-public/u7693/icon' alt='u7693.icon' height="19.5"/>
- 分かりやすいしいいんじゃね？<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
