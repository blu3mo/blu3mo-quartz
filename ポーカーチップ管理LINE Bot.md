---
title: ポーカーチップ管理LINE Bot
---

* *ポーカー*を学校でやってみた
  * 物理チップはない
  * 電卓で管理しようとしたけどキツすぎる
* ので[LINE Bot](LINE%20Bot.md)をサクッと作った

 > 
 > 使い方
 > 「set \<数字>」自分の所持チップを設定（ゲーム開始時とかにやる感じ）
 > 「\<数字>」所持チップをベット、その分がポットに追加される
 > 「allin」オールイン
 > 「win」ポットのお金を全部獲得
 > 「win \<数字>」ポットのお金を部分的に獲得
 > 「now」現状のポット金額とプレイヤー所持金を見る
 > 
 > （ポットは、現在場にかけられているチップのこと）

![image](https://gyazo.com/5f8cd73019bbdd43905cc95de2a77259/thumb/1000)

* こんな感じ

* こういうのをサクッと実装するような人でありたいな〜という気持ち
  
  * *実装力をあげたい*
* 実装
  
  * とりあえず雑な実装
  * ベットは短時間に何度も入るので、数字を直接変化する形だと被って片方のベットが記録されなくなることがある
    * 最低限ベットの整合性は取れるように、差分データの記録を積み上げていく形にした
    * それ以外の処理(ポット獲得)とかは面倒なのでやってない
      * 原則性善説なので
    * 本当にちゃんとやるなら、[ACID特性](ACID%E7%89%B9%E6%80%A7.md)あたりをちゃんとしないと
      * キューを用意して順番に処理みたいな
* すごいなぁ<img src='https://scrapbox.io/api/pages/blu3mo-public/rickshinmi/icon' alt='rickshinmi.icon' height="19.5"/>
  
  * BB/SB/Antiが設定できたらもっと面白そう
  * 現状学校では雰囲気で遊んでいる（BB/SBの区別等ない）ので、もうちょい正確にやり出したら実装したい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
* リッチメニューを使うともっとGUI的に使いやすい？<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
