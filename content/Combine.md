---
title:
 'Combine'
---

- [[Swift]]のやつ
[https://www.youtube.com/watch?v=0wTld_ROx2Y&feature=emb_title](https://www.youtube.com/watch?v=0wTld_ROx2Y&feature=emb_title)

[https://speakerdeck.com/shiz/sorosorocombine](https://speakerdeck.com/shiz/sorosorocombine)
- 「連続した多種類の非同期処理などを単一の方法で扱う宣言的なAPI」
    - 多種類: delegate, closure, etc..
        - これらが全てPublisherになる
    - 宣言的: 目的のみを指定?
- 内部での最適化が期待できるのもCombineのメリット

- `Publisher<Output, Failure: Error>`
    - Completion(finishedもしくはfailure)するまで値:Outputを流し続ける
- `Subscriber<Input, Failure: Error>`
    - Publisherから値を受け取る (InputとOutput, FailureとFailureの値が同じじゃないといけない)
    - 値を受け取る側主導、Subscriberは必要な分だけ受け取るという仕組み (BackPressureというらしい)
        - demandを調整
- `Subscription`
    - PublisherとSubscriberを仲介
    - Cancellable
        - AnyCancellable: メモリから解放されるとCancelが自動でされる
            - 画面遷移時に前の処理を消させたい場合とか
#iOSDC2020
