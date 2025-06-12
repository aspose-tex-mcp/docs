---
translation: true
template: /templates/_template-python-net.md
title: ラテックスフィギュアレンダリング| Python用のAspose.TeX
linktitle: ラテックスには図が含まれています
weight: 20
url: /python-net/latex-figure-rendering/
description: この記事では、PythonのAsops.tex APIソリューションと、ラテックスフラグメントをレンダリングするためのその機能の概要を説明します(図)。コードの例を学びます。
keywords: ラテックスフィギュア、フィギュアサイズのラテックス、ラテックス画像、ラテックス画像、ラテックスにはフィギュア、ラテックス写真、ラテックスフィギュアオプションが含まれます
lastmod: "2025-06-09"
---

{{<section overview>}}

特定の状況では、ページレイアウトに接続せずに、一般に *フィギュア *と呼ばれるスタンドアロンレンダリングピースとして、LaTexファイルから特定のコンテンツを抽出する必要がある場合があります。これは、たとえば、オンライン公開のイラストを作成するときに役立つ可能性があります。私たちのAPIを使用すると、これを達成できます。レンダリング数値のターゲット形式は、LaTex Math式レンダリング機能と同様に、PNGとSVGです。 **ラテックスフィギュアレンダリング**は、[LaTex MATH式レンダリング](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/)と比較して、より一般的な機能であることに注意してください。

## ラテックスフィギュアをPNGにレンダリングします

必要に応じて、最初に[このトピックのAPI参照セクション](https://reference.aspose.com/tex/python-net/aspose.tex.features/)をご覧ください。フォーミュラレンダリングと同様に、例から始めます。ここにあります：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

まず、[LaTexフィギュアレンダラーオプション](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/)クラスのインスタンスを作成します。このクラスでは、出力画像解像度を同時に指定します。

次に、前文を指定する必要があります。ラテックス数学の式レンダリングとは異なり、ラテックスフィギュアレンダリングのデフォルトのプリアンブルはありません。したがって、たとえば、「PICT2E」ラテックスパッケージを使用して作成されたグラフィックをレンダリングする予定がある場合は、前文で指定する必要があります。

```tex
\usepackage{pict2e}
```

次に、レンダラーに出力を300％スケーリングするよう指示します。

次のオプションは、背景色を決定します。数学の式レンダリングとは異なり、色はラテックスコードによって完全に制御されていると仮定するため、前景の色を指定する必要はありません。同様に、背景色はラテックスコードによっても制御されるため、このオプションは便利なために単純に提供されます。

この例の次の行は、特に意味がない場合があります。ログ出力を特定のストリームに向けるオプションがあることを実証することを意図しています。

最終的なオプション「Showterminal」では、端子出力をコンソールに表示するかどうかを制御できます。

図のレンダリングを担当する方法は[figurerenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-Aspose.TeX.features.FigureRendererOptions)です。フィギュアのサイズをポイントで返します。

このメソッドは、画像が記述されるストリームである2番目の引数としてストリームを受け入れます。次の行でストリームを作成します。

最後に、 `figurerenderer.render()`メソッド自体を呼び出し、3番目の引数としてオプションを渡します。図のラテックスコードは、最初の引数として提供されます。

この例の最後の数行には、図のレンダリングに関連する2つの情報が表示されます。図のサイズと簡単なエラーレポート(エラーがある場合)です。

レンダリングの結果です。

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![ラテックスフィギュアはPNGにレンダリングします](/tex/images/python-net/text-and-formula.png)</a>

これは、**ラテックスフィギュアレンダリング**機能の最も一般的なユースケースを表します。

## ラテックスフィギュアをSVGにレンダリングします

同様に、SVG形式でラテックスフィギュアをレンダリングすることもできます。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

違いは次のとおりです。

* [pngfigurerenderereroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/)クラスを使用する代わりに、[svgfigurerenderereroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/)クラスを使用します。
* 解像度を指定する必要はありません。
* [pngfigurerenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/)クラスを使用する代わりに、[svgfigurerenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/)クラスを使用します。
 
これが結果です：

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![ラテックスフィギュアはSVGにレンダリングします](/tex/images/python-net/text-and-formula.svg)</a>