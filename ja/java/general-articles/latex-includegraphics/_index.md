---
translation: true
template: /templates/_template-java.md
linktitle: Graphicsを含む
title: ラテックスにはグラフィクスが含まれます
weight: 10
url: /java/latex-includegraphics/
keywords: インクルードグラフィクスのラテックス、ラテックスインクルードグラフィック、挿入イメージ、ラテックス、ラテックスグラフィック、インサート画像、インクルードグラフィックラテックスパッケージ、描画IOラテックス、ラテックスの描画幅、グラフィクスの幅、フィギュアスケールラテックス
description: ラテックスについては、画像変換、ビューポート、クリッピング、グラフィックスパッケージとGraphicXパッケージの違いとともに、Graphics Macroを含むことを含みます。
lastmod: "2025-06-09"
---

{{<section overview>}}

## 導入

研究論文、会議の手続き、学術的なプレゼンテーションなどの学術的および科学的文書に取り組んでいる間、グラフィックフィギュアを含めることがある場合があります。

一方では、これらは図面、プロット、ヒストグラム、または一般的にベクトルグラフィックと呼ばれる他の何かです。最新のラテックスシステム(「PDFTEX」など)は、ドキュメントにこのようなグラフィックを作成するための多くのツールを提供します。たとえば、 `pict2e`、` pgf(tikz) `および` pgfplots`パッケージ。ほとんどの場合、図自体はTEXエンジンによって生成され、出力ファイルに特定の出力形式に適したベクトルグラフィックス命令のシーケンスとして含まれています。

一方、出版物に含めたいラスター画像があるかもしれません。ラテックスシステムもこれを行うことができますが、LaTexファイルの画像ファイルへのパスをラテックスマクロのパラメーターとして指定する必要があります。

この記事では、「Graphics」(および添付の`graphicx`)パッケージの「increctgraphics」マクロを使用して、ラテックスファイルのラスター画像を含むことをカバーしています。

## 「グラフィックス」または`graphicx`を選択するパッケージはどれですか？

「グラフィックス」と`graphicx`の両方のパッケージは非常に似ています。主な違いは構文にあります。 「グラフィック」パッケージは個別のマクロのセットを使用して画像に変換を適用しますが、 `graphicx`パッケージは、これらの変換を指定するために` \ incremgraphics`マクロのパラメーターの「key = value」表記を使用します。両方のパッケージの各ユースケースの例を一度に示して、違いをより明確にします。

## 選択したパッケージを含む

これは、他のラテックスパッケージと同じ方法で「\ usePackage」コマンドで行われます。


```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### ドライバーの指定

タイプセットシステムがデフォルトで「PDFTEX」を使用するように構成されていない場合、パッケージに必要な「ドライバー」を使用するように強制する適切なオプションを指定する必要があります。


```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

「ドライバー」は、パッケージコマンドとフォーマット依存の低レベルTex拡張プリミティブとの間のインターフェイスを実装するパッケージの一部です。 **Aspose.TeX**のLaTexグラフィックサポートは、独自のドライバーを使用するように構成されているため、ドライバーオプションを指定する必要はありません。

## latex `\includegraphics`マクロ

それでは、最も簡単な例を進めましょう。これはもちろん、変換のない画像を含める場合です。予想されることに、両方のパッケージを使用してラテックスコードは同じです。


```tex
\includegraphics{sample-image.png}
```

この例では、画像ファイルがLaTexファイルと同じディレクトリにあることを前提としています。しかし、別の場所を指定する方法はいくつかあります。ラテックスコードは、両方のパッケージで再び同じになります。


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

グラフィックファイルの場所を指定する別の方法は、 `\ graphicspath`コマンドを使用して「\ inclutegraphics」を呼び出す前に、「\ graphicspath」コマンドを使用して代替パスのリストを定義することです。


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## ラテックスグラフィックスの変換

LaTex「Graphics」と`graphicx`パッケージは、コンテンツを操作するための多くの方法を提供します。

### スケールフィギュアラテックス

そのため、次のように、付属のグラフィックス(実際、Tex/Latexコードで説明されているものすべて)をスケーリングできます。


```tex
% graphics examples
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively

% graphicx examples
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
% there's no analogue for the graphicx package to scale both dimensions independently
```

### サイズのフィギュアラテックス

スケーリングに似ていますが、スケーリングファクターの代わりに必要なサイズを指定します。


```tex
% graphics examples
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently

% graphicx examples
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### 数字のラテックスを回転させます

```tex
% graphics example
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise

% graphicx example
\includegraphics[angle=-10]{sample-image.png} % rotates the image by 10 degrees clockwise
```

### ビューポートとクリッピングの設定

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

`graphicx`パッケージについては、変換を組み合わせることができますが、順序は重要です。
「グラフィック」パッケージバンドル機能の詳細については、[CTANのパッケージページ](https://ctan.org/pkg/graphics)を参照してください。
[パッケージドキュメント](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf)。

### ラテックスには、グラフィックフリーWebアプリが含まれます

Graphics Latexパッケージをプログラム的に扱いたくない場合は、[.NET API]の[Aspose.TeX](https://products.aspose.com/tex/net/)に基づいて構築された無料の[LaTex Include Graphics](https://products.aspose.app/tex/includegraphics/)Webアプリをチェックアウトすることもできます。 

このアプリを使用すると、複数の画像を選択し、それらの変換を視覚的に調整できます。また、 `graphicx`パッケージを使用してLaTexソースコードを生成し、ページに結果を表示するようにします。

### ラテックスフィギュアレンダリング機能Asopse.texライブラリ

**Aspose.TeX**ライブラリは、TEX/LaTexコンテキスト以外の出版物で使用できるラスターおよびSVGのフィギュアを作成する方法を提供します。たとえば、Webページで。これは**ラテックスフィギュアレンダリング**と呼ばれます。簡単に言えば、APIのこの部分を使用すると、ページレイアウトに関係なく、ラテックスソースコードのフラグメントをレンダリングできます。詳細については、この[記事](/tex/{{lang.url-fragment}}java/latex-figure-rendering/)を参照してください。

[外部ラテックスパッケージを含む](/tex/{{lang.url-fragment}}java/external-latex-packages/)に関する記事は、ラテックスプロットからフィギュアを作成する方法についての手がかりを与えることもできます。