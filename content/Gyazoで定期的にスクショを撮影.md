---
title:
 'Gyazoで定期的にスクショを撮影'
---

- 1~2分に一度スクショ
- とても良いかもしれん
- 良いこと
    - コード書いてて、数分前に消したやつを戻したいけどなんだったっけとなった時に、見返せる
        - 文章執筆でも同じ
    - 書いてた文章が事故で消えても、スクショを見返せば復元できる
- 悪いこと
    - セキュリティ的にスーパーとてもまずい
        - 漏れるとまずい情報とかも全部記録されてく
            - しかもGyazoが便利なせいでOCRで検索可能
        - うまく安全にする方法ないかな

やりかた
- 以下を[[launchd]]で定期実行
    - [[AppleScript]]で[[スクリーンショット]]を撮影
    - [[imagemagick]]で2画面のスクリーンショットをマージ
    - [[curl]]で[[Gyazo API]]に[[POST]]

- [[Gyazo]]、同じ解像度でも画像が小さい方が丁寧に[[OCR]]かかっているっぽい
    - でかい場合はOCRかける前に縮小しているのかな

- 注: 2画面前提のスクリプト
.scpt

```
tell application "System Events"
	set activeApps to name of application processes whose frontmost is true
	set activeApp to item 1 of activeApps
end tell
set activeApp to do shell script "echo " & quoted form of activeApp & " | sed -e 's/ /_/g'"
set shotTime to do shell script "date +\"%Y-%m-%d_%H:%M \" | awk '{$1=$1;print}'"
do shell script "screencapture -x ~/Desktop/Auto_Screenshots/001.png ~/Desktop/Auto_Screenshots/002.png "
do shell script "/usr/local/bin/convert +append ~/Desktop/Auto_Screenshots/001.png ~/Desktop/Auto_Screenshots/002.png ~/Desktop/Auto_Screenshots/merged.png"
delay 1
do shell script "curl -X POST -i \"https://upload.gyazo.com/api/upload?access_token=&desc=" & shotTime & "_Screenshot&app=" & activeApp & "\" -F imagedata=@/Users/bluemountain/Desktop/Auto_Screenshots/merged.png"
```


- 408 タイムオーバーで失敗することが結構ある

- screencaptureコマンドは↓参照
    - [https://ss64.com/osx/screencapture.html](https://ss64.com/osx/screencapture.html)