---
translation: true
template: /templates/_template-net.md
title: LaTeX 図レンダリング | Aspose.TeX for .NET
linktitle: LaTeX 図の追加
weight: 20
url: /net/latex-figure-rendering/
description: この記事では、.NET LaTeX フラグメント（図）レンダリングのための Aspose.TeX API ソリューションについて説明します。コード例を用いて、この機能の使用方法をご確認ください。
keywords: LaTeX 図、LaTeX 図サイズ、LaTeX 画像、LaTeX 画像、LaTeX include figure、LaTeX 画像、LaTeX 図オプション
lastmod: "2026-02-25"
---

{{<section overview>}}


時々、LaTeX ファイルからコンテンツを抽出して、ページレイアウトとは無関係に別々にレンダリングされた *「図」* として扱いたいことがあります。たとえば、インターネット上の出版物のイラストにすることができます。これを当社の API で実現できます。対象フォーマットは PNG と SVG の 2 つがあります。LaTeX 数式レンダリング機能と同様です。また、**LaTeX 図のレンダリング**は [LaTeX 数式レンダリング](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) の一般化であることにも留意してください。

## LaTeX 図を PNG にレンダリングする方法

このトピックに関する API リファレンスセクションは [こちら](https://reference.aspose.com/tex/net/aspose.tex.features/) です。数式レンダリングと同様に、例から始めます。以下が例です：

{{< gist "aspose-com-gists" "79be6a0d7a31aa5deb213ba4ca81cb1b" "Example-RenderFigureToPNG.cs" >}}

まず、[LaTeX 図オプション](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/) のインスタンスを作成します。ここで出力画像の解像度も同時に指定します。

次に、プレアンブルを指定します。LaTeX 図のレンダリングにはデフォルトのプレアンブルがないため、たとえば `pict2e` LaTeX パッケージを使用して描画したグラフィックをレンダリングする場合は、プレアンブルで指定する必要があります：

```tex
\usepackage{pict2e}
```

次に、レンダラに出力を 300% に拡大するよう指示します。

次のオプションは背景色を定義します。数式レンダリングとは異なり、前景色は指定しません。なぜなら、色はすべて LaTeX コード側で制御されていると想定しているからです。実際、背景色も同様で、これは単なる便利なオプションです。

例の次の行はあまり意味がありません。単にログ出力をストリームに向けることができることを示しています。

そして最後のオプション `ShowTerminal` は、ターミナル出力をコンソールに書き込むかどうかを切り替えることができます。

実際にレンダリングを行うメソッドは [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/) です。これは図のサイズをポイント単位で返します。

画像を書き込むストリームはメソッドの第2引数として受け取ります。次にストリームを作成します。

最後に、`FigureRenderer.Render()` メソッド自体を呼び出し、オプションを第3引数として渡します。図の LaTeX コードは第1引数として渡されます。

例の最後の行は、図のレンダリング結果として 2 つの情報—図のサイズと簡易エラーレポート（エラーがある場合）—を出力します。

以下はレンダリング結果です。

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![LaTeX Figure rendering to PNG](/tex/images/net/text-and-formula.png)</a>

これは **LaTeX 図のレンダリング** 機能の最も汎用的な使用例です。

## LaTeX 図を SVG にレンダリングする方法

同様の方法で、LaTeX 図を SVG 形式でレンダリングできます。

{{< gist "aspose-com-gists" "79be6a0d7a31aa5deb213ba4ca81cb1b" "Example-RenderFigureToSVG.cs" >}}

相違点は次のとおりです：

* 私たちは [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) クラスを使用し、[PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/) の代わりに使用します。
* 解像度は指定しません。
* 私たちは [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) クラスを使用し、[PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/) の代わりに使用します。

結果は以下の通りです：

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/images/net/text-and-formula.svg)</a>
