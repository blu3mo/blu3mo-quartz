---
title:
 'MVP'
---

![image](https://gyazo.com/68dfc6b7a0dafff134d0cdb7fef18f08/thumb/1000)
#iOSアプリ設計パターン入門

- MVPでmodelをどう実装するか
    - static method ([[DI]]しにくい)
    - [https://medium.com/@rockname/clean-archirecture-7be37f34c943](https://medium.com/@rockname/clean-archirecture-7be37f34c943) の方法
        - これのMVP実装が個人的な正解な感じがする


- 考え方として、
    - Presenter: （もしAndroidでSwiftが使えるなら）このコードをそのまま持っていけるか
    - Model: このコードを簡単に[[CUI]]に出来るか
- みたいなイメージを持つようにしてる（正しいのかな?）

- view遷移の時にデーター受け渡したい場合
    - 遷移元Presenterに、遷移先ViewのInterfaceを作る
    - 遷移元Viewのprepare(for なんちゃら)で、遷移先viewを引数に遷移元Presenterを呼ぶ
    - 呼ばれたら、そこでデーター送る
- が正解かな? (たぶん）
