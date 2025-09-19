---
translation: true
template: /templates/_template-net.md
title: イメージへのラテックス| .NET
linktitle: 画像からラテックス
weight: 10
url: /net/latex-to-image/
keywords: ラテックスからPNG、ラテックスPNG、ラテックスから画像、ラテックス画像、ラテックス、JPG、ラテックスJPG、ラテックス、JPEG、ラテックスJPEG、ラテックスからTIFF、ラテックスティフ、ラテックスからBMP、ラテックスBMP
description: Aspose.TeX APIソリューションを使用してTexを画像形式に変換するには、この記事を学び、これを行う方法とコードの例を説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

**.NETのasops.tex**を使用すると、ラテックスファイルを多数のラスター画像形式に変換できます。

## ラテックスをPNGに変換する方法

C＃のコードを詳細に見てみましょう。ラテックスをPNG形式に変換する最も簡単な方法を提供します。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.cs" >}}

したがって、私たちが最初に行う必要があること(まあ、時には最初のものではないこともあります)は、[テキサプティオン](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/)クラスのインスタンスを作成することです。これを行う唯一の静的方法は[consoleappoptions()](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/consoleappoptions/)です。したがって、その名前の意味に困惑しないようにしましょう。このメソッドは、[TexConfig](https://reference.aspose.com/tex/net/Aspose.TeX/texconfig/)クラスの[ObjectLatexインスタンス](https://reference.aspose.com/tex/net/Aspose.TeX/texconfig/objectlatex/)を取ります。これは[LaTexファイル](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)の変換に正確に適しています。この構成は、Object Tex EngineにObject Latex形式をロードし、LaTexファイルを受け入れる準備ができているように指示します。オブジェクトラテックス形式は、実際には[latex](/tex/{{lang.url-fragment}}net/what-is-latex/)形式にすぎませんが、[オブジェクトTex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定のプリミティブを使用してページメトリックをセットアップすることを除きます。

必要なオプションの最初は[outputworkingdirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/outputworkingdirectory/)で、TEX出力が記述されるスペースまたはエリアを定義します。 [ここ](/tex/{{lang.url-fragment}}net/aspose-tex-output/)は、.net **for .net** for ** Aspose.TeXの出力ディレクトリの概念の詳細です。この例では、[outputfilesystemdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)クラスを使用して、指定されたディレクトリまたはフォルダーに出力を書き込むことができます。

2番目のオプションは、[オブジェクトモデル](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)のターゲット形式への変換を制御する[SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/)クラスインスタンスです。ラテックスをPNGに変換しているため、[pngsaveoptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/)クラスインスタンスであり、出力画像の解像度を指定できます。

次に、[texjob](https://reference.aspose.com/tex/net/Aspose.TeX/texjob/)クラスのインスタンスを作成する必要があります。ファイルシステムに保存されているラテックスファイルを変換したいので、[This](https://reference.aspose.com/tex/net/Aspose.TeX/texjob/texjob/)バージョンのコンストラクターを使用します。ファイルへのフルパスを指定する必要があります。それ以外の場合、エンジンは現在のディレクトリ([currentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory))でそれを探しますが、おそらく見つけられないでしょう。それにもかかわらず、 *.tex*拡張機能は省略できます。エンジンは自動的に追加されます。コンストラクターの2番目の引数は、[デバイス](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/)クラスインスタンスです。ラテックスをPNGに変換しているため、[Imagedevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/)クラスインスタンスであり、これはすべてのサポートされている画像形式に共通しています。最後の議論として、最近準備された変換オプションに合格します。

今やるべきことは、仕事を[走る](https://reference.aspose.com/tex/net/Aspose.TeX/texjob/run/)だけです。

実行が成功したかどうかに関係なく、私たちが見る最初の結果は端子出力になります。実行が成功した場合、それは次のようになります：


```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

出力ディレクトリとして指定したフォルダーに、エンジンの労働力の他の「果物」があります。これらはトランスクリプトファイルであり、**ここにあります！**、メインの出力PNG画像ファイルです。

## メイン出力PNGファイルを書き込む代替方法

画像データをバイト配列の配列として取得する別の方法があり、2番目のディメンションの各配列は別のページの画像データを表します。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.cs" >}}

* "page-n.png" *ファイルは、指定する任意のパスに書き込まれます。 [PDF出力](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)とは異なり、それらは出力ディレクトリに書き込まれた出力PNGファイルを複製します。

## 入力オプションについて
メイン入力ファイルに、基本的なラテックスシステムに含まれておらず、サポートされているパッケージに含まれていないパッケージなどの依存関係が必要な場合は、[RequiredInputDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/requiredinputdirectory/)オプションを設定する必要があります。依存関係は、サブディレクトリで任意に組織される場合があります。タイプセットプロセス、たとえば外部グラフィックファイルに沿って含める独自のファイルがある場合は、それらのファイルが収集される場所へのパスを使用して[inputWorkingDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/inputworkingdirectory/)を設定する必要があります。また、メイン入力ファイルを入力ディレクトリ内のどこかに配置し、 `run()`メソッドの相対パスを指定することもできます(または、メイン入力ファイルがルートにある場合はパスをまったく指定しません)。 [ここ](/tex/{{lang.url-fragment}}net/aspose-tex-input/)は、.net **の** Aspose.TeXの入力ディレクトリの概念の詳細であり、実装が提供されています。

他のTEXジョブオプションについて説明します[ここ](/tex/{{lang.url-fragment}}net/other-options/)。

**[.NET APIのAsops.Tex](https://products.aspose.com/tex/net/)に基づいて構築された無料のLaTex-to-PNG変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-png)をチェックアウトすることもできます。**

以下では、実際には詳細がないため、詳細に深く沈むことなく、他のサポートされているラスター画像形式へのラテックス変換について説明します。唯一の違いは、変換オプションの[SaveOptions](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/saveoptions/)プロパティのタイプです。

## ラテックスをJPGに変換する方法

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.cs" >}}


**[.NET APIのasophes.tex](https://products.aspose.com/tex/net/)に基づいて構築された無料のLaTex-to-JPG変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-jpg)をチェックアウトすることもできます。**

## ラテックスをTIFFに変換する方法

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.cs" >}}

**[.NET APIのasops.tex](https://products.aspose.com/tex/net/)に基づいて構築された無料のラテックスからティフへの変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-tiff)をチェックアウトすることもできます。**

## ラテックスをBMPに変換する方法

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.cs" >}}

**[.NET APIのasops.tex](https://products.aspose.com/tex/net/)に基づいて構築された無料のラテックスからBMPへの変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-bmp)をチェックアウトすることもできます。**

## ラテックスをSVGに変換する方法

さらにサポートされているターゲット形式は[**svg**](https://en.wikipedia.org/wiki/SVG)です。 **Scalable Vector Graphics(SVG)**は、対話性とアニメーションをサポートする2次元グラフィックを定義するためのXMLベースのベクトル画像形式です。

**SVG**画像はベクトルグラフィック形式で定義され、XMLテキストファイルに保存されます。 **SVG**画像は品質を失うことなくサイズをスケーリングでき、**SVG**ファイルは検索、インデックス作成、スクリプト化、および圧縮できます。 XMLテキストファイルは、テキストエディターまたはベクトルグラフィックスエディターで作成および編集でき、最も使用されているWebブラウザーによってレンダリングされます。

**svg**に関連するさまざまな機能を提供する[**aspose.svg**](https://products.aspose.com/svg/)ライブラリがあります。これらには、**svg**ドキュメントの作成、読み込み、編集、変換が含まれます。

ラテックスからSVGへの変換は、[saveoptions](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/saveoptions/)を[svgsaveoptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/)クラスインスタンスに設定する必要があり、デバイスを[svgdevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/)クラスのインスタンスに変更する必要があることを除いて、[ラスター画像形式への変換](/tex/{{lang.url-fragment}}net/latex-to-image/)と同じくらい簡単です。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.cs" >}}

**[.NET APIのAspose.TeX](https://products.aspose.com/tex/net/)に基づいて構築された無料のLaTex-to-SVG変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-svg)をチェックアウトすることもできます。**