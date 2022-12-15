---
title: Clean Architecture
---

![image](https://gyazo.com/b92336ee397b1bbbca075e2af3287737/thumb/1000)

* 中心のもの: 本質的なもの・依存してないもの・変わりにくいもの
* 一番外側: web/フレームワーク/DBなど、移植や技術遷移で変わりやすいもの
* 外側が内側に依存する（制御の流れとは関係ない）

[https://www.slideshare.net/AtsushiNakamura4/clean-architecture-release](https://www.slideshare.net/AtsushiNakamura4/clean-architecture-release)

* *アーキテクチャ*の[一般化](%E4%B8%80%E8%88%AC%E5%8C%96.md)的ルール
* 本質
  * 依存性は、より上位レベルの方針のみ向けよ（一方向）
  * 制御の流れと、依存方向は分離してコントロールせよ
* 問題のありそうな例: データーベースに依存してしまう場合
  * 普通に書くと、DBを呼ぶコードがDBに依存してしまう
  * DBの方向に依存の矢印が向いちゃうと、*ドメイン*（図の中心）と逆方向に依存の矢印が向いちゃう
  * 対処方法
    * 制御の流れと依存方向を別に考える
    * 制御の流れは、DBにアクセスするんだから当然コード-->DB
    * 依存方向を逆にする
      * DBの設計を、コードに合わせて変化させる
      * コードの方に合わせていくスタイルで解決

\#iOSアプリ設計パターン入門

---

\#iOSDC2020

* *Enterprise Bussiness Rule*
  * 同心円の中心
  * アプリによって変わらないロジック
  * 例えば、リバーシアプリならリバーシのルール自体
    * 対AIのリバーシアプリとか、対人のリバーシアプリとかあるだろうけど、それらによって変わらない部分を切り出したのがEnterprise Bussiness Rule
