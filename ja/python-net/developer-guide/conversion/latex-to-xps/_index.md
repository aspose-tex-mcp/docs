---
translation: true
template: /templates/_template-python-net.md
title: ラテックスからXPS | .NET経由でPython用のAspose.TeX
linktitle: ラテックスからXPS
weight: 12
url: /python-net/latex-to-xps/
description: Python用のAspose.TeX APIソリューションは、LaTexファイルをXPS形式に変換する変換機能を提供します。ここにいくつかのコード例があります。
lastmod: "2025-06-09"
---

{{<section overview>}}

別のターゲット形式は[**xps**](https://docs.aspose.com/page/net/what-is-xps-file/)です。 [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)ファイルは、本質的に、ドキュメントの塗装コンテンツを含むzipパッケージと、特定の視聴者(Windows XPSビューアーなど)および印刷による適切な表示に必要なメタデータです。パッケージはさまざまなファイルで構成されており、その一部はバイナリであり、画像、フォント、ICCプロファイルなどのリソースが含まれています。その他は、ドキュメントデータ自体を含むファイルを含む特定のスキーマ内のXMLファイルです。ドキュメントデータは複数のファイルに分割され、各ファイルはドキュメントの個々のページを表します。これらのファイルは、単一のページ要素と *キャンバス *、 *パス *、および *glyphs *を含む子要素のツリーで構成されています。 *Canvas *要素は、他の *キャンバス *、 *パス *、および *Glyphs *を含むグループ要素であり、グループとしてのすべての子要素の外観を制御します。 *パス*要素はベクトルグラフィックパスを定義するために使用され、* glyphs*要素はテキストコンテンツを定義するために使用されます。 3つの要素はすべて、外観のさまざまな側面を定義するプロパティがあります。

[**Aspose.Page**](https://products.aspose.com/page/)ライブラリが存在します。これは、XPSドキュメントを操作するためのAPIを提供し、これらのドキュメントをPDFおよびラスター画像形式に変換することもできます。

## ラテックスをXPSに変換します

ラテックスをXPSに変換するプロセスは、[ラスター画像形式への変換](/tex/{{lang.url-fragment}}python-net/latex-to-image/)と同様に、同様に簡単です。ただし、[save_options](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/save_options/)を[xpssaveoptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/)クラス(デフォルトまたは明示的に)のインスタンスに設定し、[xpsdevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/)クラスのインスタンスにデバイスを変更する必要があります。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### メイン出力XPSファイルを書き込む代替方法

* XPSDevice *クラスで使用できる代替コンストラクターがあり、結果のXPSファイルを別の方法で取得できます。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

効果は[ここ]を取得するのと同じです(8)。

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) を使用して開発された無料の [LaTeX から XPS への変換用 Web アプリ](https://products.aspose.app/tex/conversion/latex-to-xps) を調べることもできます。**