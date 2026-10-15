---
translation: true
template: /templates/_template-java.md
title: LaTeX 埋め込みグラフィックス | Aspose.TeX for Java
linktitle: LaTeX 埋め込みグラフィックス
weight: 18	
url: /java/latex-graphics-embedding/
keywords: includegraphics latex, latex embed base64 graphics, latex base64 encoded graphics, write18, shell-escape, latex shell command
description: この記事では、LaTeX ソースコードに Base64 エンコードされた画像を埋め込む方法と、これを可能にする \write18 機能について学びます。
lastmod: "2026-02-27"
---

{{<section overview>}}

## 画像を含める代替方法

一部の TeX/LaTeX システムでは、画像を外部ファイルとして保存せず、LaTeX ファイル自体に直接埋め込むことができます。ただし、TeX/LaTeX ファイルはプレーンテキストでありバイナリデータを含めることができないため、バイナリデータをテキスト形式で表現する方法が必要です。つまり、バイナリデータはテキスト表現にエンコードされなければなりません。このエンコードされた画像を TeX エンジンが直接解釈できるわけではありません。最終的には `graphicx` パッケージの `\includegraphics` コマンドで画像を取り込むことになりますが、このコマンドは外部画像ファイルの取り扱いに限定されています。したがって、外部画像ファイル（および中間ファイル）を LaTeX ファイルの外部に作成し、組版時にのみ使用する必要があります。その利点は、配布するのは LaTeX ファイルだけで済むことです。

さて、エンコードされた画像を LaTeX ファイルに埋め込んだとします。この画像をどのようにデコードすればよいでしょうか？ LaTeX ファイルから直接読み取り外部画像ファイルとして書き出すことはできません。代わりに、エンコードされた画像を表す文字列を外部テキストファイルに書き出し、そこからデコードして画像ファイルを生成する必要があります。

以下の手順で目的を達成できます。

1. 画像をエンコードする。  
2. エンコードされた画像データの文字列を LaTeX ファイルに挿入する。  
3. 文字列を外部ファイルに書き出す。  
4. 手順 3 で作成した外部ファイルをデコードする。  
5. デコードされた画像を取り込む。

最初の 2 つの手順は LaTeX ファイルの作者が行い、残りの手順は TeX エンジンが適切に指示されれば自動で処理します。

では **ステップ 1** に進みましょう。画像を文字列に変換する方法として最も一般的なのは **Base64** です。

## Base64 を使用したバイナリデータのエンコード

[**Base64**](https://en.wikipedia.org/wiki/Base64) は、バイナリデータを印字可能な文字列に変換するエンコーディング方式のひとつです。6 ビットずつに区切られたデータが 64 種類の固有文字にマッピングされます。すべてのバイナリ‑テキストエンコーディング方式と同様に、テキスト主体の通信路でバイナリデータを安全に転送することを目的としています。

この説明から、**Base64** がまさに必要なものだと分かります。画像ファイルを **Base64** にエンコードするには、コマンドラインユーティリティ（OS によっては標準で利用可能）、ほぼすべてのプログラミング言語が提供する標準またはサードパーティの機能、あるいは [Base64.guru](https://base64.guru/converter/encode/file) などのオンラインツールを使用できます。

## エンコードした画像を LaTeX ファイルに埋め込む

エンコードされた文字列は、LaTeX の標準 `filecontents` 環境内に配置します。例は次のとおりです。

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

これで **ステップ 2** は完了です。画像が LaTeX ファイルに埋め込まれました。では、組版時に何が起こるでしょうか？

LaTeX プロセッサは、`filecontents` 環境の文字列を外部ファイル `sample-image.64` に書き出します。`overwrite` オプションが指定されているため、既に同名ファイルが存在すれば上書きされます。これが **ステップ 3** の役割です。

## Base64 文字列のデコード

**ステップ 4** では、TeX 実装の違いによりデコード方法が変わります。デコードは主に `\write18` 機能を使って行います。

### `\write18`

従来の TeX エンジンでは、`\write<number>(<token list>)` がトークンリストを書き出すプリミティブです。`<number>` が負の場合はログファイルに、`>15` の場合は端末に、`0..15` の場合は事前に `\openout` で割り当てられたファイルに書き出されます。

PDFTeX などの新しい実装では `\write18` が使用可能で、`<token list>` を OS のシェルコマンドとして実行します。この機能はセキュリティリスクを伴うため、使用可否はオプションで制御できます。

通常、以下の 3 つのアクセスレベルが提供されます：無効、制限付き有効、完全に有効。

**Aspose.TeX** では `ShellMode` という TeX ジョブオプションがあり、`NoShellEscape` と `ShellRestricted` の 2 つの値を取ります。`NoShellEscape` は機能が無効であることを示し、`ShellRestricted` はユーザーが `Executable` クラスの拡張としてコマンドを実装する必要があることを示します。`base64` コマンドのエミュレーションはすでに Aspose.TeX に実装されており、`TeXOptions` の `Executables` コレクションにデフォルトで含まれています。 組み込みの `base64` エミュレーションは Aspose.TeX 内で実行されるため、OS の Base64 ユーティリティは不要です。

### Base64 データのデコード

Base64 エンコードされたデータが入ったファイルをデコードするには、通常次のコマンドを使用します。

```
base64 -d  FILE1 > FILE2
```

ここで `FILE1` がエンコードされたファイルで、`> FILE2` が出力先ファイルです。

したがって、LaTeX ファイル本体には次の行を追加します。

```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> `\immediate` プレフィックスは、TeX スキャナがこのプリミティブに遭遇した瞬間に `\write` 操作を実行させるために必要です。省略するとページの出力時に処理されます。

この状態で組版を実行すると、`sample-image.png` が生成されます。ビューアで開いて確認してください。

## デコードした画像の取り込み

冒頭で述べたように、デコードされた画像は標準の LaTeX コマンド `\includegraphics` で取り込みます。

```tex
\includegraphics[options]{sample-image.png}
```

次の例は文書の構造を示します。省略した Base64 行を完全な画像データに置き換えてください。点はプレースホルダーであり、デコードできません。

```tex
\documentclass{article}
\usepackage{graphicx}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \immediate\write18{base64 -d sample-image.64 > sample-image.png}
  \includegraphics[width=\textwidth]{sample-image.png}
\end{document}
```

Java の例は完全な `embedded-base64-image.tex` 文書を PDF に変換します。`inputFile` に入力の完全パス、`outputDirectory` に既存の出力フォルダーを指定します。使用する `com.aspose.tex` クラス、`com.aspose.tex.rendering.PdfDevice`、`com.aspose.tex.rendering.PdfSaveOptions` をインポートし、例外を処理または宣言してください。[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用します。組み込み Base64 コマンド用に `ShellRestricted` を有効にし、対話なしで処理して端末出力をメモリに保存します。PDF デバイスと出力ディレクトリはジョブ終了後に解放または閉じます。出力フォルダーには `sample-image.64`、デコードした `sample-image.png`、PDF、TeX ログが生成されます。

{{< gist "aspose-com-gists" "e17f869aabed3881c74973f5e875d539" "Example-EmbeddedBase64Image.java" >}}

これで **ステップ 5** が完了です。さらに詳しいサンプルは、[Example project](https://github.com/aspose-tex/Aspose.TeX-for-Java) をご覧ください。

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースに構築された無料変換 [web アプリ](https://products.aspose.app/tex/conversion/latex/) もお試しください。**
