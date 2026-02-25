---
translation: true
template: /templates/_template-net.md
title: Aspose.TeXの出力インターフェイス | .NET
linktitle: Aspose.TeXの出力インターフェイス
weight: 16
url: /net/aspose-tex-output/
description: .NET向けAspose.TeX APIソリューションの変換機能について、出力フォーマットとしてのTeXをコード例と共に説明します。
keywords: aspose tex 出力、.net tex、出力ディレクトリ、出力 zip、出力コンソール、出力ターミナル、tex オプション、出力ファイルディレクトリ、出力 zip ディレクトリ、tex 変換
lastmod: "2026-02-25"
---

{{<section overview>}}

正式な I/O 実装の定義については、**Aspose.TeX for .NET** の [API リファレンス](https://reference.aspose.com/tex/net/aspose.tex.io/) を参照してください。

## 出力ディレクトリの概念

TeX 言語の I/O プリミティブはファイル名しか扱えないため、Aspose.TeX はディレクトリを名前とデータの塊とのマッピングとして定義します。データの塊はファイル、ストリーム、配列、その他あらゆるものと想定されます。API は入力と出力の作業ディレクトリを別々に指定できるようにします。出力用の一般的な [IOutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) インターフェイスを提供しており、ユーザーはそれを独自の目的で実装できます。また、以下で説明する独自の実装も提供しています。このインターフェイスは [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) を継承しており、エンジンはまずファイルを作成・書き込み、そしてそれを再び読み取ることがあります。インターフェイス独自のメソッド [GetOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) は書き込み用ストリームを返し、[GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/) が返すのは読み取り用ストリームです。

### ディスクファイルシステムへのファイル出力

前述の [上記](/tex/{{lang.url-fragment}}net/latex-to-image/) で述べたように、[OutputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) の最も一般的な値は、おそらく [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) クラスのインスタンスです。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputFileSystemDirectory.cs" >}}

このユースケースは非常にシンプルなので、これ以上詳しく説明する必要はありません。

### ZIP アーカイブへのファイル出力

ファイル（またはストリーム）を作成し、TeX エンジンにそれを ZIP アーカイブとして出力ファイルを格納させることもできます。例は次のとおりです：

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputZipDirectory.cs" >}}

まず、ZIP ファイル用の出力ストリームを作成します。その後、変換オプションを作成し、[OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) オプションを [OutputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) クラスのインスタンスに設定します。

## 出力ターミナルの概念

出力にはもう一つ重要な部分があります --- ターミナル出力です。これについては、**Aspose.TeX for .NET** は [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) インターフェイスを定義しており、[TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter) 実装インスタンスを返す唯一のプロパティを持ちます。提供されている実装は以下で説明します。

### コンソールへのターミナル出力

これを行うには、[TerminalOut](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) オプションを [OutputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) クラスのインスタンスに設定する必要があります。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputConsoleTerminal.cs" >}}

これはオプションのデフォルト値でもあるため、明示的に指定する必要は実質的にありません。そのため、このセクションはデモンストレーション目的にとどまります。

### ファイルへのターミナル出力

入力ターミナルとは異なり、**Aspose.TeX for .NET** は [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) の実装を提供しており、ターミナル出力を任意の出力ディレクトリ内のファイルに書き込むことができます。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputFileTerminal.cs" >}} 

ここでは、TeX エンジンにターミナル出力を名前が [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm のファイルに書き込むよう指示します。このファイルは他の出力と同じディレクトリに保存されます。ただし、必ずしもそうする必要はありません。任意の [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) 実装のインスタンスをコンストラクタに渡すことも可能です。
