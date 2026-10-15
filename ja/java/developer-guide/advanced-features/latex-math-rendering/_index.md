---
translation: true
template: /templates/_template-java.md
title: LaTeX 数式レンダリング | Aspose.TeX for Java
linktitle: LaTeX 数式レンダリング
weight: 10
url: /java/latex-math-formula-rendering/
description: Aspose.TeX API for Java における LaTeX 数式レンダリングについて説明します。機能の使用方法のコード例をご覧ください。
lastmod: "2026-02-27"
---

{{<section overview>}}

## LaTeX 数式を PNG にレンダリングする方法

実際、**LaTeX 数式** レンダリング機能を示す最も簡単な方法はサンプルから始めることです。こちらがその例です:

`outputFile` に、既存フォルダー内の `java.nio.file.Path` を設定してください。例：PNG は `Paths.get(outputDirectory, "math-formula.png")`、SVG は `Paths.get(outputDirectory, "math-formula.svg")`。使用する Aspose.TeX のレンダラー、オプション、`Size2D` のクラスと `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths` をインポートします。呼び出し元のメソッドでは例外を処理するか、スローする例外として宣言してください。評価版の制限を避けるには、[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用します。

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

詳細に入ります。まず、TeX/LaTeX の組版と同様に [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/) インスタンスを作成します。ここでは同時に出力画像の解像度も指定しています。

次に、プリアンブルを指定します。デフォルトのプリアンブルは次のとおりです:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

これは基本的な LaTeX より多少高度な数式サポートを提供します。例えば、独自のハイライトを数式内で使用したい場合は `color` パッケージを追加できます（コード例に示しています）。

続いて、レンダラに出力を 300% に拡大するよう指示します。

2 つのオプションで前景色と背景色を設定します。独自のハイライトを適用していない数式の部分には、`setTextColor()` で設定した色が使われます。

この例では `setLogStream()` を使い、レンダリングのログを `ByteArrayOutputStream` に書き込みます。ログと画像の出力ストリームはレンダリング後に自動的に閉じられます。

`showTerminal()` はコンソールへのターミナル出力を制御します。例では `false` に設定しています。表示するには `true` に設定してください。

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) は `PngMathRenderer` または `SvgMathRenderer` のインスタンスで呼び出し、数式の寸法をポイント単位の `Size2D` として返します。

メソッドの第 2 引数には画像の出力ストリームを渡します。この例では try-with-resources ブロックで開き、レンダリング後に閉じます。

最後にレンダラーのインスタンスで `render()` を呼び出します。第 1 引数は LaTeX 数式、第 2 引数は画像の出力ストリーム、第 3 引数はレンダリングオプションです。

例の最後の行は、数式レンダリングの成果物である式のサイズと簡易エラーレポート（エラーがあった場合）を出力します。

以下がレンダリング結果です。

<a href="/tex/images/java/math-formula.png">![LaTeX Figure rendering to PNG](/tex/images/java/math-formula.png)</a>

これは **LaTeX 数式** レンダリングの最も一般的な使用例です。

**無料の [web app](https://products.aspose.app/tex/equation-editor/png) もご確認ください。この機能は [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API で実装されています。Java バージョンのページは [こちら](https://products.aspose.com/tex/java/)。**

## LaTeX 数式を SVG にレンダリングする方法

ほぼ同様の手順で、LaTeX 数式を SVG 形式でレンダリングできます。

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

主な違いは以下の通りです:

* [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) クラスを使用し、[PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/) の代わりに使用します。
* 解像度を指定しません。
* [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) クラスを使用し、[PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/) の代わりに使用します。

以下が結果です:

<a href="/tex/images/java/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/images/java/math-formula.svg)</a>

**無料の [web app](https://products.aspose.app/tex/equation-editor/svg) もご確認ください。この機能は [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) で実装されています。**
