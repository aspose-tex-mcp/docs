---
translation: true
template: /templates/_template-net.md
title: ラテックスフィギュアレンダリング| .netのAspose.TeX
linktitle: ラテックスには図が含まれています
weight: 20
url: /net/latex-figure-rendering/
description: .NETラテックスフラグメント(図)レンダリング用のAspose.TeX APIソリューションについては、この記事で説明します。機能の使用方法に関するコードの例を学びます。
keywords: ラテックスフィギュア、フィギュアサイズのラテックス、ラテックス画像、ラテックス画像、ラテックスにはフィギュア、ラテックス写真、ラテックスフィギュアオプションが含まれます
lastmod: "2025-06-09"
---

{{<section overview>}}


ページレイアウトに接続せずに、個別にレンダリングされたピース、または *"figure"*として、LaTexファイルからコンテンツを抽出する場合があります。たとえば、インターネット上での出版物のイラストになる可能性があります。 APIで行うことができます。ターゲット形式については、PNGとSVGの2つのオプションがあります。ラテックス数学式レンダリング機能の場合と同様です。また、**ラテックスフィギュアレンダリング**は[ラテックス数学式レンダリング](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/)の一般化であることも注目に値します。

## ラテックスフィギュアをPNGにレンダリングする方法

このトピックに関連するAPI参照セクションは[ここ](https://reference.aspose.com/tex/net/aspose.tex.features/)です。また、式レンダリングと同様に、例から始めます。ここにあります：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.cs" >}}

まず、[LaTexフィギュアオプション](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/)インスタンスを作成します。ここでは、出力画像解像度を同時に指定します。

次に、前文を指定します。ラテックスフィギュアレンダリングにはデフォルトのプリアンブルはありません。たとえば、 `pict2e`ラテックスパッケージを使用してプロットされたグラフィックをレンダリングする場合は、preambleで指定する必要があります。


```tex
\usepackage{pict2e}
```

次に、レンダラーに出力を300％スケーリングするよう指示します。

次のオプションは、背景色を定義します。数学の式レンダリングとは異なり、色は完全にラテックスコードの制御下にあると仮定するため、前景の色を指定しません。実際、背景色もそうですので、これは単なる便利なオプションです。

例の次の行はあまり意味がありません。ログ出力をストリームに向けることができることを示しています。

また、最後のオプション「showterminal」を使用すると、ターミナル出力の書き込みをコンソールに切り替えることができます。

実際にレンダリングを実行する方法は[figurerenderer.render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/)です。フィギュアのサイズをポイントで返します。

画像が記述されるストリームは、2番目の引数としてメソッドによって受け入れられます。次にストリームを作成します。

そして最後に、 `figurerenderer.render()`メソッド自体を3番目の引数として渡すオプションを呼び出します。図のラテックスコードは、最初の引数として渡されます。

この例の最後の行には、図のレンダリングの2つのアーティファクトが印刷されています。図のサイズと簡単なエラーレポート(エラーがある場合)。

レンダリングの結果です。

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![ラテックスフィギュアはPNGにレンダリングします](/tex/images/net/text-and-formula.png)</a>

これは、**LaTexフィギュアレンダリング**機能の最も一般的なユースケースです。

## ラテックスフィギュアをSVGにレンダリングする方法

ほぼ同じように、SVG形式でラテックスフィギュアをレンダリングできます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.cs" >}}

違いは次のとおりです。

* [pngfigurerenderereroptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/)の代わりに[svgfigurerenderereroptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/)クラスを使用します。
* 解決策は指定しません。
* [pngfigurerenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/)の代わりに[svgfigurerenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/)クラスを使用します。
 
これが結果です：

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![ラテックスフィギュアはSVGにレンダリングします](/tex/images/net/text-and-formula.svg)</a>