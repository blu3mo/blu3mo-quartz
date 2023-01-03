---
title:
 'Hugo Quartzで画像が表示されない'
---
- [General Infos (Folder Structure, Links)](https://glossary.airbyte.com/term/general-infos#:~:text=image/)
> Similarly, you can put local images anywhere in the `/content` folder.
- うーん、出来ないな💭
- `<a class="internal-link broken">Screenshot 2022-12-28 at 7.52.08 PM.png</a>`
	- こうなってる💭
- ![](https://i.imgur.com/kl3FN2n.png)
	- ダメだった
- [quartz/textprocessing.html at c1b0eafce668c0c7498a5875c23c074eeb71e842 · jackyzha0/quartz · GitHub](https://github.com/jackyzha0/quartz/blob/c1b0eafce668c0c7498a5875c23c074eeb71e842/layouts/partials/textprocessing.html)
	- ここで、relpathのfileExists判定がfalseになってるのが問題
	- `<!-- attempt to reverse typographer behaviour -->`がうまくいっていないのかな