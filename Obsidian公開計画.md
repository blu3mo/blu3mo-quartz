---
title: Obsidian公開計画
---

[scrapbox-duplicator](scrapbox-duplicator.md)相当の事をやりたい
*Quartz* + *Hugo*が良さそう

Front Matterがないことで詰まった

* 最初は[正規表現でmdの中身を置き換え](%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%8F%BE%E3%81%A7md%E3%81%AE%E4%B8%AD%E8%BA%AB%E3%82%92%E7%BD%AE%E3%81%8D%E6%8F%9B%E3%81%88.md)でfront matterを挿入しようとした
* これを使うと良さそう
  * https://brandonkboswell.com/blog/Publishing-your-Obsidian-Vault-Online-with-Quartz/
  * https://github.com/brandonkboswell/obsidian-export/tree/title_frontmatter
* これを使えばいける
* `/Users/bluemountain/Documents/Dev/obsidian-export/target/debug/obsidian-export notes public-notes --add-titles --frontmatter=always`
  * flags大事
* ファイルのrenderingのignoreは、export, hugo, quartzどれでもいける
  * /private, /Excalidrawは.export-ignoreで排除
