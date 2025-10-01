---
translation: true
template: /templates/_template-java.md
title: ラテックスからPDF | Java
linktitle: ラテックスからPDF
weight: 11
url: /java/latex-to-pdf/
keywords: ラテックスからPDF、ラテックスPDF、ラテックスをPDFに変換します
description: JavaのAspose.TeX APIソリューションを使用してTexをPDFに変換するには、この記事を学び、これを行う方法とコードの例を説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}


## ラテックスをPDFに変換する方法

LaTexをPDF形式に変換する最も簡単な方法を提供するJavaコードを詳しく見てみましょう。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.java" >}}

したがって、最初に行う必要があることは(後でわかったように、最初にそうではない場合があります)、[Texoptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions)クラスのインスタンスを作成することです。これを行う唯一の静的方法は[consoleappoptions()](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#consoleAppOptions-com.Aspose.TeX.TeXConfig-)です。そのため、その名前の意味を悩ませないでください。このメソッドは、[TexConfig](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXConfig)クラスの[インスタンス](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXConfig#objectLaTeX--)を取ります。これは[LaTexファイル](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)の変換に正確に適しています。この構成は、オブジェクトTex Engineにオブジェクトラテックス形式をロードし、LaTexファイルを受け入れる準備ができるように指示します。オブジェクトラテックス形式は、[Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定のプリミティブを使用してページメトリックをセットアップすることを除いて、[LaTex](/tex/{{lang.url-fragment}}net/what-is-latex/)形式にすぎません。

必要なオプションの最初は[outputworkingdirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getOutputWorkingDirectory--)で、TEX出力が記述されるスペースまたはエリアを定義します。 [ここ](/tex/{{lang.url-fragment}}java/aspose-tex-output/)は、java **for** Aspose.TeXの出力ディレクトリの概念の詳細です。この例では、[outputfilesystemdirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/OutputFileSystemDirectory)クラスを使用して、指定されたディレクトリまたはフォルダーに出力を書き込むことができます。

2番目のオプションは、[オブジェクトモデル](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)のターゲット形式への変換を制御する[SaveOptions](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/SaveOptions)クラスインスタンスです。ラテックスをPDFに変換しているため、[PDFSaveOptions](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/PdfSaveOptions)クラスインスタンスです。

次に、[texjob](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXJob)クラスのインスタンスを作成する必要があります。ファイルシステムに保存されているラテックスファイルを変換したいので、[This](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXJob#TeXJob-java.lang.String-com.Aspose.TeX.rendering.Device-com.Aspose.TeX.TeXOptions-)バージョンのコンストラクターを使用します。ファイルへのフルパスを指定する必要があります。それ以外の場合、エンジンは現在のディレクトリ([here](https://docs.oracle.com/javase/7/docs/api/java/io/File.html))で定義されており、おそらく見つけられない可能性があります。それにもかかわらず、ファイルに *.tex* 1がある場合、拡張子を省略する場合があります。エンジンは自動的に追加されます。コンストラクターの2番目の引数は、[デバイス](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/Device)クラスインスタンスです。ラテックスをPDFに変換しているため、[PDFDevice](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/PdfDevice)クラスインスタンスです。最後の議論として、最近準備された変換オプションに合格します。

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

出力ディレクトリとして指定したフォルダーにエンジンの実行の他の製品があります。これらは、トランスクリプト(.log)ファイルと**voila！**、メイン出力PDFファイルになります。

## メイン出力PDFファイルを書き込む代替方法

[pdfdevice](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/PdfDevice#PdfDevice-java.io.OutputStream-)クラスの別のコンストラクターがあります。これにより、結果のPDFファイルを代替方法で取得できます。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.java" >}}

指定されたディレクトリの *any-name.pdf* ファイルは、メインの出力PDFファイルになります。同時に、[画像出力](/tex/{{lang.url-fragment}}java/latex-to-png/#an-alternative-way-to-write-main-output-png-files)とは異なり、変換オプションで定義された出力ディレクトリにPDFファイルは見つかりません。例外： *any-name.pdf* は、[outputFilesSystemDirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/OutputFileSystemDirectory)を使用して[outputWorkingDirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getOutputWorkingDirectory--)オプションに割り当てられている同じファイルシステムディレクトリに(そのパスで)配置されます。

## 入力オプションについて

メイン入力ファイルに、基本的なラテックスシステムに含まれておらず、サポートされているパッケージに含まれていないパッケージなどの依存関係が必要な場合は、[rebyputWorkingDirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getOutputWorkingDirectory--)オプションを設定し、そのディレクトリに依存関係を設定し、[rebysputDirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getRequiredInputDirectory--)オプションを設定する必要があります。依存関係は、サブディレクトリで任意に組織される場合があります。タイプセットプロセス、たとえば外部グラフィックファイルに沿って含める独自のファイルがある場合は、それらのファイルが収集される場所へのパスを使用して[inputWorkingDirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getInputWorkingDirectory--)を設定する必要があります。また、入力ディレクトリ内のどこかにメイン入力ファイルを配置し、 `run()`メソッドの相対パスを指定することもできます(または、メイン入力ファイルがルートにある場合はパスをまったく指定しません)。 [ここ](/tex/{{lang.url-fragment}}java/aspose-tex-input/)は、Java **の** Aspose.TeXの入力ディレクトリの概念の詳細であり、実装を提供しています。

他のTEXジョブオプションについて説明します[ここ](/tex/{{lang.url-fragment}}java/other-options/)。

**[.netのAspose.TeX](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のLaTex-to-PDF変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-pdf)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/java/)はJavaバージョンページです。**