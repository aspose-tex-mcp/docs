---
translation: true
template: /templates/_template-conversion-cpp.md
title: イメージへのラテックス| C ++のAspose.TeX
linktitle: 画像からラテックス
weight: 10
url: /cpp/latex-to-image/
keywords: ラテックスからPNG、ラテックスPNG、ラテックスから画像、ラテックス画像、ラテックス、JPG、ラテックスJPG、ラテックス、JPEG、ラテックスJPEG、ラテックスからTIFF、ラテックスティフ、ラテックスからBMP、ラテックスBMP
description: C ++のAspose.TeX APIソリューションを使用してTexを画像形式に変換するには、これを行う方法とコードの例を説明するこの記事を学びます。
lastmod: 2023-03-23
---

{{<section overview>}}

**C ++のAspose.TeX**も、LaTexファイルを他の多くのラスター画像形式に変換することもできます。

## ラテックスをPNGに変換する方法

C ++のコードを詳細に見てみましょう。ラテックスをPNG形式に変換する最も簡単な方法を提供します。

{{<app/converter 
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

したがって、私たちが最初に行う必要があること(まあ、時には最初のものではないこともあります)は、[テキサプティオン](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions)クラスのインスタンスを作成することです。これを行う唯一の静的方法は[consoleappoptions()](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/consoleappoptions)です。したがって、その名前の意味に困惑しないようにしましょう。このメソッドは、[texconfig](https://reference.aspose.com/tex/cpp/Aspose.TeX/texconfig/)クラスの[get_objectlatex()instance](https://reference.aspose.com/tex/cpp/Aspose.TeX/texconfig/get_objectlatex/)を取得します。この構成は、Object Tex EngineにObject Latex形式をロードし、LaTexファイルを受け入れる準備ができているように指示します。オブジェクトラテックス形式は、実際には[latex](/tex/{{lang.url-fragment}}net/what-is-latex/)形式にすぎませんが、[オブジェクトTex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定のプリミティブを使用してページメトリックをセットアップすることを除きます。

必要なオプションの最初は[outputworkingdirectory](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_outputworkingdirectory/)で、TEX出力が記述されるスペースまたはエリアを定義します。 [ここ](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/)は、c ++ **for** Aspose.TeXの出力ディレクトリの概念の詳細です。この例では、[outputfilesystemdirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory/)クラスを使用して、指定されたディレクトリまたはフォルダーに出力を書き込むことができます。

2番目のオプションは、[オブジェクトモデル](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)のターゲット形式への変換を制御する[SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/)クラスインスタンスです。ラテックスをPNGに変換しているため、[pngsaveoptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/)クラスインスタンスであり、出力画像の解像度を指定できます。

次に、[texjob](https://reference.aspose.com/tex/cpp/Aspose.TeX/texjob/)クラスのインスタンスを作成する必要があります。ファイルシステムに保存されているラテックスファイルを変換したいので、[This](https://reference.aspose.com/tex/cpp/Aspose.TeX/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor)バージョンのコンストラクターを使用します。ファイルへのフルパスを指定する必要があります。それ以外の場合、エンジンは現在のディレクトリ([currentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory))でそれを探しますが、おそらく見つけられないでしょう。それにもかかわらず、ファイルに *.tex* 1がある場合、拡張子を省略する場合があります。エンジンは自動的に追加されます。コンストラクターの2番目の引数は、[デバイス](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device)クラスインスタンスです。ラテックスをPNGに変換しているため、[Imagedevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device)クラス(サポートされているすべての画像形式に共通)インスタンスです。最後の議論として、最近準備された変換オプションに合格します。

今やるべきことは、仕事を[走る](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job#a0bc7f8b329ea1f19cbba84bf2060f6fb)だけです。

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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

出力ディレクトリとして指定したフォルダーに、エンジンの労働力の他の「果物」があります。これらはトランスクリプトファイルであり、**ここにあります！**、メインの出力PNG画像ファイルです。

## メイン出力PNGファイルを書き込む代替方法

画像データをバイト配列の配列として取得する別の方法があり、2番目のディメンションの各配列は別のページの画像データを表します。

```C++
    // Create conversion options for Object LaTeX format on Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
    // Specify the file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Initialize the options for saving in PNG format.
    options->set_SaveOptions(System::MakeObject<PngSaveOptions>());
    // Run LaTeX to PNG conversion.
    System::SharedPtr<ImageDevice> device = System::MakeObject<ImageDevice>();
    System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), device, options)->Run();
    
    // Save pages file by file.
    for (int32_t i = 0; i < device->get_Result()->get_Length(); i++)
    {
        {
            System::SharedPtr<System::IO::Stream> fs = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, System::String(u"page-") + (i + 1) + u".png"), System::IO::FileMode::Create);
            // Clearing resources under 'using' statement
            System::Details::DisposeGuard<1> __dispose_guard_0({ fs});
            // ------------------------------------------
            
            try
            {
                fs->Write(device->get_Result()[i], 0, device->get_Result()[i]->get_Length());
            }
            catch(...)
            {
                __dispose_guard_0.SetCurrentException(std::current_exception());
            }
        }
    }
```

* "page-n.png" *ファイルは、指定する任意のパスに書き込まれます。 [PDF出力](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)とは異なり、それらは出力ディレクトリに書き込まれた出力PNGファイルを複製します。

## 入力オプションについて

メイン入力ファイルに、基本的なラテックスシステムに含まれておらず、サポートされているパッケージに含まれていないパッケージなどの依存関係が必要な場合は、[RequiredInputDirectory](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_requiredinputdirectory)オプションを設定する必要があります。依存関係は、サブディレクトリで任意に組織される場合があります。タイプセットプロセス、たとえば外部グラフィックファイルに沿って含める独自のファイルがある場合は、それらのファイルが収集される場所へのパスを使用して[inputWorkingDirectory](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_inputworkingdirectory)を設定する必要があります。また、入力ディレクトリ内のどこかにメイン入力ファイルを配置し、 `run()`メソッドの相対パスを指定することもできます(または、メイン入力ファイルがルートにある場合はパスをまったく指定しません)。 [ここ](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/)は、c ++ **の** Aspose.TeXの入力ディレクトリの概念の詳細であり、実装を提供しています。

他のTEXジョブオプションについて説明します[ここ](/tex/{{lang.url-fragment}}cpp/other-options/)。

**[.NETのAsops.Tex](https://products.aspose.com/tex/net/)AP​​Iに基づいて構築された無料のLaTex-to-PNG変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-png)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/cpp/)はC ++バージョンページです。**

以下では、他のサポートされているラスター画像形式へのラテックス変換について説明します。実際には詳細がないからといって、詳細には触れません。唯一の違いは、変換オプションの[SaveOptions](https://reference.aspose.com/tex/cpp/Aspose.TeX/texoptions/set_saveoptions)プロパティのタイプです。

## ラテックスをJPEGに変換する方法

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**[.NETのAspose.TeX](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のLaTex-to-JPEGコンバージョン[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-jpg)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/cpp/)はC ++バージョンページです。**

## ラテックスをTIFFに変換する方法

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**[.netのAspose.TeX](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のラテックス間変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-tiff)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/cpp/)はC ++バージョンページです。**

## ラテックスをBMPに変換する方法

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**[.NETのasops.tex](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のラテックスからBMPへの変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-bmp)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/cpp/)はC ++バージョンページです。**