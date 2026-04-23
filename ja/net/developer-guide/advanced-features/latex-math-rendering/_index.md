---
translation: true
template: /templates/_template-net.md
title: ラテックス数学式レンダリング | Aspose.TeX for .NET
linktitle: ラテックス数学式レンダリング
weight: 10
url: /net/latex-math-formula-rendering/
description: .NETラテックス数学式レンダリング用のAspose.TeX APIソリューションについては、この記事で説明します。機能の使用方法に関するコードの例を学びます。
lastmod: "2026-04-22"
---

{{<section overview>}}



## ラテックス数学式を PNG にレンダリングする方法


このトピックに関連する API 参照セクションは[ここ](https://reference.aspose.com/tex/net/aspose.tex.features/)です。実際、**ラテックス数学式レンダリング**機能を実証する最も簡単な方法は、例から始めることです。ここにあります：

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderMathToPNG.cs" >}}

詳細について説明しましょう。まず、TeX/LaTeXタイプセットと同様に、[レンダリングオプション](https://reference.aspose.com/tex/net/aspose.tex.features/mathrendereroptions/)インスタンスを作成します。ここでは、出力画像解像度を同時に指定します。


次に、前文を指定します。デフォルトのプリアンブルは次のとおりです。
次に、プリアンブルを指定します。デフォルトのプリアンブルは次のとおりです。


```tex
\usepackage{amssymb}
```

基本的な LaTeX よりもやや高度な数式サポートを提供します。たとえば、コード例で示したように、式で独自のハイライトを使用したい場合は `color` パッケージを追加できます。

次に、レンダラーに出力を 300% スケーリングするよう指示します。

次の 2 つのオプションは、前景色と背景色を定義します。カスタムハイライトによって覆われていない（「色付き」）式の部分は `TextColor` で表示されます。

例の次の行はあまり意味がありませんが、ログ出力をストリームに向けられることを示しています。

そして最後のオプション `ShowTerminal` を使用すると、ターミナル出力の書き込みをコンソールに切り替えることができます。

実際にレンダリングを実行するメソッドは[MathRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/mathrenderer/render/)です。式のサイズをポイントで返します。

そして最後に、`MathRenderer.Render()` メソッド自体を第 3 引数としてオプションを渡し、式の LaTeX コードを第 1 引数として渡します。

例の最後の行では、数式レンダリングの 2 つの成果物（式のサイズと簡易エラーレポート）を出力します。

以下がレンダリング結果です。

<a href="/tex/net/latex-math-formula-rendering/math-formula.png">![LaTeX Math Formula rendering to PNG](/tex/images/net/math-formula.png)</a>

これは **LaTeX 数式レンダリング** 機能の最も一般的なユースケースです。

**[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) に実装された機能をベースに構築された無料の [Web アプリ](https://products.aspose.app/tex/equation-editor/png) もぜひご確認ください。**

## ラテックス数学式を SVG にレンダリングする方法

ほぼ同様に、LaTeX 数式を SVG 形式にレンダリングできます。

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderMathToSVG.cs" >}}

違いは次のとおりです。

* [SvgMathRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrendereroptions/) クラスを [PngMathRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrendereroptions/) の代わりに使用します。
* 解像度を指定しません。

* [SvgMathRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrenderer/) クラスを [PngMathRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrenderer/) の代わりに使用します。

以下が結果です：

<a href="/tex/net/latex-math-formula-rendering/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/images/net/math-formula.svg)</a>

**[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) に実装された機能をベースに構築された無料の [Web アプリ](https://products.aspose.app/tex/equation-editor/svg) もぜひご確認ください。**
