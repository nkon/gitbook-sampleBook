
# textlint でチェック

`/.textlint`にルールを設定しておく。

```javascript
{
  "rules": {
    "max-ten": {
      "max": 3
    },
    "spellcheck-tech-word": true,
    "no-mix-dearu-desumasu": true,
    "preset-japanese": true,
    "preset-jtf-style": true,

  }
}
```

* max-ten: 1つの文の中に含まれる「、」の数の最大値をチェックする。
  https://github.com/textlint-ja/textlint-rule-max-ten
* spellcheck-tech-word: 技術書用のスペルチェック辞書。
  https://github.com/azu/textlint-rule-spellcheck-tech-word
* no-mix-dearu-desumasu: 「である調」と「ですます調」の混在をチェックする。
  https://github.com/azu/textlint-rule-no-mix-dearu-desumasu
* preset-japanese: 日本語のルール
* preset-jtf-style: 日本語のルール(JTFスタイル)
  http://efcl.info/2015/12/30/textlint-preset/


## 推奨するルール

まずは上記の.textlintrcでやってみましょう。
どれを有効化するかは、スイッチで選べるので、今後、共有化して行きたい。

## エディタに組み込む

* VS Codeを使っているなら、[vscode-textlint](https://marketplace.visualstudio.com/items?itemName=taichi.vscode-textlint)拡張がある。