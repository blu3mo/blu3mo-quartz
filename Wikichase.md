---
title: Wikichase
---

*Wikipedia*で*鬼ごっこ*

* *Wikichase設計ログ*
* *Wikichase実装ログ*
* [/collab/Wikichase](https://scrapbox.io/collab/Wikichase)
* TODO: 大事なのでここにメモ,権利関係ちゃんと確認

---

以下ルール説明

* Wikipediaのネットワークで*鬼ごっこ*ができるゲームを作った<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
  
  * ![image](https://gyazo.com/8133bb1dbfdf40d4d306f4863b6105d9/thumb/1000)
  * *スコットランドヤード*のWikipedia版の様なイメージ
* 警察側 HunterのURL: `https://wikichase.vercel.app/<ゲームID>/hunter`

* 逃走者側 RunnerのURL: `https://wikichase.vercel.app/<ゲームID>/runner`

* ゲームIDは任意の文字列
  
  * 鬼と逃走者で同じ文字列を入れると、一緒に遊べる
* テスト用URL
  
  * 警察側のURL [https://wikichase.vercel.app/game_123/hunter](https://wikichase.vercel.app/game_123/hunter)
  * 逃亡者側のURL [https://wikichase.vercel.app/game_123/runner](https://wikichase.vercel.app/game_123/runner)
  * ゲームIDを任意の文字列に変えれば新しいゲームが開始できます
* ルール
  
  * リアルタイムで進行する鬼ごっこ
    
    * （*スコットランドヤード*のようなターン制ではない）
  * Wikipediaのページ上のリンクを飛んで移動して、鬼ごっこをやる
  
  * 警察が逃走者のページに追いついたらゲームセット
  
  * 相手の位置：
    
    * 警察(chaser)の位置は常に開示される
    * 逃走者(evader)の位置は2回に1回開示される
  * そのままだと逃走者が有利すぎるので、逃走者には二つ制約がある
    
    ````
      - 移動毎に8秒のクールダウンタイムがある
    ````
  
  * ![image](https://gyazo.com/8133bb1dbfdf40d4d306f4863b6105d9/thumb/1000)
