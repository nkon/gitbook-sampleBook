# StyleSheet

## 基本的な設定

`/book.json`に設定を書くことができる。まずは基本的な設定から。

Twitterなどのシェアボタンを消す。
```javascript
{
    "plugins": ["-sharing"]
}
```

Published with GitBookリンクを消す。

```javascript
{
    "plugins": ["-sharing","hide-published-with"]
}
```

このように、`hide-published-with`プラグインを追加する。
このまま、`gitbook build`しようとすると、エラーメッセージが出る。
エラーメッセージに従い、`gitbook install`とコマンドを実行すれば、
自動で(引数などの指定は不要) `hide-published-with`プラグインがインストールされる。

## 章番号を付ける

```javascript
{
    "plugins": ["-sharing","hide-published-with", "numbered-headings-for-web-and-books"]
}
```
`numbered-headings-for-web-and-books` プラグインを使う。

手順は、いつものとおり。

1. `book.json` の `plugins` に追加。
2. `gitbook install`コマンドを実行。

ウェブサイトは次のところにある。

https://www.npmjs.com/package/gitbook-plugin-numbered-headings-for-web-and-books

だいたい、npm リポジトリの検索で、gitbook-plugin で検索すれば良い。
`plugins`に指定するのは、`gitbook-plugin-`を除いたパッケージ名になる。
インストールされたプラグインは、`~/.npm/パッケージ名/`に入るので、それを読めば、簡単なものであれば改造や設定は容易だ。

デフォルトの場合、PDF生成物には、H1章番号と章タイトルの間に何もなくて見かけが悪いので修正する(HTMLの方はドットが入っている)。

`/book.json`にてスタイルファイルを指定。
```javascript
{
    "styles": {
        "pdf": "my_pdf.css"
    }
}
```
指定したスタイルファイルに次を記載。
```css
.page .section h1:before {
  content: counter(h1) ". ";;
  padding-right: 5px;
  counter-increment: h1;
}

```


## 代表的なスタイル

### 見出し

```
# 見出し1
## 見出し2
### 見出し3
```

# 見出し1
## 見出し2
### 見出し3


### 箇条書き

```
* 箇条書き1
    + 箇条書き2
        - 箇条書き3
```

* 箇条書き1(決まりはないのだが、ルールとして * → + → - と使うように)
    + 箇条書き2
        - 箇条書き3


```
1. 箇条書き1
    1. 箇条書き2(4個以上のスペースでネストを表す)
1. 箇条書き1(先頭の数字は無視される)
```

1. 箇条書き1
    1. 箇条書き2(4個以上のスペースでネストを表す)
1. 箇条書き1(先頭の数字は無視される)

```
<dl>
<dt>定義
<dd>説明
<dt>定義付きリスト
<dd>定義付きリストは、HTML の`&lt;dl&gt;`タグを使う
</dl>
```


<dl>
<dt>定義
<dd>説明
<dt>定義付きリスト
<dd>定義付きリストは、HTML の`&lt;dl&gt;`タグを使う
</dl>


### 表

```
|良い例|悪い例|コメント|
|------|------|--------|
|改行<br>改行|悪い例|コメント|
```


|良い例|悪い例|コメント|
|------|------|--------|
|改行<br>改行|悪い例|コメント|



