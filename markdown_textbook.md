<!-- markdown_textbook -->

# 始めに

これは `Markdown` の　textbook です。

以下の「参考」にそのまま書いてあるようなことはあまり解説しません。


またびっくりするかもしれませんが、<u>***Markdown には統一規格がありません***</u>。  
なので実装によって記法が異なることがあります。



## 参考

1. [Qiita 「Markdown記法 サンプル集」 @tbpgr](https://qiita.com/tbpgr/items/989c6badefff69377da7)
   1. Markdown の書き方をほぼ網羅したすごい記事
   1. これを読めばMarkdownの書き方はほぼOKです。 

2. [HABATAKIブログ@翔 「【VSCode】Markdown PreviewをCSSで読みやすくする方法 part2」](https://habataki-blog.com/vscode-markdown-css/)
   1. VSCodeにおけるMarkdownの便利な拡張機能についての記事


# Markdown with VSCode

<u>***Markdown***</u> を <u>***表示・編集***</u> することができる便利なエディターとして <u>***VSCode***</u> があります。

VSCodeにおけるMarkdownの使い方を解説します。

## プレビュー機能

```
ctrl + K  ->  V
```
でプレビューされます。

この時、VSCodeのテーマカラーをもとに、背景やフォントの色をVSCode君がよしなにしてくれますが、それだと物足りないので以下の拡張機能を入れます。

## 拡張機能

1. [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
   1. 中国の方が作った拡張機能ですが、日本語のドキュメントがあり、様々な機能があります。 [日本語ドキュメント](https://shd101wyy.github.io/markdown-preview-enhanced/#/ja-jp/)
   1. 特にVSCodeの表示をCSSでコントロールできるのは大きいです。
1. [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
   1. これも同様に様々な機能がある拡張機能です。

## CSS

デフォルトでもMarkdownのプレビューをCSSでコントロールはできますが、
なんといちいちワークスペースを作って直下にCSSファイルを置かなくてはいけないという~~クソ~~仕様のため、上記の Markdown Preview Enhanced を使います。



1. 
    ```
    ctrl + shift + P
    ``` 
    でコマンドパレットを出す。


1. 
    ```
    > Markdown Preview Enhanced: Customize CSS
    ```
    と入力し、`style.less` を表示させる。

1. `style.less` に CSS を直接書き込む。


## CSSの書き方

`style.less` はデフォルトで以下のようになっている。

```Less
/* Please visit the URL below for more information: */
/*   https://shd101wyy.github.io/markdown-preview-enhanced/#/customize-css */ 

.markdown-preview.markdown-preview {
  // modify your style here
  // eg: background-color: blue;  
}
```

`.markdown-preview.markdown-preview` 直下に直接 CSS を記述する。


<u>**HTML のタグ名**</u> を使って CSS を記述します。

例)
```Less
.markdown-preview.markdown-preview {
  font-family: 'Consolas', 'ＭＳ ゴシック';
  background-color: #0F111A;
  color: #8F93A3;

  h1 {
    color: #8F93A3;
  }
}
```

## 例

実際に使ってみた例です。
私のVSCodeはダークモードなので、背景黒で白文字にしています。

```Less
.markdown-preview.markdown-preview {
  font-family: 'Consolas', 'ＭＳ ゴシック';
  background-color: #0F111A;
  color: #8F93A3;

  h1,
  h2,
  h3,
  h4 {
    color: #8F93A3;
  }

  strong {
    color: #8F93A3;
  }

  em {
    color: #8F93A3;
  }

  td {
    color: #8F93A3;
  }

  th {
    color: #8F93A3;
  }

  pre,
  code {
    background-color: rgb(222, 226, 253);
    font-weight: bold;
    font-size: 3rem;

  }

  li,
  ol {
    margin: 1.6rem 0rem;
  }

  ul{
    margin: 1.8rem 0rem;
  }

}
```

実際にはこのように見えます。

![実際の写真](img/markdown_screenshot.PNG) 


# Tips!

## 記法についての Tips!

### Tableについて

