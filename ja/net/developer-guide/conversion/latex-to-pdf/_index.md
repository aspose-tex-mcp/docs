---
translation: true
template: /templates/_template-net.md
title: ラテックスからPDF | .netのAspose.TeX
linktitle: ラテックスからPDF
weight: 11
url: /net/latex-to-pdf/
keywords: ラテックスからPDF、ラテックスPDF、ラテックスをPDFに変換します
description: .NETのAspose.TeX APIソリューションを使用してTexをPDFに変換するには、この記事を学び、これを行う方法とコードの例を説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}


## ラテックスをPDFに変換する方法

C＃のコードを詳細に見てみましょう。ラテックスをPDF形式に変換する最も簡単な方法を提供します。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.cs" >}}

したがって、私たちが最初に行う必要があること(まあ、時には最初のものではないこともあります)は、[テキサプティオン](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/)クラスのインスタンスを作成することです。これを行う唯一の静的方法は[consoleappoptions()](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/consoleappoptions/)です。したがって、その名前の意味に困惑しないようにしましょう。このメソッドは、[TexConfig](https://reference.aspose.com/tex/net/Aspose.TeX/texconfig/)クラスの[インスタンス](https://reference.aspose.com/tex/net/Aspose.TeX/texconfig/objectlatex/)を取ります。これは[LaTexファイル](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)の変換に正確に適しています。この構成は、Object Tex EngineにObject Latex形式をロードし、LaTexファイルを受け入れる準備ができているように指示します。オブジェクトラテックス形式は、実際には[latex](/tex/{{lang.url-fragment}}net/what-is-latex/)形式にすぎませんが、[オブジェクトTex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定のプリミティブを使用してページメトリックをセットアップすることを除きます。

必要なオプションの最初は[outputworkingdirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/outputworkingdirectory/)で、TEX出力が記述されるスペースまたはエリアを定義します。 [ここ](/tex/{{lang.url-fragment}}net/aspose-tex-output/)は、.net **for .net** for ** Aspose.TeXの出力ディレクトリの概念の詳細です。この例では、[outputfilesystemdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)クラスを使用して、指定されたディレクトリまたはフォルダーに出力を書き込むことができます。

2番目のオプションは、[オブジェクトモデル](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)のターゲット形式への変換を制御する[SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/)クラスインスタンスです。ラテックスをPDFに変換しているため、[PDFSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)クラスインスタンスです。

次に、[texjob](https://reference.aspose.com/tex/net/Aspose.TeX/texjob/)クラスのインスタンスを作成する必要があります。ファイルシステムに保存されているラテックスファイルを変換したいので、[This](https://reference.aspose.com/tex/net/Aspose.TeX/texjob/texjob/)バージョンのコンストラクターを使用します。ファイルへのフルパスを指定する必要があります。それ以外の場合、エンジンは現在のディレクトリ([currentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory))でそれを探しますが、おそらく見つけられないでしょう。それにもかかわらず、ファイルに *.tex* 1がある場合、拡張子を省略する場合があります。エンジンは自動的に追加されます。コンストラクターの2番目の引数は、[デバイス](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/)クラスインスタンスです。ラテックスをPDFに変換しているため、[PDFDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)クラスインスタンスです。最後の議論として、最近準備された変換オプションに合格します。

今やるべきことは、仕事を[走る](https://reference.aspose.com/tex/net/Aspose.TeX/texjob/run/)だけです。

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

出力ディレクトリとして指定したフォルダーに、エンジンの労働力の他の「果物」があります。これらはトランスクリプトファイルであり、**ここにあります！**、メイン出力PDFファイル。

## メイン出力PDFファイルを書き込む代替方法

[pdfdevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/)クラスの別のコンストラクターがあります。これにより、結果のPDFファイルを代替方法で取得できます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.cs" >}}

指定されたディレクトリの *any-name.pdf* ファイルは、メインの出力PDFファイルになります。同時に、[画像出力](/tex/{{lang.url-fragment}}net/latex-to-png/#an-alternative-way-to-write-main-output-png-files)とは異なり、変換オプションで定義された出力ディレクトリにPDFファイルは見つかりません。例外： *any-name.pdf* は、[outputFilesSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)を使用して[outputWorkingDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/outputworkingdirectory/)オプションに割り当てられている同じファイルシステムディレクトリに(そのパスで)配置されます。

## 入力オプションについて

メイン入力ファイルに、基本的なラテックスシステムに含まれておらず、サポートされているパッケージに含まれていないパッケージなどの依存関係が必要な場合は、[rebyputWorkingDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/outputworkingdirectory/)オプションを設定し、そのディレクトリに依存関係を設定し、[rebysputDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/requiredinputdirectory/)オプションを設定する必要があります。依存関係は、サブディレクトリで任意に組織される場合があります。タイプセットプロセス、たとえば外部グラフィックファイルに沿って含める独自のファイルがある場合は、それらのファイルが収集される場所へのパスを使用して[inputWorkingDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/inputworkingdirectory/)を設定する必要があります。また、入力ディレクトリ内のどこかにメイン入力ファイルを配置し、 `run()`メソッドの相対パスを指定することもできます(または、メイン入力ファイルがルートにある場合はパスをまったく指定しません)。 [ここ](/tex/{{lang.url-fragment}}net/aspose-tex-input/)は、.net **の** Aspose.TeXの入力ディレクトリの概念の詳細であり、実装が提供されています。

他のTEXジョブオプションについて説明します[ここ](/tex/{{lang.url-fragment}}net/other-options/)。

**[.NET APIのasops.tex](https://products.aspose.com/tex/net/)に基づいて構築された無料のラテックスからPDFへの変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-pdf)をチェックアウトすることもできます。**