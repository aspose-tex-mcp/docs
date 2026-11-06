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

`ASPOSE_TEX_OUTPUT_DIR` に出力ディレクトリを指定するか、既定の `output` フォルダーを使用してください。LaTeX コードはすべて例に含まれているため、外部入力ファイルは不要です。事前にライセンスを適用してください。 [ライセンス](/tex/ja/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

最初に、[LaTeX 図レンダラーオプション](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/) クラスのインスタンスを作成し、同時に出力画像の解像度を指定します。

次に、プリアンブルを指定する必要があります。LaTeX 数式レンダリングとは異なり、LaTeX 図のレンダリングにはデフォルトのプリアンブルがありません。そのため、たとえば `pict2e` パッケージで作成されたグラフィックをレンダリングする場合は、プリアンブルにそれを指定する必要があります:

```tex
\usepackage{pict2e}
```

`scale = 3000` で 300% に拡大し、`margin = 5` でフラグメントの周囲に余白を設けます。PNG の例では `resolution = 150` DPI を使用します。

次のオプションは背景色を決定します。数式レンダリングとは異なり、前景色を指定する必要はありません。色はすべて LaTeX コードで制御されていると想定しています。同様に背景色も LaTeX コードで制御されるため、このオプションは利便性のために用意されています。

この例ではバイナリファイルストリームを `log_stream` に設定し、`text-and-formula.png` と同じ場所に `text-and-formula.png.log` を保存します。`with` 文が両方のストリームを自動的に閉じます。

`show_terminal` はコンソールへの端末出力を制御します。例では `False` に設定していますが、ログはファイルに書き込まれます。

図のレンダリングを担当するメソッドは [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions)  です。ポイント単位で図のサイズを返します。

第2引数は画像用に開いたバイナリ出力ストリームです。第3引数はレンダリングオプションです。

最後に、`FigureRenderer.render()` メソッド自体を呼び出し、オプションを第3引数として渡します。図の LaTeX コードは第1引数として提供されます。

最後の行ではエラーレポート、またはレポートが空なら `No rendering errors.` を表示し、その後に幅と高さをポイント単位で表示します。

以下はレンダリング結果です。

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![LaTeX Figure rendering to PNG](/tex/images/python-net/text-and-formula.png)</a>

これは **LaTeX 図のレンダリング** 機能の最も一般的な使用例を表しています。

## LaTeX 図を SVG にレンダリングする

同様に、LaTeX 図を SVG 形式でもレンダリングできます。

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

この例では同じ出力ディレクトリに `text-and-formula.svg` とログ `text-and-formula.svg.log` を作成します。

違いは次のとおりです：

* [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/) クラスの代わりに、[SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/) クラスを使用します。
* 解像度を指定する必要はありません。
* [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/) クラスの代わりに、[SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/) クラスを使用します。

結果は以下です：

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/images/python-net/text-and-formula.svg)</a>
