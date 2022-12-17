---
title:
 'Wikidriveについて考える20220327'
---

from [[Wikidrive]]
- Wikidriveの仕様を考える
    - [[Google Drive]]の最上位階層にある各ファイルが、Scrapboxにページとして表示される
        - 全ファイルを最上位階層に置く前提
        - 逆に、フォルダがあってもそれをファイルとして捉える
            - この仕様があれば、階層管理をしたい場合にそれも出来る
            - ページ内は箇条書き（階層）のScrapboxと同じ感じ
        - ファイルの名前変化/削除に追従してScrapboxページの名前も変化する
    - Scrapboxページには書き込んだりリンクを貼れる
        - [[文芸的ファイルシステム]]になる
    - 検索時
        - Scrapboxページの書き込み検索と、Google Driveの全文検索両方使いたいな
        - それら統合する検索用サイト作ってもいいか
        - [/ScrapboxSpace](https://scrapbox.io/ScrapboxSpace)がどうやってるか気になる<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - [/takker/ScrapboxからGyazoのOCR結果を検索するUserScript](https://scrapbox.io/takker/ScrapboxからGyazoのOCR結果を検索するUserScript)と同じ方式で行けるな
            - ↑これとその元のやつ、頭いい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
            - 全文検索で該当するファイルをGoogle Driveで出した上で、それをScrapboxに表示する感じ

- 懸念
    - 自分がアホなことによって[[セキュリティホール]]を作ってしまった場合が怖い
        - 信頼できる人に紹介していけばそのうち見つかるかな
    - ファイル同士の名前が被る場合はどうする？
        - Scrapbox以前にDriveの方で被れないので、まあそれはいいか
        - まあそこは普通に避ければいいか

- すごそうな所（予想）
    - 色々書き込むWikiとファイルシステムを紐づけられる点
        - [[文芸的プログラミング]]のファイル版、[[文芸的ファイルシステム]]みたいな感じ
    - 最上位階層にフォルダがあったらそれを一ページとして捉えるという[[階層]]と[[非階層]]の[[ハイブリッド]]さ
    - この二点、どちらもすごくない??という気持ち<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
        - テンションが上がっている
        - [[何かアイデアを思いついた時特有の高テンション]]

- どんな課題を解決するのか
    - ファイル管理の面倒くささを解消
        - 階層管理していると、複数の場所に存在しうるファイルが出てくる
            - そういう時に困る
            - [/IFPsychology/階層型ファイルシステムの憂鬱](https://scrapbox.io/IFPsychology/階層型ファイルシステムの憂鬱)で既に言及されている
        - 探す時
            - 階層型の場合、このファイルはこの中のこの中のこの中にあったよな〜と引っ張り出す
                - 「見つけたいファイル」がわかっているなら、Wikiで検索ビリティを高めて検索した方が早い
                - たぶん、知らない物を見つけたいなら[[階層型]]の方が良い事もあると思う
                    - [[枠組みがあれば、その枠で囲まれた空白を認知できる]]
                    - と思ったけど別にそんなこともないか
    - シチュエーション

    - まあ課題とかは頭の片隅におきつつ、コンセプトの面白さ駆動でまずはプロトタイプを作りたい<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

- どんな感じの実装になる?
    - [[Google Drive API]]がどの程度充実してるか次第だな
    - できること
        - Drive API
            - 書き込み系
        - Drive Activity API
            - > The Google Drive Activity API lets your app retrieve information about a user's Google Drive activity. This provides additional functionality on top the existing Drive API for your app to do things like:
                - > Display activity on a user's files.
                - >  Track changes to specific files or folders.
                - お、これでは
                - >  Alert a user to new comments or changes to files.
    - 要は情報の流れはGDriveからScrapboxへ一方通行
        - シンプルで良い