---
translation: true
template: /templates/_template-net.md
title: ラテックスからXPS | .NET
linktitle: ラテックスからXPS
weight: 12
url: /net/latex-to-xps/
description: .NET用のASOPSE.TEX APIソリューションの変換機能により、LaTexファイルをXPS形式に変換できます。いくつかのコードの例を次に示します。
lastmod: "2025-06-09"
---

{{<section overview>}}


別のターゲット形式は[**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)です。 **XPS**ファイルは、特定の視聴者(Windows XPS Viewerなど)および印刷による適切な表示に必要なメタデータとともに、ドキュメントの塗装されたコンテンツを含む物理的にZIPパッケージです。パッケージ内のすべてのデータはファイルで表されます。それらのいくつかはバイナリであり、画像、フォント、ICCプロファイルなどのリソースが含まれています。その他は、さまざまな特定のスキーマのXMLファイルです。後者には、ドキュメントデータ自体を含むファイルが含まれます。ドキュメントデータはファイルのセットで構成されています - 各ファイルには、ドキュメントの個々のページのデータが含まれています。このようなファイルは、単一のページ要素と子要素のツリー -  *キャンバス *、 *パス *、および *glyphs*で構成されています。 *Canvas*は、他の*キャンバス*、*パス*、および*Glyphs*を含むグループ要素です。グループとしてのすべての子供の要素の外観を制御するのに役立ちます。 *パス*要素は、ベクトルグラフィックパスを定義するために使用されます。および *glyphs*要素は、テキストコンテンツを定義するために使用されます。 3つの要素はすべて、外観のさまざまな側面を定義するためのプロパティがあります。

[**Aspose.Page**](https://products.aspose.com/page/)ライブラリがあり、XPSドキュメントを操作するためのAPIを提供し、PDFおよびラスター画像形式に変換します。

## ラテックスをXPSに変換する方法

ラテックスからXPSへの変換は、[saveoptions](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/saveoptions/)を[xpssaveoptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/)クラスインスタンス(デフォルトまたは明示的に)に設定する必要があり、[xpsdevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)クラスのインスタンスにデバイスを変更する必要があります。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.cs" >}}

### メイン出力XPSファイルを書き込む代替方法

[XPSDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/)クラスの別のコンストラクターがあります。これにより、結果のXPSファイルを別の方法で取得できます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.cs" >}}


効果は[ここ]を取得するのと同じです(8)。

**[.NET APIのAsops.Tex](https://products.aspose.com/tex/net/)に基づいて構築された無料のLaTex-to-XPS変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-xps)をチェックアウトすることもできます。**