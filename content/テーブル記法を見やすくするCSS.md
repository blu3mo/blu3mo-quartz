---
title:
 'テーブル記法を見やすくするCSS'
---

テーブル記法を見やすくするCSS

table
| 1 | 2 | 3 | 4 |
| -- | -- | -- | -- |
| 5 | 6 | 7 | 8 |

[/customize/テーブルの見た目をカスタマイズ](https://scrapbox.io/customize/テーブルの見た目をカスタマイズ)を改変
- とりあえずダークモードにしか対応していないけど、[/blu3mo](https://scrapbox.io/blu3mo)では問題ないのでとりあえずこれで
    - 後で気が向いたら直したい
style.css

```
/* セル間に線を入れる */
 .table-block .cell {
 	/* 全てのセルの右と下 */
 	border-right: solid 1px rgba(255,255,255, 0.2);
 	border-bottom: solid 1px rgba(255,255,255, 0.2);
 }
 .table-block .cell:first-child {
 	/* 1列目のセルの左 */
 	border-left: solid 1px rgba(255,255,255, 0.2);
 }
```
