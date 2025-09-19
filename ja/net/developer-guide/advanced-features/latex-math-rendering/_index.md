---
translation: true
template: /templates/_template-net.md
title: ラテックス数学式レンダリング| .NET
linktitle: ラテックス数学式レンダリング
weight: 10
url: /net/latex-math-formula-rendering/
description: .NETラテックス数学式レンダリング用のAspose.TeX APIソリューションについては、この記事で説明します。機能の使用方法に関するコードの例を学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}


## ラテックス数学をPNGにレンダリングする方法

このトピックに関連するAPI参照セクションは[ここ](https://reference.aspose.com/tex/net/aspose.tex.features/)です。実際、**ラテックス数学の式レンダリング**機能を実証する最も簡単な方法は、例から始めることです。ここにあります：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.cs" >}}

詳細について説明しましょう。まず、Tex/LaTexタイプセットと同様に、[レンダリングオプション](https://reference.aspose.com/tex/net/aspose.tex.features/mathrendereroptions/)インスタンスを作成します。ここでは、出力画像解像度を同時に指定します。

次に、前文を指定します。デフォルトのプリアンブルは次のとおりです。


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

基本的なラテックスよりもわずかに高度な数学式サポートを提供します。たとえば、コードの例で示したように、式で独自のハイライトを使用する場合は、「Color」パッケージを追加できます。

次に、レンダラーに出力を300％スケーリングするよう指示します。

次の2つのオプションは、前景と背景の色を定義します。カスタムハイライトによって覆われていない(「色付き」)式のこれらの部分は、「TextColor」色で表示されます。

例の次の行はあまり意味がありません。ログ出力をストリームに向けることができることを示しています。

また、最後のオプション「showterminal」を使用すると、ターミナル出力の書き込みをコンソールに切り替えることができます。

実際にレンダリングを実行する方法は[MathRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/mathrenderer/render/)です。式のサイズをポイントで返します。

画像が記述されるストリームは、2番目の引数としてメソッドによって受け入れられます。次にストリームを作成します。

そして最後に、 `mathrenderer.render()`メソッド自体を3番目の引数として渡します。式のラテックスコードは、最初の引数として渡されます。

この例の最後の行には、数学式の2つのアーティファクトが印刷されています - 式のサイズと簡単なエラーレポート(エラーがある場合)。

レンダリングの結果です。

<a href="/tex/net/latex-math-formula-rendering/math-formula.png">![ラテックス数学式はPNGにレンダリングします](/tex/images/net/math-formula.png)</a>

これは、**LaTex MATH式レンダリング**機能の最も一般的なユースケースです。

**[.NET APIのAspose.TeX](https://products.aspose.com/tex/net/)内に実装されている機能に基づいて構築された無料の[Webアプリ](https://products.aspose.app/tex/equation-editor/png)をチェックアウトすることもできます。**

## ラテックス数学をSVGにレンダリングする方法

ほぼ同じように、LaTex MathフォーミュラをSVG形式にレンダリングできます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.cs" >}}

違いは次のとおりです。

* [pngmathrendereroptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrendereroptions/)の代わりに[svgmathrendereroptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrendereroptions/)クラスを使用します。
* 解像度を指定しません。
* [pngmathrenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrenderer/)の代わりに[svgmathrenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrenderer/)クラスを使用します。
 
これが結果です：

<a href="/tex/net/latex-math-formula-rendering/math-formula.svg">![LaTeX 数式の SVG レンダリング](/tex/images/net/math-formula.svg)</a>

**[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) に実装された機能に基づいて構築された無料の [Web アプリ](https://products.aspose.app/tex/equation-editor/svg) もぜひご確認ください。**