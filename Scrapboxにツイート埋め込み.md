---
title: Scrapboxにツイート埋め込み
---

* Goal: よくあるツイート埋め込みをやりたい

![image](https://gyazo.com/91c78eac118ba5aedc85455616d19cce/thumb/1000)

* ↑こんな感じで埋め込む事は可能
  embed.html

````html
<blockquote class="twitter-tweet" data-theme="dark"><p lang="en" dir="ltr">Sunsets don&#39;t get much better than this one over <a href="https://twitter.com/GrandTetonNPS?ref_src=twsrc%5Etfw">@GrandTetonNPS</a>. <a href="https://twitter.com/hashtag/nature?src=hash&amp;ref_src=twsrc%5Etfw">#nature</a> <a href="https://twitter.com/hashtag/sunset?src=hash&amp;ref_src=twsrc%5Etfw">#sunset</a> <a href="http://t.co/YuKy2rcjyU">pic.twitter.com/YuKy2rcjyU</a></p>&mdash; US Department of the Interior (@Interior) <a href="https://twitter.com/Interior/status/463440424141459456?ref_src=twsrc%5Etfw">May 5, 2014</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
````

````
- 埋め込みhtmlはこんな感じ
- ただ、widgets.jsが読まれていないので、本物みたいに展開されない
````

* [https://platform.twitter.com/widgets.js](https://platform.twitter.com/widgets.js) をScrapboxに置けば読み込めるのではと一瞬思ったけど、そんなわけなかった
  
  * そりゃそう、widget.jsは読み込めてもその先が*CSP*でブロックされる
* これ、*tampermonkey*あたり使ってwidget.jsをうまい事読み込めたりしないのかな
  
  * （無知な発言な気はしている）
* [/yuiseki/tweetのURLがある行にtweet埋め込みを表示する](https://scrapbox.io/yuiseki/tweetのURLがある行にtweet埋め込みを表示する)
  
  * 先人の知恵
