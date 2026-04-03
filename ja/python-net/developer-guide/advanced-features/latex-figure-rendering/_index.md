---
translation: true
template: /templates/_template-python-net.md
title: LaTeX 図のレンダリング | Python via .NET
linktitle: LaTeX 図の挿入
weight: 20
url: /python-net/latex-figure-rendering/
description: 本記事では、Python 用 Aspose.TeX API ソリューションと LaTeX フラグメント（図）のレンダリング機能の概要を示します。コード例をご覧ください。
keywords: LaTeX 図, LaTeX 図サイズ, LaTeX 画像, LaTeX ピクチャ, LaTeX 図の挿入, LaTeX ピク, LaTeX 図オプション
lastmod: "2026-04-03"
---

{{<section overview>}}

特定の状況では、LaTeX ファイルから特定のコンテンツを単独のレンダリングされた要素（一般に *図* と呼ばれます）として抽出する必要があるかもしれません。ページレイアウトとは無関係です。たとえばオンライン出版物のイラストを作成する際に役立ちます。当社の API を使用すればこれが可能です。図のレンダリング対象フォーマットは PNG と SVG で、LaTeX 数式レンダリング機能と同様です。**LaTeX 図のレンダリング** は、[LaTeX 数式レンダリング](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/) と比較して、より汎用的な機能であることに注意してください。

## LaTeX 図を PNG にレンダリングする

必要に応じて、まずこのトピックの [API リファレンス セクション](https://reference.aspose.com/tex/python-net/aspose.tex.features/) をご覧ください。数式レンダリングと同様に、例から始めます。以下です:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

最初に、[LaTeX 図レンダラーオプション](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/) クラスのインスタンスを作成し、同時に出力画像の解像度を指定します。

次に、プリアンブルを指定する必要があります。LaTeX 数式レンダリングとは異なり、LaTeX 図のレンダリングにはデフォルトのプリアンブルがありません。そのため、たとえば `pict2e` パッケージで作成されたグラフィックをレンダリングする場合は、プリアンブルにそれを指定する必要があります:

```tex
\usepackage{pict2e}
```

その後、レンダラーに出力を 300% に拡大するよう指示します。

次のオプションは背景色を決定します。数式レンダリングとは異なり、前景色を指定する必要はありません。色はすべて LaTeX コードで制御されていると想定しています。同様に背景色も LaTeX コードで制御されるため、このオプションは利便性のために用意されています。

例の次の行は特に意味があるわけではありません。ログ出力を特定のストリームに送るオプションがあることを示すためのものです。

最後のオプション `ShowTerminal` は、ターミナル出力をコンソールに表示するかどうかを制御できます。

図のレンダリングを担当するメソッドは [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/FigureRenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions) です。ポイント単位で図のサイズを返します。

このメソッドは第2引数としてストリームを受け取ります。画像が書き込まれるストリームです。次の行でストリームを作成します。

最後に、`FigureRenderer.render()` メソッド自体を呼び出し、オプションを第3引数として渡します。図の LaTeX コードは第1引数として提供されます。

例の最後の数行は、図のサイズと簡単なエラーレポート（エラーがある場合）という、図のレンダリングに関する 2 つの情報を表示します。

以下はレンダリング結果です。

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![LaTeX Figure rendering to PNG](/tex/images/python-net/text-and-formula.png)</a>

これは **LaTeX 図のレンダリング** 機能の最も一般的な使用例を表しています。

## LaTeX 図を SVG にレンダリングする

同様に、LaTeX 図を SVG 形式でもレンダリングできます。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

違いは次のとおりです：

* [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/) クラスの代わりに、[SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/) クラスを使用します。
* 解像度を指定する必要はありません。
* [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/) クラスの代わりに、[SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/) クラスを使用します。

結果は以下です：

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/images/python-net/text-and-formula.svg)</a>
