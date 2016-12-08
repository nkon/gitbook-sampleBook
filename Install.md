# Install

Windows 7環境でインストールする方法について述べる。
Windows10 Anniversary UpdateだとUbuntu環境が使えるので
apt-getしてしまうのが、きっと楽なのだろう。

http://qiita.com/mebiusbox2/items/345b909186d63e487615

## nodejs

* Node.jsのWindowsインストーラを実行すれば、Node.jsとnpmがインストールされる。

## gitbook

* Node.jsとnpmが入っていれば、`npm install -g gitbook-cli` で、一式のインストールが可能。

## PDF生成環境

* svgexportのインストール
```
npm install -g svgexport
```
* [calibre](https://calibre-ebook.com/) のインストール
  + コマンドライン上でcalibreにパスを通しておく。`book.json`あたりで設定出来たら便利なのに。
```
set PATH=%PATH%;C:\Program Files\Calibre2
```

## 動作テスト

* `gitbook init` で、カレントディレクトリを適切に初期化してスケルトンファイルができあがる。
  + `.git/`のリポジトリと`/.gitignore`が自動生成されるのが今風だ。
  + `SUMMARY.md`と`README.md`が自動生成される。
  + `SUMMARY.md`が目次、`README.md`が本体だ。
  + じつは、`SUMMARY.md`はオプショナル、`README.md`は必須だ。
* `gitbook build` でHTMLファイルが生成される。
  + `gitbook serve` で4000番ポートで簡易サーバが立ちあがるので、ウェブブラウザで http://localhost:4000/ をアクセスする。
    ウェブページ形式で表示される。

```
gitbook-sampleBook>gitbook build
info: 9 plugins are installed
info: 7 explicitly listed
info: loading plugin "hide-published-with"... OK
info: loading plugin "numbered-headings-for-web-and-books"... OK
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 4 pages
info: found 4 asset files
warn: "page.progress" property is deprecated
info: >> generation finished with success in 3.2s !

gitbook-sampleBook>gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 9 plugins are installed
info: 8 explicitly listed
info: loading plugin "hide-published-with"... OK
info: loading plugin "numbered-headings-for-web-and-books"... OK
info: loading plugin "livereload"... OK
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 4 pages
info: found 4 asset files
warn: "page.progress" property is deprecated
info: >> generation finished with success in 3.6s !

Starting server ...
Serving book on http://localhost:4000
```

* `gitbook pdf` でPDFファイルが生成される。
  + Adobe Readerなどで中身を確認する。

```
gitbook-sampleBook>set PATH=%PATH%;C:\Program Files\Calibre2

gitbook-sampleBook>gitbook pdf
info: 9 plugins are installed
info: 7 explicitly listed
info: loading plugin "hide-published-with"... OK
info: loading plugin "numbered-headings-for-web-and-books"... OK
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 4 pages
info: found 4 asset files
warn: "page.progress" property is deprecated
info: >> generation finished with success in 6.5s !
info: >> 1 file(s) generated
```

## textlint

* Node.jsとnpmが入っていれば、`npm install -g textlint`でtextlintコマンドがインストールされる。
* npmパッケージとしてtext-lint-rule-* パッケージから好みのものを入れる。
* .textlintrcにルールを設定する。


