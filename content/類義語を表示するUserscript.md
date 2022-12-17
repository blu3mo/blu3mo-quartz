---
title:
 '類義語を表示するUserscript'
---

- [[英語]]で文章書いている時に、[[Google Docs]]だと[[Grammarly]]の類義語表示がめっちゃ役立つ
- これをscrapboxに実装したい


- APIをuserscriptからは呼べない
- [[tampermonkey]]でやる感じかな

できた
- [/bluemountain-theme/類義語を表示](https://scrapbox.io/bluemountain-theme/類義語を表示)
![image](https://gyazo.com/8e939e3aae965db49fa4af96d42677c4/thumb/1000)
- 候補を選ぶとクリップボードにコピーされる
- <img src='https://scrapbox.io/api/pages/icons/よさそう/icon' alt='/icons/よさそう.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
    - 欲を言うなら、コピペの手間を省けるとより良くなりそう
        - e.g.
            - 文字列を選択した状態で`Ctrl+Space`を押すと候補が表示される
            - 候補をクリックするか、`Enter`を押すと置換される
