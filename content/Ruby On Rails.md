---
title:
 'Ruby On Rails'
---

- 学ぶ過程のメモ

- .erb, .scss, .coffeeとかは、そのファイルをプロセスするための拡張子
    - hoo.html.erb.coffeeみたいなのがあれば、coffeeで処理されて、erbで処理されて、hoo.htmlが出来上がる

- Controllerには複数形(UsersController)、Modelには単数系(User)

- RESTは、Railsでは自動的に対応するアクション(GET->showなど)に変換される
    - routes.rbにresources :usersってやると、/usersがRESTに対応する

- DB周りについて
    - Model.update_attributeは、検証を回避できる
        - update_attributesはできない
    - indexにしたパラメーターなら、全探索せずに済む

- Testについて
    - assert <bool>でtrue/falseチェック
    - assert_XXX <内容> という方式、assert_selectとか、assert_responseとか

- Gem周りについて
    - キャッシュを消すとうまくいくことがある
    - GemFileに書いた順番が影響することもある、Bootstrapの前にJquery置かないと動かなかったり?
#RailsTutorial