---
translation: true
template: /templates/_template-java.md
title: ラテックスグラフィックス| \ includegraphicsコマンド
linktitle: インクルードグラフィクスのラテックス
weight: 18
url: /net/latex-graphics/
description: Texにグラフィックを含めることは、言及する価値のある問題です。それについて話すとき、最初に思い浮かぶのは、「includegraphics」コマンドです。
lastmod: "2025-06-09"
---

{{<section overview>}}

実際、LaTexグラフィックスには言及する価値がある2つの側面があります。

* ラテックス/Texコマンドによって直接記述されたベクトルグラフィックスと
* EPS、PDF、またはラスターPNG、PDFなどの外部形式によって記述された外部グラフィックを含める。

前者は、元のラテックスとそのパッケージでのサポートが限られています。 Texの垂直および水平方向のルールの助けを借りて実装されています。これは、元のラテックスが元のTexエンジンに基づいているためです。これは、 * dvi *形式でメイン出力を生成します。しかし、グラフィックスサポート形式(PDFTEXからPDFなど)に出力できるエンジンは、形式に依存したパッケージまたはパッケージ機能を使用してグラフィックを扱うこともできます。後者のグラフィックは、同じ理由で基本的なラテックスではサポートされていません。グラフィックインクルージョン機能については、以下で説明します。

## ラテックス「グラフィックス」パッケージと `\ includegraphics`コマンド

ラテックスグラフィックスの包含について話すとき、最初に思い浮かぶのは「includegraphics」コマンドです。 「グラフィックス」パッケージで定義されています。これは、その機能を有効にするために前文で言及する必要があります。

```tex
\usepackage{graphics}
```

タイプセットシステムがデフォルトでPDFTEXを使用するように構成されていない場合、パッケージに必要な「ドライバー」ファイルを使用するように強制する適切なオプションを指定する必要があります。


```tex
\usepackage[pdftex]{graphics}
```

「ドライバー」ファイルは、パッケージコマンドとフォーマット依存の低レベルTex拡張プリミティブとの間のインターフェイスを実装するパッケージの一部です。 Aspose.TeXのLaTexグラフィックサポートは、独自のドライバーを使用するように構成されているため、ドライバーオプションを指定する必要はありません。

これで、たとえば、PNG画像を含める最も簡単な方法は、次のように入力することです。


```tex
\includegraphics{sample-image.png}
```

ここで、 `sample-image.png`は、含めるファイルの名前です。拡張機能を編集することもできます。 「グラフィック」パッケージには、サポートされている形式の定義のリストが含まれています。ファイルを探すとき、それはそのリストを通過し、見つかった最初の一致するファイルを含みます。

絶対的または相対パスを使用して、完全なファイル名を指定することもできます。


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

グラフィック ファイルの場所を指定する別の方法は、`\includegraphics` を呼び出す前に `\graphicspath` コマンドを使用して代替パスのリストを定義することです。


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### グラフィックスのスケーリング

LaTeXの`graphics`パッケージは、コンテンツを操作するためのコマンドを提供します。そのため、以下のようにして、含まれるグラフィック（実際にはTeX/LaTeXコードで記述されたあらゆるもの）を拡大縮小できます。


```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### グラフィックのサイズ変更

スケーリングに似ていますが、スケーリングファクターの代わりに必要なサイズを指定します。


```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### グラフィックスの回転

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## ラテックス`graphicx`パッケージ

LaTeXの`graphicx`パッケージは、コンテンツ変換のための`key=value`インターフェースを提供します。この機能を有効にするには、プリアンブルで次のように記述する必要があります。


```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

次のオプションのいずれかを組み合わせることができますが、順序が重要であることに留意してください。

### グラフィックビューポート
```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### グラフィックスのスケーリング

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### グラフィックスのサイズ変更

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### グラフィックスの回転

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

「グラフィック」パッケージバンドル機能の詳細については、ドキュメント[こちら](https://ctan.org/pkg/graphics)を参照してください。
[ここ](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf)。

**[.NET APIのAspose.TeX](https://products.aspose.com/tex/net/)に基づいて構築されたフリーコンバージョン[Webアプリ](https://products.aspose.app/tex/conversion/latex/)をチェックアウトすることもできます。**