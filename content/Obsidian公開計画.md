---
title:
 'Obsidian公開計画'
---
[[scrapbox-duplicator]]相当の事をやりたい
[[Quartz]] + [[Hugo]]が良さそう

Front Matterがないことで詰まった
- plan 1: 最初は[[正規表現でmdの中身を置き換え]]でfront matterを挿入しようとした
- plan 2: これを使うと良さそう?
	- https://brandonkboswell.com/blog/Publishing-your-Obsidian-Vault-Online-with-Quartz/
	- https://github.com/brandonkboswell/obsidian-export/tree/title_frontmatter
		- `/Users/bluemountain/Documents/Dev/obsidian-export/target/debug/obsidian-export notes public-notes --add-titles --frontmatter=always`
			- flags大事
		- ファイルのrenderingのignoreは、export, hugo, quartzどれでもいける
			- /private, /Excalidrawは.export-ignoreで排除
		- 対処
			- リンク切れ
				- privateの場合と、2-hopの場合と、文字置き換えでリンク切れの場合がある
				- 文字置き換えは対処、privateは仕方ない
				- ただ、全部リンクが切れて困っている
			- ![[Screenshot 2022-12-15 at 10.01.51 PM.png]]
				- 日本語入ってるとだめか〜〜〜、、、、
					- ![[Screenshot 2022-12-15 at 10.03.41 PM.png]]
					- 問題はこれだな
						- というかここはwikilinkでも効くはずなので、この変換いらないんだよな
				- 本当に欲しい変換は[[frontmatter]]の追加とprivateの排除だけ
					- [Quartz]がobsidian記法に対応しているので
					- なのに、色々と追加されて困る
					- これはむしろfrontmatterだけ自力で追加した方が早いかも
- plan 3: [[ObsidianToQuartz]]実装

- https://fulcra.design/Notes/-Start-publishing-my-notes/#tasks
	- 参考になりそう
		- 