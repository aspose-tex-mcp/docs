---
translation: true
template: /templates/_template-python-net.md
title: LaTeX 数式のレンダリング | Python via .NET
linktitle: LaTeX 数式のレンダリング
weight: 10
url: /python-net/latex-math-formula-rendering/
description: 記事では、Python 用 Aspose.TeX API ソリューションの概要と LaTeX 数式のレンダリング機能について紹介します。コード例をご覧ください
lastmod: "2026-02-27"
---

{{<section overview>}}

## PNG に LaTeX 数式をレンダリングする

必要に応じて、[このトピックのAPIリファレンスセクション](https://reference.aspose.com/tex/python-net/aspose.tex.features/)をご覧ください。実際、**LaTeX数式**レンダリング機能を理解するには、まず例を挙げるのが最も効果的です。以下に例を示します。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

詳細を見ていきましょう。まず、TeX/LaTeXタイプセッティングに似た[レンダリングオプション](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/)オブジェクトを初期化します。このオブジェクトには、必要な出力画像解像度の指定が含まれています。

次に、プリアンブルを指定します。デフォルトのプリアンブルは次のとおりです。


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

これは、標準的なLaTeXに比べて数式のサポートが強化されています。例えば、提供されているコード例に示すように、`color`パッケージをインクルードすることで、数式内のハイライト表示をカスタマイズできます。

次に、レンダラーに出力を300%に拡大するように指示します。

次の2つのオプションは、前景色と背景色を決定します。数式の中でカスタムハイライトの影響を受けない部分は、`TextColor`カラーで表示されます。

例の次の行は、ログ出力を特定のストリームにリダイレクトするオプションがあることを示しています。

最後に、`ShowTerminal` オプションを使用すると、ターミナル出力をコンソールに表示するかどうかを制御できます。

実際のレンダリング処理は [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/) メソッドによって実行され、数式のサイズをポイント単位で返します。

このメソッドは、画像を書き込むストリームを第2引数として受け取ります。その後、ストリームの作成に進みます。

最後に、`MathRenderer.render()` メソッドが呼び出され、オプションが3番目の引数として渡されます。数式の LaTeX コードは1番目の引数として提供されます。

例の最後の行には、数式レンダリング処理の2つの出力（数式のサイズと、エラーが発生した場合の簡潔なエラーレポート）が表示されます。

レンダリングの結果は次のとおりです。

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![LaTeX 数式を PNG にレンダリング](/tex/images/python-net/math-formula.png)</a>

これは、**LaTeX 数式レンダリング** 機能の最も一般的で幅広い応用例です。

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) の実装機能を活用した無料の[Webアプリ](https://products.aspose.app/tex/equation-editor/png)もお試しください。**

## SVG に LaTeX 数式をレンダリングする

同様に、同じ方法でLaTeXの数式をSVG形式に変換できます。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

違いは以下のとおりです。

* [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) クラスの代わりに、[SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/) クラスを使用します。
* 解像度は指定しません。
* [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) クラスの代わりに、[SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/) クラスを使用します。

結果は以下のとおりです。

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![LaTeX 数式を SVG にレンダリング](/tex/images/python-net/math-formula.svg)</a>

**[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) の実装機能を活用した無料の [Web アプリ](https://products.aspose.app/tex/equation-editor/svg) もお試しください。**
< A href ="/ tex/ pyth
