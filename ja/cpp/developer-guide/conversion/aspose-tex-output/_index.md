---
translation: true
template: /templates/_template-cpp.md
title: Aspose.TeXの出力インターフェイス| C++
linktitle: Aspose.TeXの出力インターフェイス
weight: 16
url: /cpp/aspose-tex-output/
description: C++のAspose.TeX APIソリューションの変換機能は、Texを入力形式として使用し、出力形式としてコード例で説明されています。
lastmod: "2026-04-20"
---

{{<section overview>}}

I/O実装の正式な定義については、**C++ 用の Aspose.TeX** [api参照](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.i_o)を参照してください。

## 出力ディレクトリの概念

Tex言語のI/O Primitivesはファイル名のみを扱うことができるため、Aspose.TeXは、ディレクトリを名前とデータのバルクのマッピングとして定義します。データの大部分は、ファイル、ストリーム、配列などであるはずです。APIにより、入力および出力作業ディレクトリを個別に指定できます。一般的な[ioutputworkingdirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory)の出力のインターフェイスを提供します。これは、ユーザーが独自の目的で実装できます。また、独自の実装も提供します。これについては、以下で説明します。インターフェイスは[iinputworkingdirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory)を拡張します。エンジンが最初にファイルを作成して書き込み、次に読み戻すことができるためです。インターフェイス独自のメソッド[getOutputFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory/getoutputfile)は、[getFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/getfile)によって返された読み取りを読み取るストリームとは対照的に、ストリームを返して書き込みます。

### ディスクファイルシステムへのファイル出力の書き込み

[上記](/tex/{{lang.url-fragment}}cpp/latex-to-image/)に述べたように、[outputDirectory](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_outputworkingdirectory)の最も一般的な値は、[outputFilesSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory)クラスのインスタンスになる可能性があります。

これが私たちがそれを設定する方法です：

```C++
// Create conversion options instance.
...
// Specify a file system working directory for the output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));

```
このユースケースは非常に簡単なので、もうそれに集中する必要はありません。

### ZIPアーカイブへのファイル出力の書き込み

また、ファイル(またはストリーム)を作成し、TexエンジンにZIPアーカイブとして使用して出力ファイルを保存することもできます。ここにあります：

```C++
    // Open the stream for the ZIP archive that will serve as the output working directory.
    System::SharedPtr<System::IO::Stream> outZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"zip-pdf-out.zip"), System::IO::FileMode::Create);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputZipDirectory>(outZipStream));
```

まず、zipファイルの出力ストリームを作成します。次に、変換オプションを作成した後、[outputzipdirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputzipdirectory)クラスのインスタンスになるように[outputworkingdirectory](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_outputworkingdirectory)オプションを設定します。

## 出力端子の概念

出力には別の重要な部分があります---端子出力。これについては、**C++ 用の Aspose.TeX**は、[textwriter](https://reference.aspose.com/tex/cpp/system.io/textwriter)実装インスタンスを返すプロパティが1つだけある一般[ioutputterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal)インターフェイスを定義します。実装を以下で説明します。

### コンソールへの端子出力の書き込み

これを行うには、[OutputConsoleterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputconsoleterminal)クラスのインスタンスになるには、[Terminalout](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_terminalout)オプションを設定する必要があります。

```C++
// Create conversion options instance.
...
// Specify the console as the output terminal.
options->set_TerminalOut(System::MakeObject<OutputConsoleTerminal>()); // Default. No need to specify.

```

繰り返しますが、これはオプションのデフォルト値であるため、指定する必要はありません。このため、このセクションはデモンストレーションのみを提供します。

### ファイルへの端子出力の書き込み

入力端子とは異なり、**C++ 用の Aspose.TeX**は[ioutputterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal)の実装を提供します。

```C++
// Create conversion options instance.
...
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options->set_TerminalOut(System::MakeObject<OutputFileTerminal>(options->get_OutputWorkingDirectory()));

```

ここでは、TEXエンジンに、[<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trmという名前のファイルに端子出力を書き込むように依頼します。しかし、これは必要ありません。 [ioutputterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal)の実装の他のインスタンスをコンストラクターに渡すこともできます。