---
translation: true
template: /templates/_template-java.md
title: ラテックスからXPS | Java用のAspose.TeX
linktitle: ラテックスからXPS
weight: 12
url: /java/latex-to-xps/
description: Java用のAspose.TeX APIソリューションの変換機能を使用すると、LaTexファイルをXPS形式に変換できます。コードの例を学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}


もう一つのターゲットフォーマットは[**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)です。**XPS**ファイルは、ページ区切りのドキュメントコンテンツと、特定のビューア（Windows XPS Viewerなど）での適切な表示や印刷に必要なメタデータを含むZIPパッケージです。パッケージ内のすべてのデータは、ディレクトリ内のファイルとして整理されます。ディレクトリの中には、画像、フォント、ICCプロファイルなどのリソースを含むものもあれば、様々な特定スキーマに従ったXMLファイルもあります。後者には、ドキュメントデータ自体を含むファイルも含まれます。ドキュメントデータはファイルの集合体であり、各ファイルにはドキュメントの各ページのデータが含まれています。これらのファイルは、単一のページ要素と、子要素（*Canvas*、*Path*、*Glyphs*）のツリーで構成されます。*Canvas*は、他の*Canvas*、*Path*、*Glyphs*を含むことができるグループ化要素です。その目的は、すべての子要素の外観をグループとして制御することです。*Path*要素は、ベクターグラフィックのパスを定義するために使用されます。 *グリフ*要素はテキストコンテンツを定義するために使用されます。これら3つの要素はすべて、外観のさまざまな側面を定義するプロパティを持っています。

[**Aspose.Page**](https://products.aspose.com/page/)ライブラリがあり、XPSドキュメントを操作するためのAPIを提供し、PDFおよびラスター画像形式に変換します。

## ラテックスをXPSに変換する方法
XPSへの変換は、[saveoptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getSaveOptions--)に加えて[xpsdevice](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/XpsDevice)クラスのインスタンスを使用する必要があることを除いて、[ラスター画像形式への変換](/tex/{{lang.url-fragment}}java/latex-to-image/)と同じくらい簡単です。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.java" >}}

### メイン出力XPSファイルを書き込む代替方法

[XPSDevice](https://reference.aspose.com/tex/java/com.Aspose.TeX.rendering/XpsDevice#XpsDevice-java.io.OutputStream-)クラスの別のコンストラクターがあります。これにより、結果のXPSファイルを別の方法で取得できます。

{<<gist "Aspose-com-gists" "67385C777283964D328086603F691AC9" "ASPOSE.TEX.CONVELS-CONVERSION-LATEXTOXPS-ALTERNATIVE.JAVA">}}}}

効果は[ここ]を取得するのと同じです(7)。

**[.NETのAsops.Tex](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のLaTex-to-XPS変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-xps)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/java/)はJavaバージョンページです。**