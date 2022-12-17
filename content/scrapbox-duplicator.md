---
title:
 'scrapbox-duplicator'
---

[https://github.com/blu3mo/Scrapbox-Duplicator](https://github.com/blu3mo/Scrapbox-Duplicator)
![image](https://www.herokucdn.com/deploy/button.svg)
- 👆のやつ（[[Deno]]）を[[heroku]]とかで定期実行してあげれば動く
- ページタイトルに`[public.icon]`が含まれている物のみ転送する仕組みになってる
- 詳細説明: [https://github.com/blu3mo/scrapbox-Duplicator](https://github.com/blu3mo/scrapbox-Duplicator)

- [[Scrapboxを一部以外全てミラーする運用]]のために作った

- 正しく動く保証は無いので使用は自己責任で
    - というか事故を起こされても怖いので使用はお勧めしません
    - 使う前にバックアップとか取っておいてください

- これはn時間に一回しか動かないので、[[ページ転送する拡張script]]を一緒に使うとすぐ転送したい時にも転送できるので良い

参考にしたやつ
- [/ras/非公式なscrapboxのAPIを叩く](https://scrapbox.io/ras/非公式なscrapboxのAPIを叩く)
- [https://castaneai.hatenablog.com/entry/2020/04/30/002737](https://castaneai.hatenablog.com/entry/2020/04/30/002737)
- [https://github.com/puppeteer/puppeteer](https://github.com/puppeteer/puppeteer)
- [/tkgshn/Herokuでワンクリックdeployを試す](https://scrapbox.io/tkgshn/Herokuでワンクリックdeployを試す)

- [[GASでScrapboxのexport APIを呼ぶ]]
- [[puppeteerでScrapboxにimport]]
の二つを組み合わせた上で、jsonを処理してあげればできる

問題点
- ページの名前を変えたときに、それが反映されず新しいページとして読み込まれる
    - [[scrapbox-sync]]はそれができるらしい
        - これが割と大きい気がしてきた<img src='https://scrapbox.io/api/pages/blu3mo-public/tkgshn/icon' alt='tkgshn.icon' height="19.5"/>
    - 雑な対処として、定期的に全リセットをかけるとかはできそう
    - ただ、過去にリンクを貼られたページがリンク切れを起こすと言う問題はある
        - （これはscrapbox-syncでも一緒だと思う）
        - まあこれは仕方ないとするか

#Deno #Heroku
