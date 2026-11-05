---
translation: true
template: /templates/_template-java.md
title: Aspose.TeXの出力インターフェイス| Aspose.TeX for Java 開発者ガイド
linktitle: Aspose.TeXの出力インターフェイス
weight: 16
url: /java/aspose-tex-output/
description: Aspose.TeX APIソリューションの変換機能TEXを使用したJavaのAPIソリューションは、ここではコードの例で説明されています。
lastmod: "2026-04-21"
---

{{<section overview>}}

I/O実装の正式な定義については、Java **[API Reference](https://reference.aspose.com/tex/java/com.aspose.tex/)の** Aspose.TeXを参照してください。

ファイルシステム、ZIP、端末の例は `hello-world.tex` を XPS に組版します。`inputDirectory` に TeX ファイルを含むフォルダーを、`outputDirectory` に既存の出力フォルダーを指定します。ZIP 出力では、`outputZip` に既存のフォルダー内の `java.nio.file.Path` を指定します。 選択した例で使用する Aspose.TeX クラス、`com.aspose.tex.rendering.XpsDevice`、必要な `java.io` と `java.nio.file` のクラスをインポートします。呼び出し元のメソッドは例外を処理するか宣言する必要があります。評価版の制限を避けるため、[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用してください。

## 出力ディレクトリの概念

Tex言語のI/O Primitivesはファイル名のみを扱うことができるため、Aspose.TeXは、ディレクトリを名前とデータのバルクのマッピングとして定義します。データの大部分は、ファイル、ストリーム、配列などであるはずです。APIにより、入力および出力作業ディレクトリを個別に指定できます。一般的な[ioutputworkingdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/)の出力のインターフェイスを提供します。これは、ユーザーが独自の目的で実装できます。また、独自の実装も提供します。これについては、以下で説明します。インターフェイスは[iinputworkingdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/)を拡張します。エンジンが最初にファイルを作成して書き込み、次に読み戻すことができるためです。インターフェイス独自のメソッド[getOuputfile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-)は、[getFile()](https://reference.aspose.com/tex/java/com.Aspose.TeX/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-)によって返された読み取りに読み取るストリームとは対照的に、ストリームを返して書き込みます。

### ディスクファイルシステムへのファイル出力の書き込み

[上記](/tex/{{lang.url-fragment}}/java/conversion/)で述べたように、[OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) の最も一般的な値は、[OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/) クラスのインスタンスである可能性があります。

これが私たちがそれを設定する方法です：

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

このユースケースは非常に簡単なので、長い間それについては言及しません。

### ZIPアーカイブへのファイル出力の書き込み

また、ファイル(またはストリーム)を作成し、TexエンジンにZIPアーカイブとして使用して出力ファイルを保存することもできます。ここにあります：

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

まず、zipファイルの出力ストリームを作成します。次に、変換オプションを作成した後、[outputzipdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/)クラスのインスタンスになるように[outputworkingdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--)オプションを設定します。 この例は `hello-world.xps` と `hello-world.log` をアーカイブに保存します。ジョブ終了後、基になるストリームを閉じる前に出力ディレクトリの `finish()` を呼び出します。例ではジョブが終了するまでストリームと作業ディレクトリを開いたままにし、その後に閉じます。

## 出力端子の概念

出力には別の重要な部分があります---端子出力。これに関しては、**Aspose.TeX for java**一般[ioutputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/)インターフェイスを2つのメソッドがあると定義します。そのうちの1人は[BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html)インスタンスを返します。別のものは、[outputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html)インスタンスを基礎となるストリームとして返します。インターフェイスの実装を以下で説明します。

### コンソールへの端子出力の書き込み

これを行うには、[OutputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/)クラスのインスタンスになるには、[Terminalout](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--)オプションを設定する必要があります。

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` はこのオプションのデフォルト値です。この例では明示的に選択し、変換中の端末出力をコンソールに書き込みます。4 つの例はすべて対話なしで実行され、ファイルシステムと ZIP の例は端末出力をメモリに保存します。

### ファイルへの端子出力の書き込み

入力端子とは異なり、**Java** for Java **は[ioutputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/)の実装を提供します。これにより、出力ディレクトリのファイルに端子出力を書き込むことができます。

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

`OutputFileTerminal` を作成する前に出力作業ディレクトリを設定します。端末出力は、そのディレクトリの [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm（この例では `hello-world.trm`）に書き込まれます。この端末ファイルは TeX のログ `hello-world.log` とは別です。端末出力を別の場所に書き込むには、別の [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) 実装をコンストラクターに渡します。