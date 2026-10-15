---
translation: true
template: /templates/_template-java.md
title: その他のTEX変換出力形式| Java
linktitle: その他のTEX形式
weight: 18
url: /java/other-tex-formats/
description: Java用のAspose.TeX APIソリューションの変換機能により、LaTexファイルと独自のカスタムTEXファイルを変換できます。いくつかのコードの例を次に示します。
lastmod: "2026-04-21"
---

{{<section overview>}}

現在、ラテックス以外の形式で記述されたTEXファイルを変換したいと思う可能性は非常に低いです。しかし、これは、何らかの理由でTex言語や内部を勉強している場合に可能です。とにかく、**JavaのAspose.TeX**では、プレーンTex形式で記述されたファイルを変換できます。また、これらの形式で設計されたカスタム形式とタイプセットドキュメントを作成することもできます。

カスタム形式の作成から始めます。

## カスタム形式の作成

フォーマットファイルは、TEXエンジンの内部状態のバイナリダンプであることを覚えておいてください。

`inputDirectory` に `customtex.tex` とその依存ファイルを含むフォルダーを、`outputDirectory` に既存の出力フォルダーを指定します。形式のソースは `\dump` で終わる必要があり、この例では出力フォルダーに `customtex.fmt` を作成します。例で使用する Aspose.TeX クラスと、組版に必要な `com.aspose.tex.rendering.XpsDevice`、`java.io.ByteArrayInputStream`、`java.nio.charset.StandardCharsets` をインポートします。呼び出し元のメソッドは例外を処理するか宣言する必要があります。評価版の制限を避けるため、[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用してください。

{{< gist "aspose-com-gists" "d21a098d3848236e0c258661f5bbc0ae" "Example-CreateCustomTeXFormat.java" >}}

ご覧のとおり、コードはTEXファイルを変換するためのコードに似ています。しかし、いくつかの違いがあります。

まず、[texconfig.objectinitex()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectIniTeX--) ジョブ構成を使用します。これは、エンジンの状態「Virgin」を離れる特別な構成です。つまり、内部パラメーターにはデフォルト値があり、コントロールシーケンスのセットはプリミティブのセットと一致します。私たちの例では、プリミティブのセットは、[ここ](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)に言及された意味で拡張されます。

次に、通常どおり、入力および出力作業ディレクトリを設定します。入力作業ディレクトリには、メイン形式のソースファイルとそのすべての依存関係を含める必要があります。

そして、2番目の重要な違いは、私たちが仕事をする方法です。今回は、static [createformat()](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#createFormat-java.lang.String-com.aspose.tex.TeXOptions-) メソッドを使用します。これは、オプションとともにメインソースファイルの名前を取得し、形式名と同じでなければなりません。

## カスタム形式でTEXファイルを植林します

独自のTex形式ができたので、この形式で記述されたTexファイルを整形したいと考えています。これがコードです：

`formatDirectory` に作成済みの `customtex.fmt` を含むフォルダーを、`outputDirectory` に既存の出力フォルダーを指定します。この例は自己完結したテキストストリームを `typeset-with-custom-format.xps` に組版するため、入力作業ディレクトリは不要です。主入力が画像などの依存ファイルを参照する場合は、入力作業ディレクトリを設定します。

{{< gist "aspose-com-gists" "d21a098d3848236e0c258661f5bbc0ae" "Example-TypesetWithCustomTeXFormat.java" >}}

明らかに、形式を何らかの形で指定する必要があります。まず、[formatprovider](https://reference.aspose.com/tex/java/com.aspose.tex/formatprovider/) クラスのインスタンスを作成する必要があります。次に、オプションコンストラクターで[TeXConfig.objectTeX(FormatProvider)](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectTeX-com.aspose.tex.FormatProvider-)構成を使用します。これは、フォーマットプロバイダーを引数として受け取り、エンジンの「処女」状態の上に形式をロードします。

両方の例は対話なしで実行され、端末出力をメモリに保存します。組版の例では、ジョブ終了後に入力ストリームを閉じ、XPS デバイスを解放し、作業ディレクトリと形式プロバイダーを閉じます。これらの機能は、この[ガイド](/tex/{{lang.url-fragment}}java/conversion/)で前述しています。

## Plain Tex形式でTexファイルを植林します

形式プロバイダーを指定せずに `TeXConfig.objectTeX()` を使用すると、エンジンはデフォルト形式をロードします。これは[オブジェクトTex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/)である4番目の意味でです。したがって、Plain Tex形式でTexファイルが書かれている場合、この方法では、サポートされているターゲット形式に変換できます。