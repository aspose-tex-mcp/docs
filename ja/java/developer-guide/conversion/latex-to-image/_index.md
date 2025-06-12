---
translation: true
template: /templates/_template-java.md
title: イメージへのラテックス| Java用のAspose.TeX
linktitle: 画像からラテックス
weight: 10
url: /java/latex-to-image/
keywords: ラテックスからPNG、ラテックスPNG、ラテックスから画像、ラテックス画像、ラテックス、JPG、ラテックスJPG、ラテックス、JPEG、ラテックスJPEG、ラテックスからTIFF、ラテックスティフ、ラテックスからBMP、ラテックスBMP
description: Aspose.TeX APIソリューションを使用してTexを画像形式に変換するには、これを行う方法とコードの例を説明するこの記事を学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}
**Java 用の Aspose.TeX** provides features for converting LaTeX files to a number of raster image formats.

## ラテックスをPNGに変換する方法

LaTexをPNG形式に変換する最も簡単な方法を提供するJavaコードを詳しく見てみましょう。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.java" >}}

したがって、最初に行う必要があることは(後でわかったように、最初にそうではない場合があります)、[Texoptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions)クラスのインスタンスを作成することです。これを行う唯一の静的方法は[consoleappoptions()](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#consoleAppOptions-com.Aspose.TeX.TeXConfig-)です。そのため、その名前の意味を悩ませないでください。このメソッドは、[TexConfig](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXConfig)クラスの[ObjectLatex()インスタンス](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXConfig#objectLaTeX--)を取得します。この構成は、オブジェクトTex Engineにオブジェクトラテックス形式をロードし、LaTexファイルを受け入れる準備ができるように指示します。オブジェクトラテックス形式は、実際には[latex](/tex/{{lang.url-fragment}}net/what-is-latex/)形式にすぎませんが、[オブジェクトTex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定のプリミティブを使用してページメトリックをセットアップすることを除きます。

必要なオプションの最初は[outputworkingdirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getOutputWorkingDirectory--)で、TEX出力が記述されるスペースまたはエリアを定義します。 [ここ](/tex/{{lang.url-fragment}}java/aspose-tex-output/)は、java **for** Aspose.TeXの出力ディレクトリの概念の詳細です。この例では、[outputfilesystemdirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/OutputFileSystemDirectory)クラスを使用して、指定されたディレクトリまたはフォルダーに出力を書き込むことができます。

2番目のオプションは、[オブジェクトモデル](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)のターゲット形式への変換を制御する[SaveOptions](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/SaveOptions)クラスインスタンスです。ラテックスをPNGに変換しているため、[pngsaveoptions](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/PngSaveOptions)クラスインスタンスであり、出力画像の解像度を指定できます。

次に、[texjob](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXJob)クラスのインスタンスを作成する必要があります。ファイルシステムに保存されているラテックスファイルを変換したいので、[This](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXJob#TeXJob-java.lang.String-com.Aspose.TeX.rendering.Device-com.Aspose.TeX.TeXOptions-)バージョンのコンストラクターを使用します。ファイルへのフルパスを指定する必要があります。それ以外の場合、エンジンは現在のディレクトリ([here](https://docs.oracle.com/javase/7/docs/api/java/io/File.html))で定義されており、おそらく見つけられない可能性があります。それにもかかわらず、ファイルに *.tex* 1がある場合、拡張子を省略する場合があります。エンジンは自動的に追加されます。コンストラクターの2番目の引数は、[デバイス](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/Device)クラスインスタンスです。ラテックスをPNGに変換しているため、[Imagedevice](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/ImageDevice)クラス(サポートされているすべての画像形式に共通)インスタンスです。最後の議論として、最近準備された変換オプションに合格します。

私たちが今しなければならないことは、仕事を(19)走ることだけです。

実行が成功したかどうかに関係なく、私たちが見る最初の結果は端子出力になります。成功した場合、それは次のように見えます：


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

出力ディレクトリとして指定したフォルダーにエンジンの実行の他の製品があります。これらは、トランスクリプト(.log)ファイルと**voila！**、メインの出力PNG画像ファイルになります。

## メイン出力PNGファイルを書き込む代替方法

画像データをバイト配列の配列として取得する別の方法があり、2番目のディメンションの各配列は別のページの画像データを表します。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.java" >}}

* "page-n.png" *ファイルは、指定する任意のパスに書き込まれます。 [PDF出力](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)とは異なり、それらは出力ディレクトリに書き込まれた出力PNGファイルを複製します。

## 入力オプションについて

メイン入力ファイルに、基本的なラテックスシステムに含まれておらず、サポートされているパッケージに含まれていないパッケージなどの依存関係が必要な場合は、[RequiredInputDirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getRequiredInputDirectory--)オプションを設定する必要があります。依存関係は、サブディレクトリで任意に組織される場合があります。タイプセットプロセス、たとえば外部グラフィックファイルに沿って含める独自のファイルがある場合は、それらのファイルが収集される場所へのパスを使用して[inputWorkingDirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getInputWorkingDirectory--)を設定する必要があります。また、入力ディレクトリ内のどこかにメイン入力ファイルを配置し、 `run()`メソッドの相対パスを指定することもできます(または、メイン入力ファイルがルートにある場合はパスをまったく指定しません)。 [ここ](/tex/{{lang.url-fragment}}java/aspose-tex-input/)は、Java **の** Aspose.TeXの入力ディレクトリの概念の詳細であり、実装を提供しています。

他のTEXジョブオプションについて説明します[ここ](/tex/{{lang.url-fragment}}java/other-options/)。

**[.NETのAsops.Tex](https://products.aspose.com/tex/net/)AP​​Iに基づいて構築された無料のLaTex-to-PNG変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-png)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/java/)はJavaバージョンページです。**

以下では、他のサポートされているラスター画像形式へのラテックス変換について説明します。実際には詳細がないからといって、詳細には触れません。唯一の違いは、変換オプションの[SaveOptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getSaveOptions--)プロパティのタイプです。

## ラテックスをJPGに変換する方法

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.cs" >}}

**[.NETのAspose.TeX](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のLaTex-to-JPGコンバージョン[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-jpg)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/java/)はJavaバージョンページです。**

## ラテックスをTIFFに変換する方法

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.cs" >}}

**[.netのAspose.TeX](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のラテックス間変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-tiff)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/java/)はJavaバージョンページです。**

## ラテックスをBMPに変換する方法

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.cs" >}}

**[.NETのasops.tex](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のラテックスからBMPへの変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-bmp)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/java/)はJavaバージョンページです。**


## ラテックスをSVGに変換する方法

さらにサポートされているターゲット形式は[**svg**](https://en.wikipedia.org/wiki/SVG)です。 **Scalable Vector Graphics(SVG)**は、対話性とアニメーションをサポートする2次元グラフィックを定義するためのXMLベースのベクトル画像形式です。

**SVG**画像はベクトルグラフィック形式で定義され、XMLテキストファイルに保存されます。これは、**svg**画像の品質を失うことなくサイズをスケーリングできることを意味し、**svg**ファイルを検索、インデックス作成、スクリプト化、および圧縮できます。 XMLテキストファイルは、テキストエディターまたはベクトルグラフィックスエディターで作成および編集できます。 Thayは、最も使用されているWebブラウザーによってレンダリングされます。

また、**svg**形式に基づいてさまざまな機能を備えた[**aspose.svg**](https://products.aspose.com/svg/)ライブラリがあります。これらには、**svg**ドキュメントの作成、読み込み、編集、変換が含まれます。

SVGへの変換は、[saveoptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getSaveOptions--)に加えて、[SVGDevice](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/SvgDevice)クラスのインスタンスにデバイスを変更する必要があることを除いて、[ラスター画像形式への変換](/tex/{{lang.url-fragment}}java/latex-to-image/)と同じくらい簡単です。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.java" >}}

**[.NETのasops.tex](https://products.aspose.com/tex/net/)に基づいて構築された無料のラテックスからSVGへの変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-svg)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/java/)はJavaバージョンページです。**