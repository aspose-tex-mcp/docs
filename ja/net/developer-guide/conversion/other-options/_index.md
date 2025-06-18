---
translation: true
template: /templates/_template-net.md
title: TEXオプションの他の管理| 。ネット
linktitle: その他のオプション
weight: 17
url: /net/other-options/
description: .NET用のASOPSE.TEX APIソリューションの変換機能により、エンジンが起動する初期インタラクションモードを設定できます。いくつかのコードの例を次に示します。
lastmod: "2025-06-09"
---

{{<section overview>}}

## インタラクションモードを設定する方法

[ここ](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)、**.netのAspose.TeX**を述べたように、エンジンが起動する最初のインタラクションモードを設定できます。これが私たちのやり方です：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InteractionMode.cs" >}}

## 求人名を設定する方法

メイン入力ファイルをファイル名として渡すと、他の拡張機能ではありますが、同じ名前の出力ファイルが取得されます。 TEXエンジンは、入力ファイルの名前を *ジョブ名 *を呼び出し、出力ファイルに使用します。メイン入力ファイルを[ストリーム](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream)として渡すと、Texエンジンはデフォルトのジョブ名、つまり *texput*を使用します。
どちらの場合も、適切な変換オプションを割り当てることにより、ジョブ名をオーバーライドできます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-JobName.cs" >}}

## 「時間を止める」方法

LaTexには、Preambleのいくつかの定義からタイトルを自動的に生成する機能があります。このタイトルには通常、現在の日付が含まれています。ある程度の希望の価値で日付を凍結することをお勧めします。これがどのように行われるかは次のとおりです。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-DateTime.cs" >}}

## 欠落しているパッケージを無視する方法

.NETライブラリのAspose.TeXによってサポートされていないいくつかのパッケージを参照するラテックスファイルを変換する場合があります。この場合、そのようなパッケージをロードしようとすると、Texエンジンはエラーで停止します。これを避けるために、次のオプションを使用できます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.cs" >}}

## 結晶の構築を避ける方法

通常、TEXエンジンは、フォントが必要なデータを提供する場合、特定のペアの文字の連結を構築します。次のコードを使用して、エンジンにligatureビルをスキップするように指示できます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-NoLigatures.cs" >}}

## 仕事を繰り返す方法

ラベルと参照に関して[上記](/tex/{{lang.url-fragment}}net/latex-io/#latex-input)を述べたように、同じジョブを2回実行したい場合があります。これがどのように行われるかは次のとおりです。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-Repeat.cs" >}}

## 数式を回す方法画像をラスターする方法

時には、フォントに入力するのではなく、ラスター画像として数学式が必要になる場合があります。次のオプションは、この目的のために役立つことができます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.cs" >}}

## グラフィックを回して画像をラスターする方法

ObjectTexエンジンを使用すると、Raster形式(PNGおよびJPG)、PS(EPS)およびXPS(OXPS)形式のグラフィックファイルを含めることができます。最後の2つの形式には、通常、ベクトル要素とテキストが含まれています。それらをラスター化して固体画像として含めるために、次のオプションを使用できます。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.cs" >}}

## サブセットフォントの方法

出力ファイルのサイズを縮小する場合は、フォントサブセットに頼ることができます。つまり、出力ドキュメントのフォントには、ドキュメントで使用されているグリフに関するデータのみが含まれます。これを解決する方法は次のとおりです。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-SubsetFonts.cs" >}}