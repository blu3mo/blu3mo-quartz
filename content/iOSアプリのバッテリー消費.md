---
title:
 'iOSアプリのバッテリー消費'
---

#iOSDC2020
- [[iOS]]アプリの[[バッテリー]]消費は、クラッシュ率より軽視されがち
- Power x Time

- バッテリー使いがちな要素
    - Processing
    - Networking - [[Cellular]] / [[Wi-Fi]] / [[Bluetooth]]
    - Location

- 配布前
    - [[Xcode]]のEnergy Gage
        - Average Energy Impactのゲージがリアルタイムで表示される
            - 注: あくまでも相対的に示される
        - Average Component Utilization
            - 要素づつにわかる
        - 時系列グラフ

- 配布後
    - Xcode Energy Logs
    - Error Logで確認
