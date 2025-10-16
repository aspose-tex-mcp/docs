---
translation: true
template: /templates/_template-net.md
title: Aspose.TeXの出力インターフェイス| .NET
linktitle: Aspose.TeXの出力インターフェイス
weight: 16
url: /net/aspose-tex-output/
description: Texを使用した.NET用のAspose.TeX APIソリューションの変換機能、ここではコードの例で説明されています。
keywords: aspose tex 出力、.net tex、出力ディレクトリ、出力 zip、出力コンソール、出力ターミナル、tex オプション、出力ファイル ディレクトリ、出力 zip ディレクトリ、tex 変換
lastmod: "2025-06-09"
---

{{<section overview>}}

I/O実装の正式な定義については、.NET **[API参照](https://reference.aspose.com/tex/net/aspose.tex.io/)の** Aspose.TeXを参照してください。

## 出力ディレクトリの概念

Tex言語のI/O Primitivesはファイル名のみを扱うことができるため、Aspose.TeXは、ディレクトリを名前とデータのバルクのマッピングとして定義します。データの大部分は、ファイル、ストリーム、配列などであるはずです。APIにより、入力および出力作業ディレクトリを個別に指定できます。一般的な[ioutputworkingdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/)の出力のインターフェイスを提供します。これは、ユーザーが独自の目的で実装できます。また、独自の実装も提供します。これについては、以下で説明します。インターフェイスは[iinputworkingdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/)を拡張します。エンジンが最初にファイルを作成して書き込み、次に読み戻すことができるためです。インターフェイス独自のメソッド[getOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/)は、[getFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/)によって返された読み取りを読み取るストリームとは対照的に、ストリームを返して書き込みます。

### ディスクファイルシステムへのファイル出力の書き込み

[上記](/tex/{{lang.url-fragment}}net/latex-to-image/)に述べたように、[outputDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/outputworkingdirectory/)の最も一般的な値は、[outputFilesSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)クラスのインスタンスになる可能性があります。

これが私たちがそれを設定する方法です：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.cs" >}}

このユースケースは非常に簡単なので、もうそれに集中する必要はありません。

### ZIPアーカイブへのファイル出力の書き込み

また、ファイル(またはストリーム)を作成し、TexエンジンにZIPアーカイブとして使用して出力ファイルを保存することもできます。ここにあります：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.cs" >}}

まず、zipファイルの出力ストリームを作成します。次に、変換オプションを作成した後、[outputzipdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)クラスのインスタンスになるように[outputworkingdirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/outputworkingdirectory/)オプションを設定します。

## 出力端子の概念

出力には別の重要な部分があります---端子出力。これについては、**Aspose.TeX for .net**が一般的な[ioutputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/)インターフェイスを定義します。実装を以下で説明します。

### コンソールへの端子出力の書き込み

これを行うには、[OutputConsoleterminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)クラスのインスタンスになるには、[Terminalout](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/terminalout/)オプションを設定する必要があります。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.cs" >}}

繰り返しますが、これはオプションのデフォルト値であるため、指定する必要はありません。このため、このセクションはデモンストレーションのみを提供します。

### ファイルへの端子出力の書き込み

入力端子とは異なり、**Aspose.TeX for .net**は、[ioutputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/)の実装を提供します。これにより、端子出力を出力ディレクトリのファイルに書き込むことができます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.cs" >}} 

ここでは、TEXエンジンに、[<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trmという名前のファイルに端子出力を書き込むように依頼します。しかし、これは必要ありません。 [ioutputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/)の実装の他のインスタンスをコンストラクターに渡すこともできます。