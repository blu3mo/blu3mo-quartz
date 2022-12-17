---
title:
 '弾性同期Youtubeプレイヤー'
---

- [[弾性同期]]的な仕組みの[[Youtube]]配信プレイヤー、面白そう
- もっと分かりやすいユースケースに合わせるなら、
    - Youtube Live視聴時に、遅れているなら自動で若干早送りにされるYoutubeプレイヤー
    - [/mitou2021demoday/自律分散的に展開される遊び場を実現するための遊びの制作支援ツールの開発#62107df52927950000a6ce4d](https://scrapbox.io/mitou2021demoday/自律分散的に展開される遊び場を実現するための遊びの制作支援ツールの開発#62107df52927950000a6ce4d) これみて思った

- 視聴中に止めたりちょっと巻き戻した時に、小さい遅延が生まれることは良くある
    - その遅延を戻すために毎回2倍速にするのは面倒
    - その速度の調整をいい感じに代わりにやってくれるプレイヤーを作った

- できた
    - [https://blu3mo.github.io/elastic-sync-player/](https://blu3mo.github.io/elastic-sync-player/)

---
実装メモ
- [[React]]と[[Youtube Player API]]使えば結構さくっと実装できそう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- [[Chakra UI]]とか[[React+Firebase]]を試しつつ作ってみよう

- [[react-player]]使えば楽に実装できそう
    - 配信の全体durationを取得するのが難しいな
        - Youtube iFrame APIがガタガタっぽい

- Stateの挙動の理解不足でハマった
    - [react HooksでsetTimeoutやsetIntervalなどからstateを参照する | きさらぼ](https://kisalabo.com/2020/04/18/react-8/)
    - [React + TypeScript: setInterval()をReactのプログラミングモデルに合わせてフックに書き替える ー useInterval - Qiita](https://qiita.com/FumioNonaka/items/587c3ed8545d820f330c)
    - [[setInterval]]を[[useInterval]]に置き換えればいけそう
        - こういうの揃ってるのありがたい

- onSeekが拾えないのきついな
    - このせいでseekした瞬間に速度が変わらずとても非直感的なUIになる
    - clickイベントの時に秒数の大きな変化があったらonSeek、みたいな感じで自作はできそうだけど面倒
