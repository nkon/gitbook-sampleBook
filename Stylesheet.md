# StyleSheet

## 基本的な設定

`/book.json`に設定を書くことができる。まずは基本的な設定から。

Twitterなどのシェアボタンを消す。
```
{
    "plugins": ["-sharing"]
}
```

Published with GitBookリンクを消す。

```json:book.json
{
    "plugins": ["-sharing","hide-published-with"]
}
```

このように、`hide-published-with`プラグインを追加する。
このまま、`gitbook build`しようとすると、エラーメッセージが出る。
エラーメッセージに従い、`gitbook install`とコマンドを実行すれば、
自動で(引数などの指定は不要) `hide-published-with`プラグインがインストールされる。

