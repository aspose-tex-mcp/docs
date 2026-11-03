---
translation: true
template: /templates/_template-net.md
title: LaTeX から画像へ | .NET
linktitle: LaTeX から画像へ
weight: 10
url: /net/latex-to-image/
aliases: 
- /net/latex-to-png/
- /net/latex-to-svg/
keywords: latex to png, latex png, latex to image, latex image, latex to jpg, latex jpg, latex to jpeg, latex jpeg, latex to tiff, latex tiff, latex to bmp, latex bmp
description: Aspose.TeX API ソリューション for .NET を使用して TeX を画像形式に変換する方法とコード例をご覧ください。
lastmod: "2026-11-02"
---

{{<section overview>}}

**Aspose.TeX for .NET** は、LaTeX ファイルをさまざまなラスタ画像形式に変換できる機能を提供します。

## LaTeX を PNG に変換する方法

C# のコード例を詳しく見て、LaTeX を PNG 形式に変換する最も簡単な方法を説明します。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Simplest.cs" >}}

まず最初に（必ずしも最初ではないこともあります）が行うべきことは、[TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) クラスのインスタンスを作成することです。このインスタンスを作成する唯一の静的メソッドは [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/) であり、名前に惑わされないでください。このメソッドは [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/) クラスの [ObjectLaTeX インスタンス](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) を受け取り、これは正確に [LaTeX ファイル](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) を変換するために適しています。この構成は Object TeX エンジンに Object LaTeX フォーマットを読み込み、LaTeX ファイルを受け入れる準備ができていることを指示します。Object LaTeX フォーマットは実際には単なる [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/) フォーマットで、[Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) 固有のプリミティブを使用してページメトリクスを設定します。

最初に必要となるオプションは [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) で、TeX の出力が書き込まれる領域（スペース）を定義します。[ここ](/tex/{{lang.url-fragment}}net/aspose-tex-output/) に **Aspose.TeX for .NET** の出力ディレクトリの概念に関する詳細があります。この例では、指定されたディレクトリ（フォルダー）に出力を書き込むことができる [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) クラスを使用します。

2 番目のオプションは、[SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) クラスのインスタンスで、[object model](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) をターゲット形式に変換する方法を制御します。LaTeX を PNG に変換するので、[PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/) クラスのインスタンスを使用し、出力画像の解像度を指定できます。

次に、[TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/) クラスのインスタンスを作成します。ファイルシステムに保存された LaTeX ファイルを変換したい場合は、[この](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) コンストラクターバージョンを使用します。ファイルへの完全パスを指定する必要があります。指定しない場合、エンジンは現在のディレクトリ（[CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)）を検索し、見つからない可能性が高いです。なお、*.tex* 拡張子は省略可能で、エンジンが自動的に付加します。コンストラクタの第 2 引数は [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/) クラスのインスタンスです。LaTeX を PNG に変換するので、[ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/) クラスのインスタンスを使用し、すべてのサポートされている画像形式で共通です。最後の引数として、先ほど準備した変換オプションを渡します。

残りは [run](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) メソッドを呼び出すだけです。

実行が成功したかどうかに関わらず、最初に表示されるのは端末出力です。実行が成功した場合は次のようになります。

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

指定した出力ディレクトリ内にエンジンが生成した他の「成果物」があります。トランスクリプトファイルと、**こちらです！** メインの PNG 画像ファイル（複数）が含まれます。

## メインの PNG ファイル（複数）を書き出す別の方法

画像データをバイト配列の配列として取得し、2 次元目の各配列が別々のページの画像データを表す別の方法があります。

**代替変換例**

次の C# スニペットは、PNG 出力をファイルシステムに直接書き込む代わりにメモリストリームに書き込む別の方法を示します。このアプローチは、生成された PNG バイト列をメモリ上でさらに処理（ネットワーク送信、データベース保存、保存前の追加変換など）したい場合に便利です。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Alternative.cs" >}}

