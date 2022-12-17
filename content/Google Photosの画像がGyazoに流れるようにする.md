---
title:
 'Google Photosの画像がGyazoに流れるようにする'
---

- [[Google Photos]]の画像が[[Gyazo]]に流れるようにする
- [[Google Photos API]]と[[Gyazo API]]
- [[GAS]]を使うのが良さそう、[[Google]] APIだし

- Google Photos API, しょぼいな
    - webhookないのか
    - あとダウンロード時に位置情報とか剥がされるっぽい
        - <img src='https://scrapbox.io/api/pages/blu3mo-public/masui/icon' alt='masui.icon' height="19.5"/>が言ってたのこれかな
    - [https://github.com/gilesknap/gphotos-sync](https://github.com/gilesknap/gphotos-sync)
    - [[Integromat]]のGoogle Photos Integrationに、「Watch Media Items」がある
        - > Triggers when new photo or video is added
        - これで得た画像を、[[Gyazo API]]でGyazoに突っ込めば実現できそう

- 結局、全部Integromatでできた
    - パラメータについては、Google Photosの指定は入れない方が良さそう
        - それで繋がりが生まれてしまう
    - 制限があるっぽい
        - Data transferがやばいな、100MBか
            - ![image](https://gyazo.com/1b08bdea4dec4b2eddad408dd1eb97d2/thumb/1000)
    - 別に全部Integromatでやる必要はない
        - なので、画像の差分検知だけIntegromatでやって、実際の画像のダウンロードとかGyazoへのアップロードは別の場所でやると良さそう
        - そうすれば100MB制限も問題無い

 .js

```javascript
const response = UrlFetchApp.fetch("https://i.gyazo.com/1b08bdea4dec4b2eddad408dd1eb97d2.png")
const blob = response.getBlob()
const res = UrlFetchApp.fetch("https://upload.gyazo.com/api/upload", {
  method: "POST",
  body: {
    access_token: accessToken,
    imageData: blob,
  },
})
```

↑を試したけど、`400: request parameter imagedata should be image file binary of supported type(jpeg, png, ...).`が帰ってくる
- なんでだろう..?
    - やってることはこれと同じ
        - [https://qiita.com/sublimer/items/2bf030248ab69e32b1f8](https://qiita.com/sublimer/items/2bf030248ab69e32b1f8)
- bodyじゃなくてpayloadに変えたら動いた....<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
    - [[REST API]]を雰囲気で使っていた結果
