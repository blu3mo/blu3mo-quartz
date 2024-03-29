---
title:
 '多数のiPhoneの同期'
---

#iOSDC2020
- 一斉に20~30台を繋いで[[同期]]させる方法
    - 条件: 20~30台レベル、ネット不要

- Idea 1: [[Core Bluetooth]]
    - 中心のノード一つと、周辺ノードたくさんみたいな[[ネットワーク]]は作れる
    - でも最大4~5台しかできない
        - 解決するためにツリー上のネットワークを作る事はできる、でも不安定すぎるので却下

- Idea 2: [[Multipeer Conectivity]]
    - Core Bluetoothと違って、
        - 多数の接続ができる（more端末台数）
        - [[Bluetooth]]なのかWifiなのかはブラックボックス化されてる、分からない
    - リーダー端末を決めないといけない
        - PeerID（ランダムに決まる）が一番大きい端末を、便宜上リーダーとする
    - リーダーは、複数のセッションを作ってそれぞれ子端末と繋がる
        - なぜ複数?: Multipeer Conectivityの接続数は7~8個程度を超えない方が良いと言われてるから
    - 新しい端末がリーダーよりPeerIDがでかかったら: リーダーを変えて新たにセッション開始
    - リーダーが抜けたら: 同じく新たにセッション開始
    - これらの機能によって、[[有機]]的なネットワークになる

- ただ、ニコニコのコメントで
    - > MultiConnectivityデモを展示会場でやるとラグがすごくなった経験がある・・・
- ってのがあったので注意が必要
