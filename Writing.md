# コンテンツの書き方

## リポジトリの初期化

次のコマンドを実行するとリポジトリが初期化される。
```
gitbook init
```
`.gitignore`、`SUMMARY.md`、`README.md`の３つのファイルが作成される。

ついでなので、git リポジトリも初期化しておく。
```
git init
git commit -m "initial commit."
```

## コンテンツの書き方

要は Markdown でガシガシ書くだけ。

`/SUMMARY.md`は全体の目次となるファイルで必須。
`/SUMMARY.md`からリンクを張ったファイルが読み込まれて文書となる。
最初は、次のようになっているはずだ。

```md:/SUMMARY.md

# Summary

* [Introduction](README.md)
```

`/README.md`に文書を書いていけば良いのだが、章立てごとにディレクトリを分けても良い。
各ディレクトリには `README.md`を置いて章のまとめとしておこう。




### 図の埋め込み

### 表の埋め込み

## textlint でチェック

### 推奨するルール
