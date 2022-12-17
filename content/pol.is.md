---
title:
 'pol.is'
---

- [[意見]]を集めて二次元にマップするツール
    - 対立している点（=論点）が整理できるのが嬉しさっぽい

[https://compdemocracy.org/algorithms](https://compdemocracy.org/algorithms)
- 自然言語処理を使った意味の解釈はせずに、投票結果だけで二次元マップを実現しているの面白い
    - > "The machine learning 👾 Algorithms run are solely run on the polis opinion matrix of agrees, disagrees and passes by participants on comments. Thus, Polis is language agnostic."
    - ディープラーニングゴリ押しではないこういうやつ好き
- それぞれの意見に対してn人が投票する時、それぞれの意見にn次元の値が紐づく
    - それを[[次元圧縮]]して2次元に落とし込めば、マップができる
    - 天才<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- あとは[[k近傍法]]で[[クラスタリング]]なり分類なりなんでもできる
    - 確かに今思い返すとこれ天才かも。<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
    - [[人力オラクル]]に採用するのはこっちのUIの方がユーザーとしてはやりやすいか？

- なんか<img src='https://scrapbox.io/api/pages/blu3mo-public/masui/icon' alt='masui.icon' height="19.5"/>っぽさを感じた(?)
    - なんと言い換えられるのだろう

- これに[[Quadratic Voting]]を組み合わせれば[[意思決定]]まで持っていける
    - それをやろうとしているのが[[RxC Voice]]
