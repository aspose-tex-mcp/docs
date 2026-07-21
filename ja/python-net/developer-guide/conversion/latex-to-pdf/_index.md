---
translation: true
template: /templates/_template-python-net.md
title: ラテックスからPDF | .NET経由でPython用のAspose.TeX
linktitle: ラテックスからPDF
weight: 11
url: /python-net/latex-to-pdf/
keywords: ラテックスからPDF、ラテックスPDF、ラテックスをPDFに変換します
description: この記事を使用して、Python用のAsops.tex APIソリューションを使用してTexをPDFに変換する方法を学びます。これは、詳細な説明とコードの例を提供します。
lastmod: "2025-06-09"
---

{{<section overview>}}

## ラテックスをPDFに変換します

次に、ラテックスをPDF形式に深く変換するための最も簡単なアプローチを提供するPythonコードを調べてみましょう。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

まず、[Texoptions](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/)クラスのインスタンスを作成する必要があります。 [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)  メソッドはこれを達成する唯一の静的メソッドです。そのため、その名前を心配しないでください。この方法では、[texconfig](https://reference.aspose.com/tex/python-net/Aspose.TeX/texconfig/)クラスの[object_latex](https://reference.aspose.com/tex/python-net/Aspose.TeX/texconfig/object_latex/)インスタンスを使用します。これは、[latexファイル](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)を変換するのに最適です。この構成は、オブジェクトTex Engineにオブジェクトラテックス形式をロードし、ラテックスファイルを処理するように指示します。オブジェクトラテックス形式は、[LaTex](/tex/{{lang.url-fragment}}net/what-is-latex/)形式と本質的に同じですが、[Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)固有のプリミティブを使用してページメトリックを定義します。

指定する必要がある最初のオプションは[output_working_directory](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/output_working_directory/)です。これは、TEX出力が保存される場所を決定します。必要に応じて、[**Aspose.TeX**の出力ディレクトリの概念](/tex/{{lang.url-fragment}}net/aspose-tex-output/)の詳細情報を見つけることができます。この特定のケースでは、[outputFilesSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/)クラスを使用して、出力を指定されたディレクトリまたはフォルダーに書き込むことができます。

2番目のオプションには、[saveoptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/)クラスのインスタンスが必要であり、[オブジェクトモデル](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)が目的の形式に変換される方法を決定します。私たちの場合、ラテックスをPDFに変換しているため、[pdfsaveoptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/)クラスのインスタンスを指します。

ファイルシステムに保存されているラテックスファイルを変換するには、ファイルのフルパスをパラメーターとして使用する[コンストラクター](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)  を使用して[Texjob](https://reference.aspose.com/tex/python-net/Aspose.TeX/texjob/)クラスのインスタンスを作成する必要があります。フルパスを指定しない場合、エンジンは現在のディレクトリ内のファイル(スクリプトのワーキングディレクトリ)を探し、それを見つけられない場合があります。ただし、エンジンが自動的に追加されるため、ファイルに`.tex`拡張機能がある場合、拡張機能を省略できます。コンストラクターの2番目の引数は、[デバイス](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/)クラスのインスタンスです。私たちの場合、ラテックスをPDFに変換しているため、[PDFDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/)クラスのインスタンスです。最後に、最近準備された変換オプションを最後の引数として渡します。

さて、残っているのは、仕事を[実行](https://reference.aspose.com/tex/python-net/Aspose.TeX/texjob/run/#)することです。

実行後、成功したかどうかに関係なく、最初に表示されるのは端子出力です。実行が成功した場合、出力はこれに似ています。

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

出力ディレクトリとして指定したフォルダーには、トランスクリプトファイルがあります。

## メイン出力PDFファイルを書き込む代替方法

* pdfdevice *クラスには、結果のpdfファイルを異なる方法で取得できる別の[コンストラクター](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase)があります。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

メインの出力PDFファイルは「any-name.pdf」という名前で、指定されたディレクトリに配置されます。ただし、[画像出力](/tex/{{lang.url-fragment}}python-net/latex-to-image/#an-alternative-way-to-write-the-main-output-png-files)とは異なり、変換オプションで指定された出力ディレクトリに他のPDFファイルはありません。例外は、「any-name.pdf」が *output_working_directory *オプションに割り当てられた同じファイルシステムディレクトリにある場合、 *outputFilesSystemDirectory *を使用している場合です。

## 入力オプションについて

メインの入力ファイルに、基本的なラテックスシステムに含まれていないパッケージやサポートされているパッケージなどの依存関係が必要な場合、[reburce_input_directory](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/required_input_directory/)オプションを * output_working_directory *オプションを設定し、そのディレクトリに依存関係を配置する必要があります。依存関係は、必要に応じてサブディレクトリで編成できます。さらに、外部グラフィックファイルなどの版形設定プロセスに含める独自のファイルがある場合は、[input_working_directory](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/input_working_directory/)を設定する必要があります。また、入力ディレクトリ内にメイン入力ファイルを配置し、 `run()`メソッドの相対パスを指定したり、メインの入力ファイルがルートにある場合はまったくパスを指定したりすることもできます。 Python **の** Aspose.TeXの入力ディレクトリの概念の詳細および提供された実装については、[こちら](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/)を参照してください。

[他のTexジョブオプション](/tex/{{lang.url-fragment}}python-net/other-options/)も議論されています。

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) を使用して開発された無料の [LaTeX から PDF への変換用 Web アプリ](https://products.aspose.app/tex/conversion/latex-to-pdf) を調べることもできます。**