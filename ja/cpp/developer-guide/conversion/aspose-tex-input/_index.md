---
translation: true
template: /templates/_template-cpp.md
title: Aspose.TeXの入力インターフェイス| C ++
linktitle: Aspose.TeXの入力インターフェイス
weight: 15
url: /cpp/aspose-tex-input/
description: 入力形式として、Texを使用したC ++のAsophes.Tex APIソリューションの変換機能については、コードの例で説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

I/O実装の正式な定義については、**C++ 用の Aspose.TeX** [api参照](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.i_o)を参照してください。

## 入力ディレクトリの概念

Tex言語のI/O Primitivesはファイル名のみを扱うことができるため、**C++ 用の Aspose.TeX**は、ディレクトリを名前とデータのバルクのマッピングとして定義します。データの大部分は、ファイル、ストリーム、配列などであるはずです。APIにより、入力および出力作業ディレクトリを個別に指定できます。一般的な[iinputworkingdirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory)インターフェイスを提供します。これは、ユーザーが独自の目的で実装できる。また、独自の実装も提供します。これについては、以下で説明します。インターフェイスは[getFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/getfile)メソッドを定義します。これは、データストリームを返してファイルのフルネームを決定しますが、仮説的に異なる名前を最初の引数として使用します。実際、マッピングキーです。

### ディスクファイルシステムからファイル入力を取得します

これが私たちがそれをする方法です：

```C++
// Create conversion options instance.
...
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));

```

このユースケースは非常に簡単なので、もうそれに集中する必要はありません。

### ZIPアーカイブからファイル入力を取得します

また、入力ファイルをZIPアーカイブに配置して、入力ディレクトリと見なすこともできます。この場合、次のように進める必要があります。

```C++
    // Open a stream on a ZIP archive that will serve as the input working directory.
    System::SharedPtr<System::IO::Stream> inZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::InputDirectory, u"zip-in.zip"), System::IO::FileMode::Open);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for input.
    options->set_InputWorkingDirectory(System::MakeObject<InputZipDirectory>(inZipStream, u"in"));
```

最初に、zipファイルを含むストリームを作成します。次に、変換オプションを作成した後、[inputzipdirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputzipdirectory)クラスのインスタンスになるように[inputWorkingDirectory](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_inputworkingdirectory)オプションを設定します。コンストラクターの2番目の引数は、アーカイブ内のベースパスです。アーカイブ全体を入力ディレクトリにしたい場合は、空の文字列を渡す必要があります。 

## 入力端子の概念

さて、端子入力もあることを覚えておく時が来ました。これについては、**C++ 用の Aspose.TeX**は、[textreader](https://reference.aspose.com/tex/cpp/class/system.i_o.text_reader)実装インスタンスを返すプロパティが1つだけある一般[iinputterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputterminal)インターフェイスを定義します。実装を以下で説明します。

### コンソールから端子入力を取得します

これを行うには、[inputConsoleterminal](https://reference.aspose.com/tex/cpp/class/aspose.te_x.i_o.input_console_terminal)クラスのインスタンスになるには、[Terminalin](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_terminalin)オプションを設定する必要があります。

```C++
// Create conversion options instance.
...
// Specify the console as the input terminal.
options->set_TerminalIn(System::MakeObject<InputConsoleTerminal>()); // Default. Not necessary to specify.

```

しかし、真実を伝えるために、これはオプションのデフォルト値であるため、指定する必要はありません。 :-)この事実のため、および他の実装がない限り、このセクションはデモンストレーションのみを提供します。

理論的には、予測可能な動作を備えたインタラクティブなTEXファイル(またはスクリプト)がある場合、TEXエンジンの要求に応答するための補完的なスクリプトを含む入力端子のバージョンを実装することをお勧めします。時間があるときは手を試してみてください！