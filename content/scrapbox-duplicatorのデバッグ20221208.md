---
title:
 'scrapbox-duplicatorのデバッグ20221208'
---

- [[scrapbox-duplicator]]、Herokuで再度立てたらエラー吐いたので確認
- `deno run --allow-net=scrapbox.io --allow-read=./ --allow-env index.ts`
error

```
Exporting a json file from "/blu3mo"...
error: Uncaught (in promise) SyntaxError: Unexpected token < in JSON at position 0
  const { pages } = (await res.json()) as ExportResponse;
                     ^
    at JSON.parse (<anonymous>)
    at packageData (deno:op_crates/fetch/22_body.js:247:21)
    at Response.json (deno:op_crates/fetch/22_body.js:192:18)
    at async exportJSON (file:///app/index.ts:39:22)
    at async file:///app/index.ts:79:17
```


[https://learn.microsoft.com/en-us/answers/questions/449617/syntaxerror-unexpected-token-lt-in-json-at-positio.html](https://learn.microsoft.com/en-us/answers/questions/449617/syntaxerror-unexpected-token-lt-in-json-at-positio.html)
> this error is typical when rather than return json, the webapi is returning the developer html error page.
- これありそうだな<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>
- [[ScrapboxのSID]]の設定ミスかと思ったが違った
- あとで追う
