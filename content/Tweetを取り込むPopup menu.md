---
title:
 'Tweetを取り込むPopup menu'
---

- <img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>結構ツイートを引用してると思ってたので紹介
    - [/customize/Tweetを取り込むPopup menu](https://scrapbox.io/customize/Tweetを取り込むPopup menu)
- 便利です、めっちゃ使ってる
- ありがとうございます！！<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>

- <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>🙏
    - 入れた
    - このscrapboxでは人をTwitterID名で基本的に管理してるから、ツイートした人のidがリンクになるように変えた
    - [/bluemountain-theme/Tweetを取り込むPopup menu](https://scrapbox.io/bluemountain-theme/Tweetを取り込むPopup menu)
    - 例
        - >  小難しい言葉を使いすぎて「リアルタイム授業」「オンデマンド授業」という言葉を忘れていた
        - >  	@[[blu3mo]] [March 5, 2021](https://twitter.com/blu3mo/status/1367813572986765316?ref_src=twsrc%5Etfw)
        - 「blu3mo」がリンクになる
        - （よく考えたら自分の名前は唯一TwitterID名で管理してなかった..）

- これさ、私が[[userscript]]を理解してないからあれなんだけど、カスタマイズの仕方を教えて欲しい<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
    - [/bluemountain-theme/Tweetを取り込むPopup menu](https://scrapbox.io/bluemountain-theme/Tweetを取り込むPopup menu)だとこうなるじゃん、
        - >  むしろ標準化されてないやり方で、同じ結果にしないといけないから今は大変。
        - >  	@[[fukkyy]] [[https://twitter.com/fukkyy/status/1368106933387812870?ref_src=twsrc%5Etfw](https://twitter.com/fukkyy/status/1368106933387812870?ref_src=twsrc%5Etfw) March 6, 2021
    - だけど、これに加えて、Tweet引用がわかりやすいようにアイコン<img src='https://scrapbox.io/api/pages/icons/Twitter/icon' alt='/icons/Twitter.icon' height="19.5"/>を加えたい ]
        - >  <img src='https://scrapbox.io/api/pages/icons/Twitter/icon' alt='/icons/Twitter.icon' height="19.5"/> むしろ標準化されてないやり方で、同じ結果にしないといけないから今は大変。
        - >  	@[[fukkyy]] [March 6, 2021](https://twitter.com/fukkyy/status/1368106933387812870?ref_src=twsrc%5Etfw)
            - こうやって最初に`[/icons/Twitter.icon]`を埋め込むためには、どの部分を変更したらいい？
            - 解読したけど難しかった (((;◔ᴗ◔;)))
                - ![image](https://gyazo.com/22b4ca334acc010e76b3c2a04abf0483/thumb/1000)
                - 読みづらくて本当に申し訳ないです……<img src='https://scrapbox.io/api/pages/blu3mo-public/takker/icon' alt='takker.icon' height="19.5"/>
        - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>↓
convert.js

```javascript
function convert({tweetInfo, indent}) {
  return [
    ...tweetInfo.content.map(text => `${indent}> [/icons/Twitter.icon]${text}`),
     //@blu3mo ツイッターアイコン追加
    `${indent}> \t@[${tweetInfo.signatureID}] [${tweetInfo.date.href} ${tweetInfo.date.text}]`
  ].join('\n');
}
```

        - でできると思われる（未テスト）
