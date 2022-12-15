---
title: TypescriptでReact
---

* Typescriptの場合、*関数コンポーネント*を書くなら
  ts

````
function GuessInput({ onGuess }: { onGuess: (guess: string) => void }) { }
````

````
- みたいな事になる?
    - onGuessをなんで二度書かないといけないんだ?
````

ts

````
  function GuessInput(props: { onGuess: (guess: string) => void }) { }
````

````
    - で良いのか
````

* [一番文句言われなさそうな React コンポーネントの書き方](https://zenn.dev/seya/articles/0317b7a61ee781)
