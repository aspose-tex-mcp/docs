---
translation: true
template: /templates/_template-cpp.md
title: その他のTEX変換出力形式| C++
linktitle: その他のTEX形式
weight: 18
url: /cpp/other-tex-formats/
description: C ++用のAspose.TeX APIソリューションの変換機能により、LaTexファイルと独自のカスタムTEXファイルを変換できます。いくつかのコードの例を次に示します。
lastmod: "2025-06-09"
---

{{<section overview>}}

現在、ラテックス以外の形式で記述されたTEXファイルを変換したいと思う可能性は非常に低いです。しかし、これは、何らかの理由でTex言語や内部を勉強している場合に可能です。とにかく、**C++ 用の Aspose.TeX**では、プレーンTex形式で記述されたファイルを変換できます。また、これらの形式で設計されたカスタム形式とタイプセットドキュメントを作成することもできます。

カスタム形式の作成から始めます。

## カスタム形式の作成

フォーマットファイルは、TEXエンジンの内部状態のバイナリダンプであることを覚えておいてください。

```C++
// Create typesetting options for no format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectIniTeX());
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    
// Run format creation.
Aspose::TeX::TeXJob::CreateFormat(u"customtex", options);
    
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```
ご覧のとおり、コードはTEXファイルを変換するためのコードに似ています。しかし、いくつかの違いがあります。

まず、[texconfig.objectinitex](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e)ジョブ構成を使用します。これは、エンジンの状態「Virgin」を離れる特別な構成です。つまり、内部パラメーターにはデフォルト値があり、コントロールシーケンスのセットはプリミティブのセットと一致します。私たちの例では、プリミティブのセットは、[ここ](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)に言及された意味で拡張されます。

次に、通常どおり、入力および出力作業ディレクトリを設定します。入力作業ディレクトリには、メイン形式のソースファイルとそのすべての依存関係を含める必要があります。

そして、2番目の重要な違いは、私たちが仕事をする方法です。今回は、static [createformat()](https://reference.aspose.com/tex/net/Aspose.TeX/texjob/createformat/)メソッドを使用します。これは、オプションとともにメインソースファイルの名前を取得し、形式名と同じでなければなりません。

## カスタム形式でTEXファイルを植林します

独自のTex形式ができたので、この形式で記述されたTexファイルを整形したいと考えています。これがコードです：

```C++
// Create typesetting options for a custom format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX(formatProvider));
options->set_JobName(u"typeset-with-custom-format");
// Specify the input working directory.
options->set_InputWorkingDirectory(wd);
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            
// Run typesetting.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(u"Congratulations! You have successfully typeset this text with your own TeX format!\\end")), System::MakeObject<XpsDevice>(), options)->Run();
            
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```
明らかに、形式を何らかの形で指定する必要があります。まず、[formatprovider](https://reference.aspose.com/tex/cpp/aspose.tex.resourceproviders/formatprovider/)クラスのインスタンスを作成する必要があります。次に、オプションコンストラクターで[texconfig.objecttex()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e)構成を使用します。これは、フォーマットプロバイダーを引数として受け取り、エンジンの「処女」状態の上に形式をロードします。

残りのコードはあなたに馴染みがあるはずです。この[ガイド](/tex/{{lang.url-fragment}}cpp/conversion/)で前述した機能を使用します。

## Plain Tex形式でTexファイルを植林します

実証されたコードからフォーマットプロバイダーを捨てると、エンジンはデフォルト形式をロードします。これは[オブジェクトTex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/)である4番目の意味でです。したがって、Plain Tex形式でTexファイルが書かれている場合、この方法では、サポートされているターゲット形式に変換できます。