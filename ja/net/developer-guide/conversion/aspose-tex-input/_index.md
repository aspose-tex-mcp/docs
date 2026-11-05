---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX の入力インターフェイス | Aspose.TeX for .NET 開発者ガイド
linktitle: Aspose.TeX の入力インターフェイス
weight: 15
url: /net/aspose-tex-input/
description: Aspose.TeX API ソリューションの .NET 用変換機能で、TeX を入力形式として使用する方法をコード例とともに説明します。
keywords: aspose.tex 入力、.net tex、入力ディレクトリ、入力 zip、入力コンソール、tex オプション、iinputworkingdirectory、inputzipdirectory、inputterminal、tex 変換, searchcurrentdirectory
lastmod: "2026-11-03"
aliases: 
- /cpp/typesetting-tex-input/
- /cpp/creating-custom-tex-format/
---

{{<section overview>}}

**Aspose.TeX for .NET** の [API reference](https://reference.aspose.com/tex/net/aspose.tex.io/) を参照してください。

## The concept of the input directory

TeX 言語の I/O プリミティブはファイル名しか扱えないため、**Aspose.TeX for .NET** ではディレクトリを名前とデータのバルクのマッピングとして定義しています。データのバルクはファイル、ストリーム、配列、またはその他何でも構いません。API は入力作業ディレクトリと出力作業ディレクトリを個別に指定できるようにしています。一般的な [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) インターフェイスが提供されており、ユーザーは独自に実装できます。また、以下で説明する独自実装も用意されています。このインターフェイスは [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/) メソッドを定義しており、データストリームを返し、最初の引数として仮想的に異なる名前（実際にはマッピングキー）を受け取ってファイルの完全名を決定します。

### Getting file input from the disk file system

以下のように実装します。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputFileSystemDirectory.cs" >}}

この使用例は非常にシンプルなため、これ以上詳しく説明する必要はありません。

### Getting file input from a ZIP archive

入力ファイルを ZIP アーカイブに格納し、入力ディレクトリとして扱うこともできます。その場合は次の手順で実装します。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputZipDirectory.cs" >}}

まず、ZIP ファイルを含むストリームを作成します。その後、変換オプションを作成し、[InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) オプションに [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) クラスのインスタンスを設定します。コンストラクタの第 2 引数はアーカイブ内のベースパスです。アーカイブ全体を入力ディレクトリとして使用したい場合は空文字列を渡します。

### 作業ディレクトリでのみ入力ファイルを検索する {#looking-for-input-files-only-in-the-working-directories}

既定では、TeX エンジンは相対名の入力ファイルが必要になると、まずプロセスのカレント ディレクトリとメイン入力ファイルのディレクトリでファイルを探します。その後で初めて [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/)、[RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/)、[OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) を探します。これは単純なコンソール アプリケーションには便利ですが、結果がプロセスを起動した場所や、そこにたまたま置かれているファイルに左右される可能性があることも意味します。指定したディレクトリからのみ入力を取得したい場合は、[SearchCurrentDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/searchcurrentdirectory/) オプションを `false` に設定します。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-SearchCurrentDirectory.cs" >}}

絶対名のファイルは、このオプションに関係なく直接開かれます。同じオプションは、[数式と図のレンダリング](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/searchcurrentdirectory/)および [LaTeX の修復](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/searchcurrentdirectory/) でも使用できます。

## The concept of the input terminal

次に、端末入力についても説明します。**Aspose.TeX for .NET** は、[IInputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/) インターフェイスを定義しており、これは [TextReader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader) 実装インスタンスを返す唯一のプロパティを持ちます。提供されている実装については以下で紹介します。

### Getting terminal input from the console

これを行うには、[TerminalIn](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) オプションに [InputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/) クラスのインスタンスを設定します。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputConsoleTerminal.cs" >}}

しかし実際には、このオプションのデフォルト値が同クラスのインスタンスであるため、明示的に指定する必要はほとんどありません。この事実と、他の実装が存在しないことから、この節はデモンストレーション目的に留めておきます。

理論的には、予測可能な動作を持つインタラクティブな TeX ファイル（またはスクリプト）を扱う場合、TeX エンジンのリクエストに応答する補助スクリプトを含む入力端末の実装を作成したくなるでしょう。時間があるときにぜひお試しください！
