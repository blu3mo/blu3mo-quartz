---
title: Wikichase設計ログ
---

20220731

* n分間逃げ続けたら勝ち、というルールの方が初プレイの人には楽そう
  * とりあえずそっちをメインに実装して、ゴール指定モードもオプションとしてそのうち実装できたら楽しそう

20220709 とりあえず以下のルールでテストプレイ w/ <img src='https://scrapbox.io/api/pages/blu3mo-public/rickshinmi/icon' alt='rickshinmi.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/feda/icon' alt='feda.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/kaya/icon' alt='kaya.icon' height="19.5"/>

 > 
 > 　ルール
 > 　　リアルタイムで進行する鬼ごっこ
 > 　　　（*スコットランドヤード*のようなターン制ではない）
 > 　　Wikipediaのページ上のリンクを飛んで移動して、鬼ごっこをやる
 > 　　警察が逃走者のページに追いついたらゲームセット
 > 　　相手の位置：
 > 　　　警察(chaser)の位置は常に開示される
 > 　　　逃走者(evader)の位置は2回に1回開示される
 > 　　そのままだと逃走者が有利すぎるので、逃走者には二つ制約がある
 > 　　 1. 8秒に1回しか移動できない
 > 移動毎に8秒のクールダウンタイムがある
 > 　　 2. ページの最初の段落のリンクしか使えない

* 結構楽しかった<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* 感想/知見
  * ゴールを設定すると逃げ側にも目的が生まれて良い
    * 「逃げ側の勝ち」が生まれるのも良い
    * ゴールは鬼は知らない方が良さそうだった
      * 鬼がゴールを知っていると、ゴールで待ち伏せが出来てしまうので
      * 圧倒的に早く移動できる鬼側にゴール周辺で待機されるとゴールがほぼ不可能になる
    * ゴールはどう決める?
      * ゴールをランダムに選ぶとかだと問題がありそう
        * 逃げ側は一段落めしか使えないので、結構目的のページに辿り着くのが難しい
          * 特にゴールが固有名詞だと一段落目に書かれないがちで大変
        * ので、ランダムではなく、ゴールとして適切な難易度な単語を選ぶ必要がある
      * テストプレイ時は人力で第三者が決めた
      * 「ゴールとして適切な単語セット」を用意して、そこからランダムに選ぶとかになりそう?
        * ただそうなると多言語展開が難しくなるので、可能であれば機械的にゴールを決められる方法を見つけたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
      * そもそもゴールを複数用意することにして、ランダムに5ページくらいを選ぶとか?
        * 5ページ選べば一つくらいはたどり着けるだろ、みたいな
        * いや、5ページだと無理だなw<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

          * ランダムに5ページ出してみたがどれも絶望って感じだった
  * これ、30ホップ以内に捕まえるとかホップ数制限にしたら楽しいかもって思ったけどそうしたらひたすら連打されるのかな<img src='https://scrapbox.io/api/pages/blu3mo-public/rickshinmi/icon' alt='rickshinmi.icon' height="19.5"/>

    * ゴール設定モードとは別のゲームモードとして、「逃げ側は自由移動で、追う側が制限回数以内に捕まえられたら勝ち」とかあっても楽しそう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
