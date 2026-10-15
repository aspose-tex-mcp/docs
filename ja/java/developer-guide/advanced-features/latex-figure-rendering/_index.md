---
translation: true
template: /templates/_template-java.md
title: LaTeX 図のレンダリング | Aspose.TeX for Java
linktitle: LaTeX 図のレンダリング
weight: 20
url: /java/latex-figure-rendering/
description: Aspose.TeX API ソリューション for Java の LaTeX フラグメント（図）レンダリングについて説明しています。機能の使用方法に関するコード例をご覧ください。
lastmod: "2026-02-27"
---

{{<section overview>}}

LaTeX ファイルからコンテンツ（図形、文章、プロット等）を別々にレンダリングされたパーツ、つまり *「図」* として抽出したい場合があります。たとえば、インターネット上で公開する出版物のイラストの場合です。弊社の API がこのタスクを支援します。利用できる出力形式は PNG と SVG の 2 種類です。LaTeX 数式のレンダリングと同様です。また、**LaTeX 図のレンダリング**は [LaTeX 数式のレンダリング](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/) の一般化であることに留意してください。

## LaTeX 図を PNG にレンダリングする方法

数式レンダリングと同様に、例から始めます。以下がその例です。

`outputFile` に、既存フォルダー内の `java.nio.file.Path` を設定してください。例：PNG は `Paths.get(outputDirectory, "text-and-formula.png")`、SVG は `Paths.get(outputDirectory, "text-and-formula.svg")`。使用する Aspose.TeX のレンダラー、オプション、`Size2D` のクラスと `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths` をインポートします。呼び出し元のメソッドでは例外を処理するか、スローする例外として宣言してください。評価版の制限を避けるには、[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用します。

{{< gist "aspose-com-gists" "4598064edf58fab0b87d9543a4a88234" "Example-RenderFigureToPNG.java" >}}

まず、[レンダリング オプション](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/) インスタンスを作成します。ここで出力画像の解像度も指定します。

次に、前文（preamble）を指定します。LaTeX 図のレンダリングにはデフォルトの前文がありません。そのため、たとえば `pict2e` パッケージを使用したグラフを描画したい場合は、前文に以下のように記述する必要があります。

```tex
\usepackage{pict2e}
```

その後、レンダラに出力を 300% に拡大するよう指示します。 また、`setMargin(5)` で図の周囲に 5 ポイントの余白を設定します。PNG の例では 150 DPI を使用します。

次のオプションは背景色を定義します。数式レンダリングとは異なり、前景色は指定しません。なぜなら、色はすべて LaTeX のコードで制御されていると想定しているからです。背景色も同様に LaTeX が管理するため、これは便利なオプションにすぎません。

この例では `setLogStream()` を使い、レンダリングのログを `ByteArrayOutputStream` に書き込みます。ログと画像の出力ストリームはレンダリング後に自動的に閉じられます。

`showTerminal()` はコンソールへのターミナル出力を制御します。例では `false` に設定しています。表示するには `true` に設定してください。

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) は `PngFigureRenderer` または `SvgFigureRenderer` のインスタンスで呼び出し、図の寸法をポイント単位の `Size2D` として返します。

メソッドの第 2 引数には画像の出力ストリームを渡します。この例では try-with-resources ブロックで開き、レンダリング後に閉じます。

最後にレンダラーのインスタンスで `render()` を呼び出します。第 1 引数は LaTeX 図、第 2 引数は画像の出力ストリーム、第 3 引数はレンダリングオプションです。

例の最後の行では、図のサイズとエラーレポート（エラーがある場合）という二つの情報を出力しています。

以下がレンダリング結果です。

![LaTeX Figure rendering to PNG](/tex/images/java/text-and-formula.png)

これは **LaTeX 図のレンダリング** 機能の最も一般的な使用例です。

## LaTeX 図を SVG にレンダリングする方法

ほぼ同様の手順で、LaTeX 図を SVG 形式にレンダリングできます。

{{< gist "aspose-com-gists" "4598064edf58fab0b87d9543a4a88234" "Example-RenderFigureToSVG.java" >}}

相違点は次のとおりです。

* [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) クラスを、[PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/) の代わりに使用します。
* 解像度を指定しません。
* [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) クラスを、[PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/) の代わりに使用します。

結果は以下の通りです。

<a href="/tex/images/java/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/images/java/text-and-formula.svg)</a>
