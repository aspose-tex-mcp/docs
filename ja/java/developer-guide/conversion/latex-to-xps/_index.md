---
translation: true
template: /templates/_template-java.md
title: ラテックスからXPS | Aspose.TeX for Java 開発者ガイド
linktitle: ラテックスからXPS
weight: 12
url: /java/latex-to-xps/
description: Java用のAspose.TeX APIソリューションの変換機能を使用すると、LaTexファイルをXPS形式に変換できます。コードの例を学びます。
lastmod: "2026-04-21"
---

{{<section overview>}}


もう一つのターゲットフォーマットは[**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)です。**XPS**ファイルは、ページ区切りのドキュメントコンテンツと、特定のビューア（Windows XPS Viewerなど）での適切な表示や印刷に必要なメタデータを含むZIPパッケージです。パッケージ内のすべてのデータは、ディレクトリ内のファイルとして整理されます。ディレクトリの中には、画像、フォント、ICCプロファイルなどのリソースを含むものもあれば、様々な特定スキーマに従ったXMLファイルもあります。後者には、ドキュメントデータ自体を含むファイルも含まれます。ドキュメントデータはファイルの集合体であり、各ファイルにはドキュメントの各ページのデータが含まれています。これらのファイルは、単一のページ要素と、子要素（*Canvas*、*Path*、*Glyphs*）のツリーで構成されます。*Canvas*は、他の*Canvas*、*Path*、*Glyphs*を含むことができるグループ化要素です。その目的は、すべての子要素の外観をグループとして制御することです。*Path*要素は、ベクターグラフィックのパスを定義するために使用されます。 *グリフ*要素はテキストコンテンツを定義するために使用されます。これら3つの要素はすべて、外観のさまざまな側面を定義するプロパティを持っています。

[**Aspose.Page**](https://products.aspose.com/page/)ライブラリがあり、XPSドキュメントを操作するためのAPIを提供し、PDFおよびラスター画像形式に変換します。

## ラテックスをXPSに変換する方法
XPSへの変換は、[saveoptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--)に加えて[xpsdevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) クラスのインスタンスを使用する必要があることを除いて、[ラスター画像形式への変換](/tex/{{lang.url-fragment}}java/latex-to-image/)と同じくらい簡単です。

`inputFile` に LaTeX ファイル（例：`hello-world.ltx`）のフルパスを設定し、`outputDirectory` に既存の出力フォルダーを設定してください。スニペットで使用する `com.aspose.tex` と `com.aspose.tex.rendering` のクラスをインポートします。呼び出し元のメソッドでは、例外を処理するか、スローする例外として宣言する必要があります。評価版の制限を避けるには、[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用してください。この例では非対話モードで処理し、出力リソースを閉じます。 外部ファイルに依存しない入力ファイル `hello-world.ltx` の既定の出力は `hello-world.xps` です。

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### メイン出力XPSファイルを書き込む代替方法

[XPSDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-)クラスの別のコンストラクターがあります。これにより、結果のXPSファイルを別の方法で取得できます。

上記と同じ `inputFile` と `outputDirectory` の値を使用してください。`xpsFile` に `java.nio.file.Path` を設定します（例：`Paths.get(outputDirectory, "any-name.xps")`）。Aspose.TeX のクラスに加えて、`java.io.OutputStream`、`java.nio.file.Files`、`java.nio.file.Path`、`java.nio.file.Paths` をインポートしてください。 ストリームで XPS ファイルの出力先を指定します。補助ファイルは引き続き `outputDirectory` に書き込まれます。

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

効果は[ここ](/tex/{{lang.url-fragment}}java/latex-to-pdf/#メイン出力pdfファイルを書き込む代替方法)と同じです。

**[.NETのAsops.Tex](https://products.aspose.com/tex/net/)APIに基づいて構築された無料のLaTex-to-XPS変換[Webアプリ](https://products.aspose.app/tex/conversion/latex-to-xps)をチェックアウトすることもできます。 [ここ](https://products.aspose.com/tex/java/)はJavaバージョンページです。**