---
translation: true
template: /templates/_template-python-net.md
title: イメージへのラテックス| .NET経由でPython用のAspose.TeX
linktitle: 画像からラテックス
weight: 10
url: /python-net/latex-to-image/
keywords: ラテックスからPNG、ラテックスPNG、ラテックスから画像、ラテックス画像、ラテックス、JPG、ラテックスJPG、ラテックス、JPEG、ラテックスJPEG、ラテックスからTIFF、ラテックスティフ、ラテックスからBMP、ラテックスBMP
description: Aspose.TeX APIソリューションを使用してTexを画像形式に変換するには、この記事を学び、これを行う方法とコードの例を説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

**PythonのAsops.tex**は、LaTexファイルをさまざまなラスター画像形式に変換する機能を提供します。

## ラテックスをPNGに変換します

次に、ラテックスをPNG形式に深く変換するための最も簡単なアプローチを提供するPythonコードを調べましょう。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

まず、[console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)  メソッドを使用して[texoptions](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/)クラスのインスタンスを作成する必要があります。名前を心配しないでください。インスタンスを作成するのは静的な方法だけです。この方法では、[texconfig](https://reference.aspose.com/tex/python-net/Aspose.TeX/texconfig/)クラスの[object_latex](https://reference.aspose.com/tex/python-net/Aspose.TeX/texconfig/object_latex/)インスタンスを取ります。これは、[latexファイル](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)を変換するのに最適です。この構成により、オブジェクトTexエンジンを設定して、オブジェクトラテックス形式をロードし、ラテックスファイルを処理する準備ができています。オブジェクトラテックス形式は基本的に[ラテックス形式](/tex/{{lang.url-fragment}}net/what-is-latex/)と同じですが、[Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定のプリミティブを使用してページメトリックを定義します。

必須オプションの1つ目は[output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/)で、TeX出力の保存場所を指定します。ご興味があれば、[**Aspose.TeX for Python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/)における[output directory](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/)出力ディレクトリの概念について詳細をご確認ください。この例では、[OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/)クラスを使用して、出力を特定のディレクトリまたはフォルダーに書き込みます。

2番目のオプションは、[オブジェクトモデル](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)から目的の形式への変換の管理を担当する[SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/)クラスのインスタンスです。この場合、ラテックスをPNGに変換するため、[pngsaveoptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/)クラスインスタンスを使用して、出力画像の解像度を指定できます。

次に、[texjob](https://reference.aspose.com/tex/python-net/Aspose.TeX/texjob/)クラスのインスタンスを作成します。この場合、ファイルシステムに保存されているラテックスファイルを変換するため、[コンストラクターのこのバージョン](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)  を使用します。ファイルへのフルパスを提供する必要があります。そうしないと、エンジンは現在のディレクトリ(スクリプトのワーキングディレクトリ)でそれを探し、それを見つけられない場合があります。ただし、エンジンが自動的に追加されるため、 `.tex`拡張子を省略できます。コンストラクターの2番目の引数は、[デバイス](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/)クラスのインスタンスです。ラテックスをPNGに変換しているため、サポートされているすべての画像形式に共通する[Imagedevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/)クラスインスタンスです。最後に、準備した変換オプションを最後の引数として渡します。

さて、残っているのは、仕事を[実行](https://reference.aspose.com/tex/python-net/Aspose.TeX/texjob/run/#)することです。

ジョブが実行された後、その成功や失敗に関係なく、最初に遭遇する出力は端末出力です。実行が成功した場合、出力は次のものに似ています。


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

エンジンの作業の結果は、指定した出力ディレクトリにあります。これには、トランスクリプトファイルと、最も重要なことに、メインの出力PNGイメージファイルが含まれます。

## メイン出力PNGファイルを書き込む代替方法

2番目のディメンションの各配列が個別のページの画像データを表すバイト配列の配列として画像データを取得する代替方法があります。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

「page-n.png」ファイルは、指定されたパスに書き込むことができます。 [PDF出力](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file)とは異なり、これらのPNGファイルは、出力ディレクトリに書き込まれる出力PNGファイルを複製します。

## 入力オプションについて

メインの入力ファイルに、基本的なラテックスシステムやサポートされているパッケージに含まれていないパッケージなどの依存関係が必要な場合、[rebuse_input_directory](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/required_input_directory/)オプションを * output_working_directory *オプションの設定方法と同様の方法で設定し、そのディレクトリに依存関係を配置する必要があります。依存関係は、必要に応じてサブディレクトリで編成できます。外部グラフィックファイルなどの版形セットプロセスに含めるファイルがある場合は、[input_working_directory](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/input_working_directory/)をそれらのファイルが保存されている場所に設定する必要があります。また、入力ディレクトリ内にメイン入力ファイルを配置し、 `run()`メソッドの相対パスを指定したり、メイン入力ファイルがルートディレクトリにある場合はパスをまったく指定したりすることもできます。また、[入力ディレクトリの概念](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/)の詳細については、**Aspose.TeX**と説明されている実装が記載されています。

また、[他のTEXジョブオプションはこちら](/tex/{{lang.url-fragment}}python-net/other-options/)を学びます。

** LaTex-to-PNG変換用の無料[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-png)を探索することもできます。

以下に、有意な違いがないため、あまり詳細に飛び込むことなく、ラテックスの他のサポートされているラスター画像形式への変換を簡単に説明します。唯一のバリエーションは、変換オプションの[save_options](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/save_options/)プロパティのタイプにあります。

## ラテックスをJPGに変換します

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

** [LaTex-to-JPG変換用のWebアプリ](https://products.aspose.app/tex/conversion/latex-to-jpg)を探索することもできます。

## ラテックスをTIFFに変換します

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) を使用して開発された無料の [LaTeX から TIFF への変換用 Web アプリ](https://products.aspose.app/tex/conversion/latex-to-tiff) を調べることもできます。**

## ラテックスをBMPに変換します

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

** [LaTex-to-BMP変換用のWebアプリ](https://products.aspose.app/tex/conversion/latex-to-bmp)を探索することもできます。


## ラテックスをSVGに変換します

別のサポートされているターゲット形式は[**svg**](https://en.wikipedia.org/wiki/SVG)です。 **Scalable Vector Graphics(SVG)**は、2次元グラフィックを定義するために使用されるXMLベースのベクトル画像形式です。対話性とアニメーションをサポートします。

**SVG**画像はXMLテキストファイルに保存され、ベクトルグラフィック形式で定義されています。これは、**svg**画像を品質を失うことなくサイズでスケーリングできることを意味し、**svg**ファイル自体を検索、インデックス作成、スクリプト化、および圧縮できます。 XMLテキストファイルは、テキストエディターまたはベクトルグラフィックスエディターを使用して作成および編集でき、最も一般的に使用されるWebブラウザーによってレンダリングできます。

[**Aspose.svg**](https://products.aspose.com/svg/)APIは、**svg**の作成、読み込み、編集、変換など、**svg**を操作するためのさまざまな機能を提供します。

ラテックスをSVGに変換することは[ラスター画像形式に変換](/tex/{{lang.url-fragment}}python-net/latex-to-image/)と同じくらい簡単です。唯一の違いは、[save_options](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/save_options/)を[svgsaveoptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/)クラスのインスタンスに設定する必要があることです。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

** [LaTex-to-SVG変換用のWebアプリ](https://products.aspose.app/tex/conversion/latex-to-svg)を探索することもできます。