# コンテンツの書き方

## リポジトリの初期化

次のコマンドを実行するとリポジトリが初期化される。
```
gitbook init
```
`.gitignore`、`SUMMARY.md`、`README.md`の3つのファイルが作成される。
`.gitignore`まで生成されるのが今風だ。

ついでなので、Gitリポジトリも初期化しておく。
```
git init
git commit -m "initial commit."
```

## コンテンツの書き方

要はMarkdownでガシガシ書くだけ。
Markdownのflavorは [GitHub Flavored Markdown](http://qiita.com/qurage/items/a2f3f52c60d7c64b2e08)だ。

`/SUMMARY.md`は全体の目次となるファイル。
Optionalだが `gitbook init`でも生成されるし、各種文書でも使われているので、ほぼ必須。
`/SUMMARY.md`からリンクを張ったファイルが読み込まれて文書となる。
最初は、次のようになっているはずだ。

```md

# Summary

* [Introduction](README.md)
```

`/README.md`に文書を書いていけば良いのだが、章立てごとにディレクトリを分けても良い。
各ディレクトリには `README.md`を置いて章のまとめとしておこう。


### 図の埋め込み

![sample.gif](sample.gif)

### 表の埋め込み

| タイトル | 要素 |
|----------|------|
| 表の例   | ほげ |
| 表の例   | ふが |


