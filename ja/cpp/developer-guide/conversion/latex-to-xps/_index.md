---
translation: true
template: /templates/_template-cpp.md
title: ラテックスからXPS | C++
linktitle: ラテックスからXPS
weight: 12
url: /cpp/latex-to-xps/
description: C ++用のAspose.TeX APIソリューションの変換機能により、LaTexファイルをTEH XPS形式に変換できます。いくつかのコードの例を次に示します。
lastmod: "2025-06-09"
---

{{<section overview>}}

**Aspose.TeX** がサポートするもう一つのターゲット形式は [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) です。**XPS** ファイルは、ページ区切りのドキュメントコンテンツと、特定のビューア（Windows XPS Viewer など）での適切な表示や印刷に必要なメタデータを含む ZIP パッケージです。パッケージ内のすべてのデータはファイルで表現されます。ファイルの中にはバイナリ形式のものもあり、画像、フォント、ICC プロファイルなどのリソースが含まれています。また、様々な特定スキーマで記述された XML ファイルもあります。後者には、ドキュメントデータ自体を含むファイルも含まれます。ドキュメントデータは複数のファイルで構成され、各ファイルにはドキュメントの各ページのデータが含まれています。これらのファイルは、単一のページ要素と、子要素（*Canvas*、*Path*、*Glyphs*）のツリーで構成されます。*Canvas* はグループ化要素であり、他の *Canvas*、*Path*、*Glyphs* を含めることができます。その役割は、すべての子要素の外観をグループとして制御することです。 *Path*要素はベクターグラフィックのパスを定義するために使用されます。また、*Glyphs*要素はテキストコンテンツを定義するために使用されます。これら3つの要素はすべて、外観のさまざまな側面を定義するプロパティを持っています。

[**Aspose.Page**](https://products.aspose.com/page/)ライブラリがあり、XPSドキュメントを操作するためのAPIを提供し、PDFおよびラスター画像形式に変換します。

## ラテックスをXPSに変換する方法

XPSへの変換は、[saveoptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions/)に加えて、[xpsdevice](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.xps/xpsdevice/)クラスのインスタンスにデバイスを変更する必要があることを除いて、[ラスター画像形式への変換](/tex/{{lang.url-fragment}}cpp/latex-to-image/)と同じくらい簡単です。

```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### メイン出力XPSファイルを書き込む代替方法

[XPSDevice](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.xps/xpsdevice/#aa24d2c38c5d134d90782b27ba090116a)クラスの別のコンストラクターがあります。これにより、結果のXPSファイルを別の方法で取得できます。

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> xpsStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.xps"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ xpsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in XPS format.
            options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<XpsDevice>(xpsStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

効果は[ここ](https://products.aspose.app/tex/conversion/latex-to-xps)を取得するのと同じです。

**[.NETのAsops.Tex](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のLaTex-to-XPS変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-xps)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/cpp/)はC ++バージョンページです。**