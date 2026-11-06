---
translation: true
template: /templates/_template-python-net.md
title: LaTeX 数式のレンダリング | Python via .NET
linktitle: LaTeX 数式のレンダリング
weight: 10
url: /python-net/latex-math-formula-rendering/
description: 記事では、Python 用 Aspose.TeX API ソリューションの概要と LaTeX 数式のレンダリング機能について紹介します。コード例をご覧ください
lastmod: "2026-04-03"
---

{{<section overview>}}

## PNG に LaTeX 数式をレンダリングする

必要に応じて、[このトピックのAPIリファレンスセクション](https://reference.aspose.com/tex/python-net/aspose.tex.features/)をご覧ください。実際、**LaTeX数式**レンダリング機能を理解するには、まず例を挙げるのが最も効果的です。以下に例を示します。

`ASPOSE_TEX_OUTPUT_DIR` に出力ディレクトリを指定するか、既定の `output` フォルダーを使用してください。LaTeX コードはすべて例に含まれているため、外部入力ファイルは不要です。事前にライセンスを適用してください。 [ライセンス](/tex/ja/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

詳細を見ていきましょう。まず、TeX/LaTeXタイプッティングに似た[レンダリングオプション](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/)オブジェクトを初期化します。このオブジェクトには、必要な出力画像解像度の指定が含まれています。

次に、プリアンブルを指定します。デフォルトのプリアンブルは次のとおりです。


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

これは、標準的なLaTeXに比べて数式のサポートが強化されています。例えば、提供されているコード例に示すように、`color`パッケージをインクルードすることで、数式内のハイライト表示をカスタマイズできます。

`scale = 3000` で 300% に拡大し、`margin = 5` でフラグメントの周囲に余白を設けます。PNG の例では `resolution = 150` DPI を使用します。

次の2つのオプションは、前景色と背景色を決定します。数式の中でカスタムハイライトの影響を受けない部分は、`text_color`カラーで表示されます。

この例ではバイナリファイルストリームを `log_stream` に設定し、`math-formula.png` と同じ場所に `math-formula.png.log` を保存します。`with` 文が両方のストリームを自動的に閉じます。

`show_terminal` はコンソールへの端末出力を制御します。例では `False` に設定していますが、ログはファイルに書き込まれます。

実際のレンダリング処理は [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/) メソッドによって実行され、数式のサイズをポイント単位で返します。

第2引数は画像用に開いたバイナリ出力ストリームです。第3引数はレンダリングオプションです。

最後に、`MathRenderer.render()` メソッドが呼び出され、オプションが3番目の引数として渡されます。数式の LaTeX コードは1番目の引数として提供されます。

最後の行ではエラーレポート、またはレポートが空なら `No rendering errors.` を表示し、その後に幅と高さをポイント単位で表示します。

レンダリングの結果は次のとおりです。

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![LaTeX 数式を PNG にレンダリング](/tex/images/python-net/math-formula.png)</a>

これは、**LaTeX 数式レンダリング** 機能の最も一般的で幅広い応用例です。

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) の実装機能を活用した無料の[Webアプリ](https://products.aspose.app/tex/equation-editor/png)もお試しください。**

## SVG に LaTeX 数式をレンダリングする

同様に、同じ方法でLaTeXの数式をSVG形式に変換できます。

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

この例では同じ出力ディレクトリに `math-formula.svg` とログ `math-formula.svg.log` を作成します。

違いは以下のとおりです。

* [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) クラスの代わりに、[SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/) クラスを使用します。
* 解像度は指定しません。
* [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) クラスの代わりに、[SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/) クラスを使用します。

結果は以下のとおりです。

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![LaTeX 数式を SVG にレンダリング](/tex/images/python-net/math-formula.svg)</a>

**[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) の実装機能を活用した無料の [Web アプリ](https://products.aspose.app/tex/equation-editor/svg) もお試しください。**