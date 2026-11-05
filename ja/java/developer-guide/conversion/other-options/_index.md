---
translation: true
template: /templates/_template-java.md
title: TEXオプションの他の管理| Aspose.TeX for Java 開発者ガイド
linktitle: その他のオプション
weight: 17
url: /java/other-options/
description: Java用のAspose.TeX APIソリューションの変換機能により、エンジンが起動する初期インタラクションモードを設定できます。いくつかのコードの例を次に示します。
lastmod: "2025-06-09"
---

{{<section overview>}}


各例は LaTeX 用の `TeXOptions` を作成し、1 つのオプションを設定します。これらのオプションを `TeXJob` に渡し、適切な LaTeX 入力を用意して、実行前に出力作業ディレクトリを設定します。`com.aspose.tex.TeXOptions`、`TeXConfig`、選択した例で使用するクラス（`Interaction`、`com.aspose.tex.rendering.XpsSaveOptions` または `PdfSaveOptions`、日付の例では `java.util.Calendar`/`GregorianCalendar`）をインポートします。呼び出し元のメソッドは例外を処理するか宣言します。ラスタライズとフォントサブセットの例は `PdfSaveOptions` を使用するため、互換性のある `PdfDevice` でレンダリングします。[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用してください。

## インタラクションモードを設定する方法

[ここ](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)、**JavaのAspose.TeX**を述べたように、エンジンが起動する初期インタラクションモードを設定できます。これが私たちのやり方です：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-InteractionMode.java" >}}

## 求人名を設定する方法

メイン入力ファイルをファイル名として渡すと、他の拡張機能ではありますが、同じ名前の出力ファイルが取得されます。 TEXエンジンは、入力ファイルの名前を *ジョブ名 *を呼び出し、出力ファイルに使用します。メイン入力ファイルを[ストリーム](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream)として渡すと、Texエンジンはデフォルトのジョブ名、つまり *texput*を使用します。
どちらの場合も、適切な変換オプションを割り当てることにより、ジョブ名をオーバーライドできます。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-JobName.java" >}}

## 「時間を止める」方法

LaTexには、Preambleのいくつかの定義からタイトルを自動的に生成する機能があります。このタイトルには通常、現在の日付が含まれています。ある程度の希望の価値で日付を凍結することをお勧めします。これがどのように行われるかは次のとおりです。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-DateTime.java" >}}

## 欠落しているパッケージを無視する方法

LaTeX ファイルが Aspose.TeX for Java ライブラリで利用できないパッケージを参照する場合があります。通常、エンジンはそのパッケージの読み込み時にエラーで停止します。`ignoreMissingPackages(true)` を使用すると、利用できないパッケージをスキップできます。ただし、それらのパッケージが定義するコマンドは提供されないため、入力はそのコマンドに依存してはいけません。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-IgnoreMissingPackages.java" >}}

## 結晶の構築を避ける方法

通常、TEXエンジンは、フォントが必要なデータを提供する場合、特定のペアの文字の連結を構築します。次のコードを使用して、エンジンにligatureビルをスキップするように指示できます。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-NoLigatures.java" >}}

## 仕事を繰り返す方法

ラベルと参照に関して[上記](/tex/{{lang.url-fragment}}net/latex-io/#latex-input)に述べたように、同じジョブを2回実行したい場合があります。これがどのように行われるかは次のとおりです。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-Repeat.java" >}}

## 数式を回す方法画像をラスターする方法

時には、フォントに入力するのではなく、ラスター画像として数学式が必要になる場合があります。次のオプションは、この目的のために役立つことができます。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeFormulas.java" >}}

## グラフィックを回して画像をラスターする方法

ObjectTexエンジンを使用すると、Raster形式(PNGおよびJPG)、PS(EPS)およびXPS(OXPS)形式のグラフィックファイルを含めることができます。最後の2つの形式には、通常、ベクトル要素とテキストが含まれています。それらをラスター化して固体画像として含めるために、次のオプションを使用できます。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeIncludedGraphics.java" >}}

## サブセットフォントの方法

フォントサブセットは、埋め込みフォントを文書内で使用するグリフに限定します。出力サイズへの影響は、フォントと出力デバイスによる埋め込み方法によって異なります。以下のように、`subsetFonts(true)` を有効にする前に保存オプションを割り当てます。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-SubsetFonts.java" >}}