---
translation: true
template: /templates/_template-java.md
linktitle: Includegraphics
title: LaTeX includegraphics | Aspose.TeX チュートリアル
weight: 10
url: /java/latex-includegraphics/
keywords: includegraphics latex、latex includegraphic、latex 画像の挿入、latex graphicx、latex 画像の挿入、includegraphics latex パッケージ、latex io の描画、latex includegraphics の幅、includegraphics の幅、latex の図のスケール
description: LaTeX の includegraphics マクロ、画像変換、ビューポート、クリッピング、graphics パッケージと graphicx パッケージの違いについて学びます。
lastmod: "2026-02-20"
---

{{<section overview>}}

## はじめに

学術論文、会議録、学術プレゼンテーションなどの文書を作成していると、図形を挿入したくなることがあります。

一方で、これらは図面、プロット、ヒストグラムなど、一般にベクターグラフィックと呼ばれるものです。現代の LaTeX システム（例: `pdfTeX`）は、文書中でそのようなグラフィックを作成するための多数のツールを提供しています。たとえば、`pict2e`、`PGF(TikZ)`、`PGFplots` パッケージがあります。多くの場合、図は TeX エンジンによって生成され、特定の出力形式に適したベクター指示として出力ファイルに組み込まれます。

もう一方で、ラスター画像を文書に挿入したい場合もあります。LaTeX システムは現在これもサポートしていますが、画像ファイルへのパスを LaTeX ファイル内のマクロにパラメータとして指定する必要があります。

本稿では、`graphics`（および付随する `graphicx`）パッケージの `\includegraphics` マクロを用いて、LaTeX ファイルにラスター画像を組み込む方法を解説します。

## どちらのパッケージを選ぶべきか、`graphics` と `graphicx`？

`graphics` と `graphicx` の両パッケージは非常に似ています。主な違いは構文にあります。`graphics` パッケージは画像の変換を適用するために個別のマクロの集合を使用しますが、`graphicx` パッケージは `\includegraphics` マクロのパラメータを `key=value` 形式で指定します。ここでは、両パッケージの使用例を同時に示し、違いを分かりやすくします。

## 必要なパッケージの導入

他の LaTeX パッケージと同様に、`\usepackage` コマンドで行います。

```tex
\usepackage{graphics} % graphics パッケージを使用
\usepackage{graphicx} % graphicx パッケージを使用
```

### ドライバの指定

使用している組版システムがデフォルトで `pdfTeX` などになっていない場合は、パッケージに適切な `driver` オプションを指定してください。

```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

`driver` は、パッケージコマンドとフォーマット依存の低レベル TeX 拡張プリミティブとのインターフェースを実装するパッケージの一部です。**Aspose.TeX** の LaTeX グラフィックサポートは独自のドライバを使用するように設定されているため、ドライバオプションを指定する必要はありません。

## LaTeX `\includegraphics` マクロ

まずは最もシンプルな例から始めます。これは変換を全く行わずに画像を挿入するケースです。期待通り、両パッケージでの LaTeX コードは同じです。

```tex
\includegraphics{sample-image.png}
```

この例は、画像ファイルが LaTeX ファイルと同じディレクトリにあることを前提としています。別の場所にある画像を指定する方法はいくつかあります。両パッケージでのコードは同じです。

```tex
\includegraphics{d:/sample-image.png} % 絶対パス
\includegraphics{./sample-image.png} % カレントディレクトリからの相対パス
\includegraphics{../img/sample-image.png} % 現在のディレクトリの親ディレクトリ内の img フォルダからの相対パス
```

画像ファイルの検索パスを事前にリストとして定義することもできます。その場合は `\graphicspath` コマンドを `\includegraphics` の呼び出し前に置きます。

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## LaTeX のグラフィック変換

`graphics` と `graphicx` パッケージは、内容を操作するためのさまざまな方法を提供します。

### 図のスケーリング

以下のように、含めた画像（実際には TeX/LaTeX コードで記述されたすべてのもの）をスケールできます。

```tex
% graphics の例
\scalebox{.5}{\includegraphics{sample-image.png}} % 幅と高さを 0.5 倍に縮小
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % 幅を 0.5 倍、高さを 1.5 倍に縮小

% graphicx の例
\includegraphics[scale=.5]{sample-image.png} % 幅と高さを 0.5 倍に縮小
% graphicx には幅と高さを個別にスケールする直接的な対応はありません
```

### 図のリサイズ

スケーリングに似ていますが、倍率ではなく目的とするサイズを指定します。

```tex
% graphics の例
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % 幅を 10mm に変更し、比率は保持
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % 幅と高さを個別に変更

% graphicx の例
\includegraphics[width=15mm]{sample-image.png} % 幅を 15mm に変更し、比率は保持
\includegraphics[height=15mm,width=25mm]{sample-image.png} % 幅と高さを個別に変更
```

### 図の回転

```tex
% graphics の例
\rotatebox{25}{\includegraphics{sample-image.png}} % 画像を反時計回りに 25 度回転

% graphicx の例
\includegraphics[angle=-10]{sample-image.png} % 画像を時計回りに 10 度回転
```

### ビューポートとクリッピングの設定

```tex
% graphics パッケージには対応する機能がありません

% graphicx の例
\includegraphics[viewport=10 10 280 220]{sample-image.png} % 左下隅が (10, 10) （ボックスの (0, 0) と一致）で、幅 280pt・高さ 220pt のビューポートを設定
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % 同上だが、ビューポートで画像をクリップ
```

`graphicx` パッケージでは、変換を組み合わせることができますが、順序は重要です。

`graphics` パッケージの機能詳細については、[CTAN のパッケージページ](https://ctan.org/pkg/graphics) と
[パッケージのドキュメント](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf) を参照してください。

### LaTeX Include Graphics 無料ウェブアプリ

プログラムから `includegraphics` LaTeX パッケージを操作したくない場合は、無料の [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics/) ウェブアプリも試してみてください。このアプリは [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースに構築されています。

このアプリでは複数の画像を選択し、視覚的に変換を調整できます。また、`graphicx` パッケージを使用した LaTeX ソースコードを生成し、ページ上で結果を表示します。

### Aspose.TeX ライブラリの LaTeX 図描画機能

**Aspose.TeX** ライブラリは、TeX/LaTeX のコンテキスト外（例: Web ページ）で使用できるラスターや SVG の図を作成する手段を提供します。この機能は **LaTeX Figure Rendering** と呼ばれます。簡単に言えば、ページレイアウトに関係なく LaTeX ソースコードの断片を描画できる API です。詳細は、この記事 [article](/tex/{{lang.url-fragment}}java/latex-figure-rendering/) をご覧ください。

[外部 LaTeX パッケージの導入に関する記事](/tex/{{lang.url-fragment}}java/external-latex-packages/) でも、LaTeX プロットから図を作成する手順のヒントが得られます。
