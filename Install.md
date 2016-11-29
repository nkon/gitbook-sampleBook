# Install

Windows 7 環境でインストールする方法について述べる。
Windows10 Aniversary UpdateだとUbuntu 環境が使えるので
apt-get してしまうのが、きっと楽なのだろう。

http://qiita.com/mebiusbox2/items/345b909186d63e487615

## nodejs

* Node.js の Windows インストーラを実行すれば、Node.js と npm がインストールされる。

## gitbook

* Node.js と npm が入っていれば、`npm install -g gitbook-cli` で、一式のインストールが可能。

## PDF生成環境

* svgexport のインストール
```
npm install -g svgexport
```
* [calibre](https://calibre-ebook.com/) のインストール
  + コマンドライン上で calibre にパスを通しておく。`book.json`あたりで設定出来たら便利なのに。
```
set PATH=%PATH%;C:\Program Files\Calibre2
```

## 動作テスト

* `gitbook init` で、カレントディレクトリを適切に初期化してスケルトンファイルができあがる。
* `gitbook build` で HTMLファイルが生成される。
  + `gitbook serve` で 4000番ポートで簡易サーバが立ちあがるので、ウェブブラウザで http://localhost:4000/ をアクセスする。
    ウェブページ形式で表示される。
* `gitbook pdf` でPDFファイルが生成される。
  + Adobe Reader などで中身を確認する。


## textlint

* Node.js と npm が入っていれば、`npm install -g textlint`で textlint コマンドがインストールされる。
* npm パッケージとして text-lint-rule-* パッケージから好みのものを入れる。
* .textlintrc にルールを設定する。


