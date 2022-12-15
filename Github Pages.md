---
title: Github Pages
---

* Reactでgithub pages使う方法
* [https://web-begginer-log.com/create-react-app-gh-pages/](https://web-begginer-log.com/create-react-app-gh-pages/)

package.json

````json
{
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
  }
  "homepage": "./"
}
````

* これを追加する必要がある

* *SPA*っぽい挙動にしたい場合
  
  * [React GitHub Pagesにデプロイ - create-react-appで作ったReactプロジェクトをGitHub Pagesにデプロイしてみましょう。](https://dev-yakuza.posstree.com/react/github-pages/#404ページ)
