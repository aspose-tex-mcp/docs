---
translation: true
template: /templates/_template-java.md
title: LaTeX グラフィックス | \includegraphics コマンド
linktitle: グラフィックス LaTeX を含める
weight: 18	
url: /net/latex-graphics/
description: TeX におけるグラフィックスの挿入は言及すべき重要な項目です。これについて語るとき、まず頭に浮かぶのは `\includegraphics` コマンドです。
lastmod: "2026-02-26"
---

{{<section overview>}}

実際、LaTeX グラフィックスには言及すべき 2 つの側面があります：

* LaTeX/TeX コマンドを直接用いて記述されたベクターグラフィックス、  
* EPS、PDF、またはラスター PNG や PDF などの外部フォーマットで記述された外部グラフィックスのインクルード。

前者はオリジナルの LaTeX とそのパッケージでのサポートが限定的です。TeX の垂直・水平ルールを利用して実装されています。これは、元の LaTeX が元の TeX エンジンに基づいており、主に *DVI* 形式で出力するため、線や曲線、あるいはバイナリのラスター画像データを表現するのに適さないからです。しかし、pdfTeX のようにグラフィックス対応形式（PDF など）への出力が可能なエンジンは、フォーマット依存のパッケージや機能を利用してグラフィックスを扱うことができます。同様の理由で、基本的な LaTeX では外部グラフィックスはサポートされていません。以下でグラフィックスのインクルード機能について説明します。

## LaTeX `graphics` パッケージと `\includegraphics` コマンド

LaTeX のグラフィックスインクルードについて語るとき、最初に思い浮かぶのは `\includegraphics` コマンドです。これは `graphics` パッケージで定義されており、機能を有効にするためにプリアンブルでこのパッケージを呼び出す必要があります。

```tex
\usepackage{graphics}
```

使用している組版システムがデフォルトで pdfTeX などになっていない場合は、必要な `driver` ファイルを強制的に使用させるオプションを指定してください。

```tex
\usepackage[pdftex]{graphics}
```

`driver` ファイルは、パッケージコマンドとフォーマット依存の低レベル TeX 拡張プリミティブとのインターフェイスを実装するパッケージの一部です。Aspose.TeX の LaTeX グラフィックスサポートは独自のドライバを使用するように設定されているため、ドライバオプションを指定する必要はありません。

さて、PNG 画像を挿入する最もシンプルな方法は次のように記述することです。

```tex
\includegraphics{sample-image.png}
```

ここで `sample-image.png` は挿入したいファイル名です。拡張子を省略することも可能です。`graphics` パッケージはサポートされているフォーマットの定義リストを保持しており、ファイル検索時にそのリストを走査して最初に一致したファイルをインクルードします。

絶対パスや相対パスでファイル名を指定することもできます:

```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

別の方法として、`\includegraphics` を呼び出す前に `\graphicspath` コマンドで代替パスのリストを定義することができます:

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### グラフィックスのスケーリング

LaTeX `graphics` パッケージはコンテンツを操作するコマンドを提供しています。そのため、以下のようにインクルードしたグラフィックス（実際には TeX/LaTeX コードで記述されたすべてのもの）を拡大縮小できます。

```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### グラフィックのサイズ変更

拡大縮小と似ていますが、拡大率ではなく必要なサイズを指定します。

```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### グラフィックの回転

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## LaTeX `graphicx` パッケージ

LaTeX `graphicx` パッケージは `key=value` インターフェイスを提供し、コンテンツ変換を簡単に行えるようにします。機能を有効にするには、プリアンブルでこのパッケージを呼び出してください。

```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

以下のオプションを任意に組み合わせることができますが、順序が重要であることに留意してください。


### グラフィックビューポート

```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### グラフィックのスケーリング
```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### グラフィックのサイズ変更

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### グラフィックの回転

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

`graphics` パッケージのバンドル機能の詳細については、ドキュメント [here](https://ctan.org/pkg/graphics) と [here](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf) を参照してください。

**[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) に基づいて構築された無料の変換 [Web アプリ](https://products.aspose.app/tex/conversion/latex/) も確認することができます。**
