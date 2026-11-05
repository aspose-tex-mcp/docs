---
translation: true
template: /templates/_template-net.md
title: LaTeX から XPS へ | Aspose.TeX for .NET 開発者ガイド
linktitle: LaTeX から XPS へ
weight: 12
url: /net/latex-to-xps/
aliases: /net/other-target-formats/
description: Aspose.TeX API ソリューション for .NET の変換機能を使用すると、LaTeX ファイルを XPS 形式に変換できます。以下にコード例を示します。
keywords: LaTeXからXPS、Aspose Tex、.NET変換、XPS形式、TexからXPS、ドキュメント変換、Aspose Page、XPSデバイス、XPS保存オプション、C#の例
lastmod: "2026-11-02"
---

{{<section overview>}}

別のターゲット形式として [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) があります。**XPS** ファイルは、実際には ZIP パッケージで、ドキュメントのページ化されたコンテンツと、特定のビューア（例：Windows XPS Viewer）や印刷のために必要なメタデータが含まれています。パッケージ内のすべてのデータはファイルとして表現されます。そのうちいくつかはバイナリで、画像、フォント、ICC プロファイルなどのリソースを含みます。他はさまざまな特定スキーマの XML ファイルです。後者にはドキュメントデータ自体が含まれます。ドキュメントデータは一連のファイルで構成され、各ファイルはドキュメントの個々のページのデータを保持します。これらのファイルは単一のページ要素と子要素ツリー（*Canvas*、*Path*、*Glyphs*）で構成されます。*Canvas* は他の *Canvas*、*Path*、*Glyphs* を含むことができるグルーピング要素で、子要素全体の外観をまとめて制御します。*Path* 要素はベクターグラフィックのパスを定義し、*Glyphs* 要素はテキスト コンテンツを定義します。これら 3 つの要素には、外観のさまざまな側面を定義するプロパティがあります。

[**Aspose.Page**](https://products.aspose.com/page/) ライブラリは XPS ドキュメントを操作する API を提供し、さらに PDF やラスタ画像形式への変換もサポートしています。

## LaTeX を XPS に変換する方法

LaTeX から XPS への変換は、[ラスタ画像形式への変換](/tex/{{lang.url-fragment}}net/latex-to-image/) と同様に簡単です。ただし、[SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) はデフォルトまたは明示的に [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) クラスのインスタンスに設定する必要があり、デバイスは [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/) クラスのインスタンスに変更する必要があります。

**最も簡単な変換例**

以下の例は、数ステップで LaTeX ファイルを XPS に変換する方法を示しています。

1. `TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX)` を使用して、ObjectLaTeX 形式の `TeXOptions` を作成します。
2. 出力作業ディレクトリ (`OutputFileSystemDirectory` など) を指定します。
3. `SaveOptions` に `XpsSaveOptions` のインスタンスを設定します。
4. ソース `.tex` ファイルに対して、`XpsDevice` を指定した `TeXJob` を実行します。XPS ファイルは出力作業ディレクトリに書き込まれます。

このコードは、LaTeX から XPS ファイルを生成する最も直接的な方法を示しています。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### メイン出力 XPS ファイルを書き込む別の方法

[XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/) クラスには、結果の XPS ファイルを別の方法で取得できるコンストラクタがあります。

**代替変換例**

このスニペットは `Stream` を受け取る `XpsDevice` コンストラクタの使用例です。手順は次のとおりです。

1. XPS ドキュメントの書き込み先となるストリームを開きます (ここではファイル ストリームですが、`MemoryStream` でも同様に動作します)。
2. 前の例と同様に、`TeXOptions` を作成し、出力作業ディレクトリを指定して、`SaveOptions` に `XpsSaveOptions` のインスタンスを設定します。
3. ストリームを渡して作成した `XpsDevice` を指定して `TeXJob` を実行します。XPS ドキュメントはストリームに書き込まれます。トランスクリプトなどのその他の出力ファイルは、引き続き出力作業ディレクトリに書き込まれます。

このアプローチは、XPS ドキュメントを任意のストリームに書き込む必要がある場合 (メモリ上に保持する場合やネットワーク経由で送信する場合など) に便利です。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

この効果は、[こちら](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) で確認できます。

**無料の LaTeX から XPS への変換 [Web アプリ](https://products.aspose.app/tex/conversion/latex-to-xps) もご利用いただけます（[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) に基づいて構築）**