*"page-n.png"* ファイルは任意のパスに書き込まれます。[PDF 出力](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) とは異なり、出力ディレクトリに書き込まれた PNG ファイルのコピーが生成されます。

## 入力オプションについて

メインの入力ファイルが依存関係（例: パッケージ）を必要とし、基本的な LaTeX システムやサポートされているパッケージに含まれていない場合は、[RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) オプションを [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) と同様の方法で設定し、依存ファイルをそのディレクトリに配置する必要があります。依存ファイルはサブディレクトリに自由に整理できます。タイプセットプロセス中に外部画像ファイルなど独自のファイルを含める必要がある場合は、[InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) を設定し、ファイルが収集されている場所へのパスを指定してください。`run()` メソッドで相対パスを指定するか、メイン入力ファイルがルートにある場合はパスを省略することもできます。[ここ](/tex/{{lang.url-fragment}}net/aspose-tex-input/) に **Aspose.TeX for .NET** の入力ディレクトリ概念に関する詳細があります。

他の TeX ジョブ オプションについては、[ここ](/tex/{{lang.url-fragment}}net/other-options/) を参照してください。

**無料の LaTeX から PNG 変換 [Web アプリ](https://products.aspose.app/tex/conversion/latex-to-png) も、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースに構築されています。**

以下では、他のサポートされているラスタ画像形式への LaTeX 変換について、詳細に立ち入らずに説明します。唯一の違いは、変換オプション内の [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) プロパティの型です。

## LaTeX を JPG に変換する方法

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToJPEG.cs" >}}

**無料の LaTeX から JPG 変換 [Web アプリ](https://products.aspose.app/tex/conversion/latex-to-jpg) も、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースに構築されています。**

## LaTeX を TIFF に変換する方法

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToTIFF.cs" >}}

{{% alert color="primary" %}}
`Aspose.TeX.Drawing` パッケージは、まだマルチページ TIFF ファイルを保存できません。`TiffSaveOptions.Multipage` を `true` に設定しても、TIFF ファイルには最初のページしか含まれません。ページごとに個別の TIFF 画像を取得するには、`Multipage` を `false` に設定してください。[Linux、macOS、Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/#known-limitations)を参照してください。
{{% /alert %}}

**無料の LaTeX から TIFF 変換 [Web アプリ](https://products.aspose.app/tex/conversion/latex-to-tiff) も、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースに構築されています。**

## LaTeX を BMP に変換する方法

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToBMP.cs" >}}

**無料の LaTeX から BMP 変換 [Web アプリ](https://products.aspose.app/tex/conversion/latex-to-bmp) も、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースに構築されています。**

## LaTeX を SVG に変換する方法

そして、もう 1 つのサポート対象フォーマットは [**SVG**](https://en.wikipedia.org/wiki/SVG) です。**Scalable Vector Graphics (SVG)** は、インタラクティブ性とアニメーションをサポートする XML ベースのベクター画像形式です。

**SVG** 画像はベクターグラフィック形式で定義され、XML テキストファイルに保存されます。そのため、品質を損なうことなくサイズを拡大縮小でき、**SVG** ファイルは検索、インデックス付け、スクリプト化、圧縮が可能です。XML テキストファイルはテキストエディタやベクターグラフィックエディタで作成・編集でき、主要なウェブブラウザでレンダリングされます。

[**Aspose.SVG**](https://products.aspose.com/svg/) ライブラリは、**SVG** に関連するさまざまな機能（作成、読み込み、編集、変換）を提供します。

LaTeX から SVG への変換も、[ラスタ画像形式への変換](/tex/{{lang.url-fragment}}net/latex-to-image/) と同様に簡単です。ただし、[SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) を [SvgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/) クラスのインスタンスに設定し、デバイスを [SvgDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/) クラスのインスタンスに変更する必要があります。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToSVG-Simplest.cs" >}}

**無料の LaTeX から SVG 変換 [Web アプリ](https://products.aspose.app/tex/conversion/latex-to-svg) も、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースに構築されています。**
