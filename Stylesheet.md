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

だいたい、npmリポジトリの検索で、gitbook-pluginで検索すれば良い。
`plugins`に指定するのは、`gitbook-plugin-`を除いたパッケージ名になる。
インストールされたプラグインは、`~/.npm/パッケージ名/`に入るので、それを読めば、簡単なものであれば改造や設定は容易だ。

デフォルトの場合、PDF生成物には、H1章番号と章タイトルの間に何もなくて見かけが悪いので修正する(HTMLの方はドットが入っている)。

http://qiita.com/nutti/items/96e7194c82b8d04382e2

`/book.json`にてスタイルファイルを指定。

```javascript
{
    "styles": {
        "webstyle" : "my_website.css",
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

## 表紙が気に入らない

PDF版では、表紙の"Table of Contens" に"1." と不要な番号が付くので抑制する。

`my_pdf.css`に次のように指定。

```
.page .section.toc h1:before{
  display: none;
}
```

### ページテンプレートの編集

デフォルトのページテンプレートは次のところにある。

`C:\Users\mm05681\AppData\Roaming\npm\node_modules\gitbook\node_modules\gitbook-plugin-theme-default\_layouts`

これを`/_layouts/`にコピーして編集すれば、さらにカスタマイズが可能だ。

表紙に章が並ぶが、PDF版の場合は変な番号が付いてしまうので、それを削除する。

`/_layouts/ebook/summary.html`を次のように編集する。

* summary
  + part(章)
    - article(節)

このようなデータ構造になっているので、自分の文章の構成によって、どのレベルのループを回すかを編集する。


```
｛% block page %}
<div class="section toc">
    <h1>｛｛ "SUMMARY"|t ｝｝</h1>
    <ol>
        ｛% for part in summary.parts %｝
            ｛% if part.title %｝
            <li class="part-title">
                <h2>｛｛ part.title ｝｝</h2>
            </li>
            ｛% endif %｝
<!--            ｛｛ articles(part.articles) ｝｝ -->
            ｛% for article in part.articles %｝
            <li>｛｛ article.title ｝｝</li>
            ｛% endfor %｝

            ｛% if not loop.last %｝
            <li class="divider"></li>
            ｛% endif %｝
        ｛% endfor %｝

        ｛% if glossary.path %｝
        <li>
            <span class="inner">
                <a href="｛｛ ('/' + glossary.path)|contentURL ｝｝">｛｛ "GLOSSARY"|t ｝｝</a>
            </span>
        </li>
        ｛% endif %｝
    </ol>
</div>
｛% endblock %｝
```
