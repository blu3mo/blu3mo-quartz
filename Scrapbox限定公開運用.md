---
title: Scrapbox限定公開運用
---

* [Scrapbox](Scrapbox.md)を、最近までprivateで運用していた

* そのうちpublicに戻したいなーと思っていたけど、
  
  * publicだとちょっとまずいもの（人のスライドのスクショとか, privateなアンケートの結果とか, 他人の顔が写った写真とか）
  * が増えてしまった
  * *Scrapboxを他人に公開しちゃダメな理由*
* なので、全世界公開はせず、知り合いを編集者に突っ込んでいくという運用を試してみたい

* その人たちへの説明: [⭐️inviteした人たちへ](%E2%AD%90%EF%B8%8Finvite%E3%81%97%E3%81%9F%E4%BA%BA%E3%81%9F%E3%81%A1%E3%81%B8.md)
  
  * 結構上手く回っている
    * にぎやかで楽しい
    * 自分の知らない関連情報が集まる
    * 昔書いたものを他の人が掘り出してくれる
  * 感じる課題
    * 非Scrapboxerを誘いずらい
      * 雑多なメモ箱を見せられてもどうすればいいの？となりそう
    * わざわざ[/blu3mo](https://scrapbox.io/blu3mo)を開いてもらわないと、読まれない
      * あたりまえだけど
        * <img src='https://scrapbox.io/api/pages/blu3mo-public/nishio/icon' alt='nishio.icon' height="19.5"/>この件、個人的には当初の予想ほど問題ではないなと感じている
          * Scrapboxのプロジェクト一覧タブで更新のあったプロジェクトに緑の線が出るようになったことと、bがアルファベット順で上の方にあることですぐ目に入るからかな
          * <img src='https://scrapbox.io/api/pages/icons/なるほど/icon' alt='/icons/なるほど.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

            * （最近、緑の線がついているプロジェクトを頻繁に巡回する癖がついていて、結構無駄に時間を食われるので良くないなー思っている）<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

              * *中毒*みを感じる
              * [/takker/スクボサーフィン防止対策#5fa09c881280f00000f23604](https://scrapbox.io/takker/スクボサーフィン防止対策#5fa09c881280f00000f23604)をどうぞ<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
      * [villagepump](villagepump.md)みたいに全員の書き込みがまとまっていれば、「ここを見れば良い」という場所があって良いなーと思う
        * [/forum-jp/複数プロジェクトのStreamを一つのページで見たい](https://scrapbox.io/forum-jp/複数プロジェクトのStreamを一つのページで見たい)
      * [/nishio/Scrapboxで他人のプロジェクトに参加する](https://scrapbox.io/nishio/Scrapboxで他人のプロジェクトに参加する)
        * 
           > 
           > 　そもそも他人のプロジェクトを読まないのではなか
        
        * 
           > 
           > 　　これは実際、読まない
        
        * 
           > 
           > 　　この「読まない」は「全部のページを読んだりしない」「毎日読んだりしない」ということ
        
        * 
           > 
           > 　　　人間は機械ではないので当たり前である
        
        * 
           > 
           > 　　読める状態であると、何かのきっかけにバースト的に読む時がある
        
        * なるほど<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    * 「誰か書き込んでくれてないかな」と期待して定期的に確認してしまう
      * [/shokai/人間には承認欲求を刺激すると知能が下がるバグがある](https://scrapbox.io/shokai/人間には承認欲求を刺激すると知能が下がるバグがある)あたりの問題
      * *polling*してしまうのが問題なのではないか<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

        * *スキナー箱*と同じ構造になっている
          * 「確認しにいくと必ず情報が得られる仕組み」ではなく、「確認しにいくと確率で情報が得られる仕組み」
          * *ランダム報酬*が絡んでいる
      * 逆にRSSなどの*push通知*を使えば、ある程度緩和されると思う<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

        * 通知アプリの通知をきっかけにして他人のprojectを読む
          * 例えばこのページの更新は通知経由で知った
        * 特に更新頻度が乏しいプロジェクトだと効果が高い
          * 「見に行く→更新ないOTL」というしょうもない精神的摩耗を避けられる
        * RSSは頻度が多すぎるので、[/programming-notes/1日ごとにScrapboxの更新を通知するbot](https://scrapbox.io/programming-notes/1日ごとにScrapboxの更新を通知するbot)をなどで頻度を調節するとちょうどいい感じなる(ステマ)
        * 自分のプロジェクトのRSS通知、ほとんどが自分の編集なのが難点<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

          * 更新された行のうち、自分のuser idと一致しないものを通知する仕組みをつくればいけそう<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
  * ScrapboxのSlack通知を流しておくと、それぞれの書き込みの編集者がわかって良い
    * ないだろうけど、もし万が一荒らされても誰がやったか分かる
    * アイコン付け忘れて書いてそうなやつとかも、誰が書いたか分かる
    * *自分以外のユーザーによるScrapboxへの書き込みを通知*
* 真似してこの運用をやってる人をちらほら見る
  
  * [/tkgshn](https://scrapbox.io/tkgshn)
  * [/rickshinmi](https://scrapbox.io/rickshinmi)
  * [/momeemt](https://scrapbox.io/momeemt)
