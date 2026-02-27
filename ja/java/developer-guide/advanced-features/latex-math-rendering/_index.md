---
translation: true
template: /templates/_template-java.md
title: LaTeX 数式レンダリング | Aspose.TeX for Java
linktitle: LaTeX 数式レンダリング
weight: 10
url: /java/latex-math-formula-rendering/
description: Aspose.TeX API for Java における LaTeX 数式レンダリングについて説明します。機能の使用方法のコード例をご覧ください。
lastmod: "2026-02-27"
---

{{<section overview>}}

## LaTeX 数式を PNG にレンダリングする方法

実際、**LaTeX 数式** レンダリング機能を示す最も簡単な方法はサンプルから始めることです。こちらがその例です:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

詳細に入ります。まず、TeX/LaTeX の組版と同様に [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions) インスタンスを作成します。ここでは同時に出力画像の解像度も指定しています。

次に、プリアンブルを指定します。デフォルトのプリアンブルは次のとおりです:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

これは基本的な LaTeX より多少高度な数式サポートを提供します。例えば、独自のハイライトを数式内で使用したい場合は `color` パッケージを追加できます（コード例に示しています）。

続いて、レンダラに出力を 300% に拡大するよう指示します。

次の 2 つのオプションは前景色と背景色を定義します。カスタムハイライトで「色付け」されていない数式の部分は `TextColor` の色で表示されます。

例の次の行はあまり意味がありませんが、ログ出力を任意のストリームにリダイレクトできることを示しています。

最後のオプション `ShowTerminal` はターミナル出力をコンソールに書き込むかどうかを切り替えます。

実際にレンダリングを行うメソッドは [MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) です。式のサイズ（ポイント単位）を返します。

画像を書き込むストリームはメソッドの第 2 引数として受け取ります。次にストリームを作成します。

そして最後に、`MathRenderer.render()` メソッド自体を呼び出し、オプションを第 3 引数として渡します。式の LaTeX コードは第 1 引数として渡されます。

例の最後の行は、数式レンダリングの成果物である式のサイズと簡易エラーレポート（エラーがあった場合）を出力します。

以下がレンダリング結果です。

<a href="/tex/images/java/math-formula.png">![LaTeX Figure rendering to PNG](/tex/images/java/math-formula.png)</a>

これは **LaTeX 数式** レンダリングの最も一般的な使用例です。

**無料の [web app](https://products.aspose.app/tex/equation-editor/png) もご確認ください。この機能は [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API で実装されています。Java バージョンのページは [こちら](https://products.aspose.com/tex/java/)。**

## LaTeX 数式を SVG にレンダリングする方法

ほぼ同様の手順で、LaTeX 数式を SVG 形式でレンダリングできます。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

主な違いは以下の通りです:

* [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) クラスを使用し、[PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions) の代わりに使用します。
* 解像度を指定しません。
* [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) クラスを使用し、[PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer) の代わりに使用します。

以下が結果です:

<a href="/tex/images/java/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/images/java/math-formula.svg)</a>

**無料の [web app](https://products.aspose.app/tex/equation-editor/svg) もご確認ください。この機能は [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) で実装されています。**
