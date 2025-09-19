---
translation: true
template: /templates/_template-java.md
title: ラテックス数学式レンダリング| Java用のAspose.TeX
linktitle: ラテックス数学式レンダリング
weight: 10
url: /java/latex-math-formula-rendering/
description: JavaのAspose.TeX API内でレンダリングするLaTex MATH式レンダリングについては、この記事で説明します。機能の使用方法のコード例を学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}

## ラテックス数学をPNGにレンダリングする方法

実際、**ラテックス数学式**レンダリング機能を実証する最も簡単な方法は、例から始めることです。ここにあります：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

詳細について説明しましょう。まず、TEX/LaTexタイプセットと同様に、[レンダリングオプション](https://reference.aspose.com/tex/java/com.Aspose.TeX/PngMathRendererOptions)インスタンスを作成します。ここでは、出力画像解像度を同時に指定します。

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

実際にレンダリングを実行する方法は[MathRenderer.Render()](https://reference.aspose.com/tex/java/com.Aspose.TeX/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.Aspose.TeX.MathRendererOptions-)です。式のサイズをポイントで返します。

画像が記述されるストリームは、2番目の引数としてメソッドによって受け入れられます。次にストリームを作成します。

そして最後に、 `mathrenderer.render()`メソッド自体を3番目の引数として渡します。式のラテックスコードは、最初の引数として渡されます。

この例の最後の行には、数学式の2つのアーティファクトが印刷されています。式のサイズと簡単なエラーレポート(エラーがあった場合)。

レンダリングの結果です。

<a href="/tex/images/java/math-formula.png">![ラテックスフィギュアはPNGにレンダリングします](/tex/images/java/math-formula.png)</a>

これは、**ラテックス数学式**レンダリングの最も一般的なユースケースです。

**[Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API に実装された機能をベースに構築された無料の [Web アプリ](https://products.aspose.app/tex/equation-editor/png) もぜひお試しください。Java 版のページは [こちら](https://products.aspose.com/tex/java/) です。**

## ラテックス数学をSVGにレンダリングする方法

ほぼ同じように、LaTex MathフォーミュラをSVG形式にレンダリングできます。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

違いは次のとおりです。

 * [pngmathrendereroptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/PngMathRendererOptions)の代わりに[svgmathrendereroptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/SvgMathRendererOptions)クラスを使用します。
 * 解像度を指定しません。
 * [pngmathrenderer](https://reference.aspose.com/tex/java/com.Aspose.TeX/PngMathRenderer)の代わりに[svgmathrenderer](https://reference.aspose.com/tex/java/com.Aspose.TeX/SvgMathRenderer)クラスを使用します。

これが結果です：

<a href="/tex/images/java/math-formula.svg">![ラテックス数学式はSVGにレンダリングします](/tex/images/java/math-formula.svg)</a>

**[.NET APIのAspose.TeX](https://products.aspose.com/tex/net/)内に実装されている機能に基づいて構築された無料の[Webアプリ](https://products.aspose.app/tex/equation-editor/svg)をチェックアウトすることもできます。**