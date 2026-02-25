---
translation: true
template: /templates/_template-net.md
title: LaTeX 埋め込み画像 | Aspose.TeX for .NET
linktitle: LaTeX 埋め込み画像
weight: 18	
url: /net/latex-embedded-graphics/
keywords: includegraphics latex、latex 埋め込み base64 グラフィック、latex base64 エンコード グラフィック、write18、shell-escape、latex シェルコマンド
description: この記事では、LaTeX ソースコードに base64 エンコードされた画像を埋め込む方法と、これを可能にする \write18 機能について説明します。
lastmod: "2026-02-25"
---

{{<section overview>}}

## 画像を埋め込む別の方法

一部の TeX/LaTeX システムでは、画像ファイルを LaTeX ファイル自体と別に格納するのではなく、直接 LaTeX ファイル内に埋め込むことができます。ただし、TeX/LaTeX ファイルはプレーンテキストファイルであるため、バイナリデータを含めることはできません。そのため、バイナリデータをテキスト形式で表現する必要があります。つまり、バイナリデータはテキスト表現にエンコードしなければなりません。問題は、そのようにエンコードされた画像を TeX エンジンが直接解釈できないことです。実際、画像の挿入は `graphicx` パッケージの古典的な `\includegraphics` コマンドで行われますが、このコマンドは外部画像ファイルしか扱えません。外部画像ファイル（および中間ファイル）は LaTeX ファイルの外に作成されますが、重要なのは LaTeX ファイルだけを配布すればよいという点です。

さて、エンコードされた画像を LaTeX ファイルに何らかの形で配置したとします。では、画像をデコードするにはどうすればよいでしょうか？残念ながら、LaTeX ファイルから直接画像ファイルを生成して書き出すことはできません。エンコードされた画像を表す文字列は、まず外部テキストファイルに書き出され、その後デコードして画像ファイルが生成されます。

これまでの手順をまとめると次のようになります。

1. 画像をエンコードする。
2. エンコードされた画像データの文字列を LaTeX ファイルに埋め込む。
3. 文字列を外部ファイルに出力する。
4. 手順 3 で作成した外部ファイルをデコードする。
5. デコードされた画像を挿入する。

最初の 2 つのステップは LaTeX ファイルの作者が行います。残りのステップは、適切に指示すれば TeX エンジンが処理します。

まず、画像を文字列に変換する方法から始めましょう。最も一般的で広く使われている方法は **Base64** です。

## Base64 を使ったバイナリデータのエンコード

[**Base64**](https://en.wikipedia.org/wiki/Base64) は、バイナリデータを印字可能な文字列に変換するエンコード方式の一群です。ソースとなるバイナリデータは 6 ビットずつ読み取られ、64 個のユニークな文字の中から対応する文字が選ばれます。すべてのバイナリ‑テキスト変換方式と同様に、**Base64** はテキストだけをサポートするチャンネル上でバイナリ形式のデータを安全に運ぶために設計されています。

この説明から分かるように、**Base64** は私たちが必要としているものです。画像ファイルを **Base64** にエンコードするには、OS に標準で備わっているコマンドラインユーティリティ、ほぼすべてのプログラミング言語が提供する標準／サードパーティ機能、あるいは [Base64.guru](https://base64.guru/converter/encode/file) などのオンラインツールを利用できます。

## エンコードした画像を LaTeX ファイルに配置する

エンコードされた文字列は、LaTeX ファイルのプリアンブルにある標準的な `filecontents` 環境に次のように書き込みます。

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

これで手順 2 は完了です。画像が LaTeX ファイル内部に埋め込まれました！このファイルを LaTeX で処理するとどうなるでしょうか？

LaTeX プロセッサは `filecontents` 環境の文字列を外部ファイル `sample-image.64` として書き出します。`overwrite` オプションが指定されているため、すでに同名のファイルが存在すれば上書きされます。これが手順 3 に相当します。

## Base64 文字列のデコード

手順 4 では、Base64 文字列をデコードする必要があります。この処理は `\write18` 機能を使って実行します。

### `\write18`

古典的な TeX エンジンでは、`\write<number>(<token list>)` がトークンのリストを書き出すプリミティブです。数値が負の場合はログファイルに、15 より大きい場合は端末に、0〜15 の範囲であれば直前の `\openout` によって指定されたファイルに書き出されます。` \openout<4-bit integer>=<file name>` はファイル名を番号にマッピングします。

PDFTeX などの新しい実装では `\write18` が利用可能で、`<token list>` を OS のシェルで実行すべきコマンドラインとして解釈します。この機能は潜在的なバックドアとなり得るため、PDFTeX/LaTeX では機能の有効化レベルを制御するオプションが用意されています。

主に次の 3 つのレベルがあります：無効、制限付き有効、完全に有効。

**Aspose.TeX** では `ShellMode` という TeX ジョブオプションが用意されており、`NoShellEscape` と `ShellRestricted` の 2 つの値が使用できます。`NoShellEscape` は機能を無効化し、`ShellRestricted` はユーザーが `Executable` クラスを拡張して実装したコマンドだけを許可します。ここでは実装の詳細には立ち入らず、`base64` コマンドのエミュレーションが Aspose.TeX に既に実装されていることだけを述べます。既定では `TeXOptions` クラスの `Executables` コレクションにプロトタイプインスタンスが含まれています。

### Base64 データのデコード

Base64 エンコードされたファイルをデコードするには、通常次のコマンドラインを使用します。

```
base64 -d  FILE1 > FILE2
```

ここで `FILE1` は「エンコードされた」ファイル、`> FILE2` は出力を `FILE2` にリダイレクトすることを示します。

したがって、LaTeX ファイルの本文には次の行を追加します。

```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> `\immediate` プレフィックスは、`\write` 操作が TeX スキャナによってコマンドが検出された瞬間に実行されるようにするために必要です。省略するとページ送出時に処理されます。

この行を追加した状態で LaTeX を実行すれば、`sample-image.png` が作成されます。画像ビューアで開いて確認してください！

## デコードした画像の挿入

冒頭で述べたように、デコードした画像は従来通り `\includegraphics` コマンドで挿入します。

```tex
\includegraphics[options]{sample-image.png}
```

以上の手順をすべてまとめると、次のような (ほぼ) 完全な LaTeX ファイルになります。

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \write18{base64 -d  sample-image.64 > sample-image.png}
  \includegraphics[options]{sample-image.png}
\end{document}
```

そして、**Aspose.TeX** API を使用した C# コードは他の記事と同様ですが、`ShellMode` オプションを指定する点が異なります。

{{< gist "aspose-com-gists" "7f54d335270200ebf5987d071bad028a" "Examples_LaTeXEmbeddedBase64EncodedImage" >}}

これで **Step 5** は完了です。完全なサンプルは、[Example project](https://github.com/aspose-tex/Aspose.TeX-for-.NET) をご覧ください。

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースに構築された無料の変換 [Web アプリ](https://products.aspose.app/tex/conversion/latex/) もぜひお試しください。**
