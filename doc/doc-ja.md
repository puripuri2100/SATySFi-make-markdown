# 想定している使い方

SATySFiのテキストモードでMarkdownファイルを出力するときに使用してください。

言語はmarkdownを指定してください。

例えばこのように感じです。


```
satysfi <input>.saty --text-mode "markdown" -o <output>.html
```


# このリポジトリにあるパッケージ

- stdjamarkdown.satyh-markdown
- code.satyh-markdown

# 提供コマンド

## stdjahtml.satyh-html

module StdJaMarkdown

```
  val document : 'a -> block-text -> string
    constraint 'a :: (|
      title : inline-text;
      author : inline-text;
      style-sheet : string;
    |)
```
ドキュメント関数です。

- `direct +section : [string?; inline-text; block-text] block-cmd` : 節です。
- `direct +subsection : [string?; inline-text; block-text] block-cmd` : 小節です。
- `direct +p : [inline-text] block-cmd` : 段落です。
- `direct +pn : [inline-text] block-cmd` : 段落です。

## code.satyh-html

module Code

- `direct +code : [string] block-cmd` : ブロックでのコードです。
- `direct +console : [string] block-cmd` : ブロックでのコンソールです。
- `direct \code : [string] inline-cmd` : インラインでのコードです。
- `direct \console : [string] inline-cmd` : インラインでのコンソールです。
- `direct \d-code : [string] inline-cmd` : ブロックでのコードをインラインで書けます。
