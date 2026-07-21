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

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

まず、[レンダリング オプション](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/) インスタンスを作成します。ここで出力画像の解像度も指定します。

次に、前文（preamble）を指定します。LaTeX 図のレンダリングにはデフォルトの前文がありません。そのため、たとえば `pict2e` パッケージを使用したグラフを描画したい場合は、前文に以下のように記述する必要があります。

```tex
\usepackage{pict2e}
```

その後、レンダラに出力を 300% に拡大するよう指示します。

次のオプションは背景色を定義します。数式レンダリングとは異なり、前景色は指定しません。なぜなら、色はすべて LaTeX のコードで制御されていると想定しているからです。背景色も同様に LaTeX が管理するため、これは便利なオプションにすぎません。

例の次の行はあまり意味がありませんが、ログ出力を任意のストリームにリダイレクトできることを示しています。

最後のオプション `ShowTerminal` は、ターミナル出力をコンソールに表示するかどうかを切り替えるものです。

実際にレンダリングを実行するメソッドは [FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) です。このメソッドは図のサイズ（ポイント単位）を返します。

画像を書き込むストリームは、メソッドの第2引数として受け取ります。次にそのストリームを作成します。

最後に、`FigureRenderer.render()` メソッドを呼び出し、3 番目の引数にオプションを渡します。図の LaTeX コードは最初の引数として渡します。

例の最後の行では、図のサイズとエラーレポート（エラーがある場合）という二つの情報を出力しています。

以下がレンダリング結果です。

![LaTeX Figure rendering to PNG](/tex/images/java/text-and-formula.png)

これは **LaTeX 図のレンダリング** 機能の最も一般的な使用例です。

## LaTeX 図を SVG にレンダリングする方法

ほぼ同様の手順で、LaTeX 図を SVG 形式にレンダリングできます。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

相違点は次のとおりです。

* [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) クラスを、[PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/) の代わりに使用します。
* 解像度を指定しません。
* [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) クラスを、[PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/) の代わりに使用します。

結果は以下の通りです。

<a href="/tex/images/java/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/images/java/text-and-formula.svg)</a>
