---
translation: true
template: /templates/_template-net.md
title: LaTeX から PDF へ | .NET
linktitle: LaTeX から PDF へ
weight: 11
url: /net/latex-to-pdf/
keywords: LaTeX to PDF, LaTeX PDF, LaTeX を PDF に変換
description: Aspose.TeX API ソリューション for .NET を使用して TeX を PDF に変換する方法を、この記事で学び、手順とコード例をご紹介します。
lastmod: "2026-04-22"
---

{{<section overview>}}


## LaTeX を PDF に変換する方法

C# のコードを詳しく見て、LaTeX を PDF 形式に変換する最も簡単な方法をご紹介します。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

そこで、最初に（必ずしも最初ではないこともありますが）行うべきことは、[TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) のインスタンスを作成することです。このクラスの唯一の静的メソッドは [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/) であり、その名前に惑わされないでください。このメソッドは、[TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/) のインスタンスを受け取り、これは [LaTeX file](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) の変換に正確に適しています。この構成は、Object TeX エンジンに Object LaTeX 形式をロードさせ、LaTeX ファイルを受け入れる準備をさせます。Object LaTeX 形式は実際には単なる [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/) 形式で、ページメトリックを設定するために [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) 固有のプリミティブを使用します。

必要なオプションの最初は [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) で、TeX の出力が書き込まれる領域を定義します。[Here](/tex/{{lang.url-fragment}}net/aspose-tex-output/) には **Aspose.TeX for .NET** における出力ディレクトリの概念の詳細があります。この例では、[OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) クラスを使用し、指定したディレクトリ（フォルダー）に出力を書き込めるようにします。

次のオプションは [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) クラスのインスタンスで、[object model](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) をターゲット形式に変換する処理を制御します。LaTeX を PDF に変換するので、使用するのは [PdfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) クラスのインスタンスです。

次に、[TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/) クラスのインスタンスを作成します。ファイルシステムに保存された LaTeX ファイルを変換したい場合は、[this](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) コンストラクタを使用します。ファイルへのフルパスを指定しなければなりません。そうしなければ、エンジンは現在のディレクトリ（[CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)）で検索し、見つからない可能性が高いです。拡張子が *.tex* であれば省略可能で、エンジンが自動的に付加します。コンストラクタの第2引数は [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/) クラスのインスタンスです。LaTeX を PDF に変換するので、[PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/) クラスのインスタンスを使用します。最後の引数として、先ほど準備した変換オプションを渡します。

残る作業は、ジョブを [run](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) することだけです。

実行が成功したかどうかに関わらず、最初に表示される結果はターミナル出力です。成功した場合は以下のようになります：

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

出力ディレクトリとして指定したフォルダー内に、エンジンの成果物としての他の「成果物」があります。それはトランスクリプトファイルと、**こちらです！** メインの出力 PDF ファイルです。

## メイン出力 PDF ファイルを書き出す別の方法

[PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/) クラスの別のコンストラクタがあり、結果の PDF ファイルを別の方法で取得できます。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Alternative.cs" >}}

指定ディレクトリ内の *any-name.pdf* ファイルがメインの出力 PDF ファイルとなります。同時に、[image output](/tex/{{lang.url-fragment}}net/latex-to-image/) と異なり、変換オプションで定義された出力ディレクトリには PDF ファイルは生成されません。例外として、*any-name.pdf* は [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) オプションで [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) を使用して割り当てた同じファイルシステムディレクトリ内に配置されます。

## 入力オプションについて

メインの入力ファイルが基本的な LaTeX システムやサポートされているパッケージに含まれない依存関係（例: パッケージ）を必要とする場合は、[OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) オプションと同様の方法で [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) オプションを設定し、依存ファイルをそのディレクトリに置く必要があります。依存関係はサブディレクトリに自由に整理できます。組版プロセスで外部画像ファイルなど独自のファイルを含める場合は、[InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) を設定し、それらのファイルが格納されている場所へのパスを指定する必要があります。また、メイン入力ファイルを入力ディレクトリ内の任意の場所に配置し、`run()` メソッドで相対パスを指定することもできます（ルートにある場合はパスなしでも可）。[Here](/tex/{{lang.url-fragment}}net/aspose-tex-input/) には **Aspose.TeX for .NET** における入力ディレクトリの概念と実装の詳細が掲載されています。

他の TeX ジョブオプションについては、[here](/tex/{{lang.url-fragment}}net/other-options/) を参照してください。

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) を基に構築された無料の LaTeX から PDF への変換 [web app](https://products.aspose.app/tex/conversion/latex-to-pdf) もご利用いただけます。**
