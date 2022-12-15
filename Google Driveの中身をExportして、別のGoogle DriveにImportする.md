---
title: Google Driveの中身をExportして、別のGoogle DriveにImportする
---

from [高校GSuiteから個人GDriveへの移行](%E9%AB%98%E6%A0%A1GSuite%E3%81%8B%E3%82%89%E5%80%8B%E4%BA%BAGDrive%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C.md)
[Google Driveの中身をExportして、別のGoogle DriveにImportする](Google%20Drive%E3%81%AE%E4%B8%AD%E8%BA%AB%E3%82%92Export%E3%81%97%E3%81%A6%E3%80%81%E5%88%A5%E3%81%AEGoogle%20Drive%E3%81%ABImport%E3%81%99%E3%82%8B.md)

Step 1. Export

* 全部エクスポートして、個人アカウントに移す
  * 一番シンプル
* [Google Takeout](Google%20Takeout.md)が使えるならそこで一括でexportした方が良い
  * 制約があって使えない場合は、Google Driveのダウンロード機能でフォルダのzipをダウンロード
* ただ、office形式に変換されてしまうのが厄介
  * エクスポートするとdocs, pptの*MS Office*形式ででることは把握している
    * Docs -> word
    * Spreadsheet -> excel
    * Slides -> powerpoint
    * Jamboard -> pdf
    * 生きているコメントはちゃんとword形式に変換はされる
      * それをGoogle Docsに戻せば、ちゃんとコメントも戻る
    * もう使わないドキュメントなら、まあ最悪開ければ良いのでoffice形式でも良いかな
      * 妥協案ではある
  * もしくは、手作業ではあるが、ファイルを共有した上で「Docsのファイル>コピーを作成>コメントを残すオプションでコピー」すればownershipを奪ったコピーファイルが作れる
  * これをフォルダに対して丸ごと行えれば嬉しいけど、むずそう
* あと、他人がownershipを持っているファイルも厄介
  * submitした課題とかは大体先生がowner
  * エクスポートするとどうなる？
    * ちゃんとエクスポートされるので問題なさそう
* エイリアスは？
  * 問題なくexportされる
  * ただ、フォルダはダメみたい..?
    * そのdriveフォルダへのリンクを持つhtmlファイルが生成される
      * まあそれで良さそう<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

Step 2. Merge zips

* ![image](https://gyazo.com/37f1bc916d4d67cd3d9124562a7e4a4a/thumb/1000)
* こういう感じで分割したzipを吐いてくる
* これを全部結合したい
  * [https://stackoverflow.com/questions/60842075/combine-the-split-zip-files-downloading-from-google-drive](https://stackoverflow.com/questions/60842075/combine-the-split-zip-files-downloading-from-google-drive)
    shell

````
mkdir combined
unzip '*.zip' -d combined
````

````
- これだと日本語ファイルが消える、つら
- `checkdir error:  cannot create combined/Projects/z_Past Projects/????????ա?????????? Illegal byte sequence`
    - みたいな感じ
    - > This is an efficient answer, but on macOS 11.2.3, this unfortunately fails for zipped file names with some non-ASCII characters (like û) . The solution of chanduthedev does work, when opening the resulting single ZIP file directly through the Finder. I couldn't find a way of having the unzip command to work. –
        - ないんかい〜
        - [[ditto]]もだめ、一つのファイルしかできないので
    - WindowsあるいはLinux環境ならいける説
        - [[Columbia Computer Lab]]で試すか
- 解決:
    - `unar Projects-20221207T211520Z-<番号>.zip -o combined`
        - これで、combinedフォルダに毎回展開される
    - ので、全番号でこれを繰り返せば展開内容をマージできる
        - オプションはOverrideを選べば良い````
