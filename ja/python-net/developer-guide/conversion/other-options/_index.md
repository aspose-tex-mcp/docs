---
translation: true
template: /templates/_template-python-net.md
title: TEXオプションの他の管理| .NET経由でPython用のAspose.TeX
linktitle: その他のオプション
weight: 17
url: /python-net/other-options/
description: Python用のAspose.TeX APIソリューションには、エンジンが起動する初期インタラクションモードを設定できる変換機能が含まれています。
lastmod: "2025-06-09"
---

{{<section overview>}}

以下の例は XPS ファイルを生成します。まず[ライセンス](/tex/{{lang.url-fragment}}python-net/licensing/)を適用し、`ASPOSE_TEX_OUTPUT_DIR` に出力フォルダーを指定します（既定値：`output`）。すべての結果を保持するには、例ごとに別の出力フォルダーを使用してください。

## インタラクションモードの設定

前述のように、[Tex相互作用パラプラフ](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)、**Aspose.TeX for Python**は、エンジンが起動する初期インタラクションモードを設定する機能を提供します。これがどのようにできるかの例です。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-InteractionMode.py" >}}

## ジョブ名を設定します

メインの入力ファイルがファイル名として提供されると、結果の出力ファイルは同じ名前を持ちますが、拡張機能が異なります。 TEXエンジンは、入力ファイルの名前を *ジョブ名 *と呼び、出力ファイルに使用します。例外は、明示的に指定されたファイル名を持つ補助ファイルです。ただし、メイン入力ファイルが[ストリーム](/tex/{{lang.url-fragment}}python-net/other-ways-of-main-input/#supplying-the-main-input-file-as-a-stream)として渡されると、TEXエンジンはデフォルトのジョブ名、つまり *texput*を使用します。両方のシナリオで、適切な変換オプションを割り当てることでジョブ名をオーバーライドすることが可能です。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-JobName.py" >}}

## 「停止時間」

Preambleで特定の定義からタイトルを自動的に生成するために、LaTexは通常、現在の日付を含む機能を提供します。ただし、日付を特定の値に修正するインスタンスがある場合があります。これを実現する方法は次のとおりです。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-DateTime.py" >}}

## 欠落しているパッケージを無視します

python **ライブラリの** Aspose.TeXによってサポートされていないパッケージへの参照を含むラテックスファイルがある場合、Texエンジンはこれらのパッケージをロードしようとするときにエラーに遭遇し、停止します。これを防ぐために、次のオプションを利用できます。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.py" >}}

## 結晶の構築を避ける方法

デフォルトでは、TEXエンジンには、フォントに必要なデータが含まれている場合、特定の文字ペアの結晶を構築します。ただし、次のコードを使用して、エンジンに結晶構造をバイパスするように指示できます。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-NoLigatures.py" >}}

## 仕事を繰り返します

[LaTex入力ファイルの段落](/tex/{{lang.url-fragment}}net/latex-io/#latex-input-file)、ラベル、参考文献で述べたように、同じジョブを2回実行する必要がある状況があります。これを達成する方法は次のとおりです。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-Repeat.py" >}}

## 数式をラスター画像に変える

数式をフォントでレンダリングする代わりに、数式をラスター画像に変換する必要がある場合は、次のオプションをこの目的に使用できます。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.py" >}}

## グラフィックをラスター画像に変える

ObjectTexエンジンは、PNGやJPG、PS(EPS)やXPS(OXPS)形式などのラスター形式のグラフィックファイルを含める機能を提供します。後者の2つの形式には、通常、ベクトル要素とテキストが含まれています。ラスター化して固体画像として含める場合は、次のオプションを利用できます。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.py" >}}

グラフィックスの例は、`ASPOSE_TEX_INPUT_DIR`（既定値：`input`）内の `Typesetting/triangle.eps` を読み込みます。リソースを準備する際は、このサブフォルダー構造を維持してください。

## サブセットフォント

出力ファイルのサイズを縮小することを望む場合、フォントサブセットを使用できます。これには、結果のドキュメントのフォントには、ドキュメントに存在しないグリフのデータが含まれないことが含まれます。これを実現するためのソリューションは次のとおりです。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-SubsetFonts.py" >}}