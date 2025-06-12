---
translation: true
template: /templates/_template-java.md
title: ラテックスフィギュアレンダリング| Java用のAspose.TeX
linktitle: ラテックスフィギュアレンダリング
weight: 20
url: /java/latex-figure-rendering/
description: JavaラテックスフラグメントのAspose.TeX APIソリューション(図)レンダリングについては、この記事で説明します。機能の使用方法に関するコードの例を学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}

出力ドキュメントページのその場所に関係なく、ラテックスファイルから個別にレンダリングされたピース、または *"figure"*として、いくつかのコンテンツ(図面、書き込み、プロットなど)を抽出することができます。たとえば、インターネット上での出版物のイラストが当てはまります。私たちのAPIはタスクを支援します。 PNGとSVGの2つの使用可能なターゲット形式があります。ラテックス数学の式レンダリングのように。また、**ラテックスフィギュアレンダリング**は[ラテックス数学式レンダリング]の一般化であることに注意する必要があります(1)。

## ラテックスフィギュアをPNGにレンダリングする方法

また、式レンダリングと同様に、例から始めます。ここにあります：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

まず、[レンダリングオプション](https://reference.aspose.com/tex/java/com.Aspose.TeX/PngFigureRendererOptions)インスタンスを作成します。ここでは、出力画像解像度を指定します。

次に、前文を指定します。ラテックスフィギュアレンダリングにはデフォルトのプリアンブルはありません。たとえば、 `pict2e`ラテックスパッケージを使用してプロットされたグラフィックをレンダリングする必要がある場合は、preambleで指定する必要があります。

```tex
\usepackage{pict2e}
```

次に、レンダラーに出力を300％スケーリングするよう指示します。

次のオプションは、背景色を定義します。数学の式レンダリングとは異なり、色は完全にラテックスコードの制御下にあると仮定するため、前景の色を指定しません。実際、背景色もそうですので、これは単なる便利なオプションです。

例の次の行はあまり意味がありません。ログ出力をストリームに向けることができることを示しています。

また、最後のオプション「showterminal」を使用すると、ターミナル出力の書き込みをコンソールに切り替えることができます。

実際にレンダリングを実行する方法は[figurerenderer.render()](https://reference.aspose.com/tex/java/com.Aspose.TeX/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.Aspose.TeX.FigureRendererOptions-)です。フィギュアのサイズをポイントで返します。

画像が記述されるストリームは、2番目の引数としてメソッドによって受け入れられます。次にストリームを作成します。

そして最後に、 `figurerenderer.render()`メソッド自体を3番目の引数として渡すオプションを呼び出します。図のラテックスコードは、最初の引数として渡されます。

この例の最後の行には、図のレンダリングの2つのアーティファクトが印刷されています。図のサイズと簡単なエラーレポート(エラーがある場合)。

レンダリングの結果です。

![ラテックスフィギュアはPNGにレンダリングします](/tex/images/java/text-and-formula.png)

これは、**LaTexフィギュアレンダリング**機能の最も一般的なユースケースです。

## ラテックスフィギュアをSVGにレンダリングする方法

ほぼ同じように、ラテックスフィギュアをSVG形式にレンダリングできます。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

違いは次のとおりです。

 * [pngfigurerenderereroptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/PngFigureRendererOptions)の代わりに[svgfigurerenderereroptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/SvgFigureRendererOptions)クラスを使用します。
 * 解決策は指定しません。
 * [pngfigurerenderer](https://reference.aspose.com/tex/java/com.Aspose.TeX/PngFigureRenderer)の代わりに[svgfigurerenderer](https://reference.aspose.com/tex/java/com.Aspose.TeX/SvgFigureRenderer)クラスを使用します。
 
これが結果です：

<a href="/tex/images/java/text-and-formula.svg">![ラテックスフィギュアはSVGにレンダリングします](/tex/images/java/text-and-formula.svg)</a>
