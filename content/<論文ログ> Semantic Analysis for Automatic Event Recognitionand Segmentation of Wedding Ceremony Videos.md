---
title:
 '<論文ログ> Semantic Analysis for Automatic Event Recognitionand Segmentation of Wedding Ceremony Videos'
---

- 結婚式の[[映像]]を、[[映像]]とか[[音]]とか用いて[[シーン分割]]する研究
    - 例: ケーキカットのシーン、ブーケトスのシーン
- [[結婚式]]の[[文化]]を前提とした、[[制約]]つき分割
    - ![image](https://gyazo.com/3d834a033e455f91be9961e9fe4833f2/thumb/1000)

- 活用する情報
    - 音声/[[BGM]]を判別した情報
    - [[拍手]]音の特性を用いた情報
    - カメラの[[フラッシュ]]情報
    - Bridal White（衣装の色）（[[カラーヒストグラム]]とか使って）

- これらの情報を[[隠れマルコフモデル]]に突っ込んで、予想

- 結婚式と似たようなイベントにも、方法論を転用できるかもって主張
    - [[誕生日パーティ]]とか

[https://www.researchgate.net/publication/224330770_Semantic_Analysis_for_Automatic_Event_Recognition_and_Segmentation_of_Wedding_Ceremony_Videos](https://www.researchgate.net/publication/224330770_Semantic_Analysis_for_Automatic_Event_Recognition_and_Segmentation_of_Wedding_Ceremony_Videos)
#文献ログ
