---
translation: true
template: /templates/_template-java.md
title: Aspose.TeXの出力インターフェイス| Java
linktitle: Aspose.TeXの出力インターフェイス
weight: 16
url: /java/aspose-tex-output/
description: Aspose.TeX APIソリューションの変換機能TEXを使用したJavaのAPIソリューションは、ここではコードの例で説明されています。
lastmod: "2025-06-09"
---

{{<section overview>}}

I/O実装の正式な定義については、Java **[API Reference](https://reference.aspose.com/tex/java/com.Aspose.TeX/package-frame)の** Aspose.TeXを参照してください。

## 出力ディレクトリの概念

Tex言語のI/O Primitivesはファイル名のみを扱うことができるため、Aspose.TeXは、ディレクトリを名前とデータのバルクのマッピングとして定義します。データの大部分は、ファイル、ストリーム、配列などであるはずです。APIにより、入力および出力作業ディレクトリを個別に指定できます。一般的な[ioutputworkingdirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/IOutputWorkingDirectory)の出力のインターフェイスを提供します。これは、ユーザーが独自の目的で実装できます。また、独自の実装も提供します。これについては、以下で説明します。インターフェイスは[iinputworkingdirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/IInputWorkingDirectory)を拡張します。エンジンが最初にファイルを作成して書き込み、次に読み戻すことができるためです。インターフェイス独自のメソッド[getOuputfile()](https://reference.aspose.com/tex/java/com.Aspose.TeX/IOutputWorkingDirectory#getOutputFile-java.lang.String-java.lang.String:A-)は、[getFile()](https://reference.aspose.com/tex/java/com.Aspose.TeX/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-)によって返された読み取りに読み取るストリームとは対照的に、ストリームを返して書き込みます。

### ディスクファイルシステムへのファイル出力の書き込み

[上記](/tex/{{lang.url-fragment}}/java/conversion/)で述べたように、[OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) の最も一般的な値は、[OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory) クラスのインスタンスである可能性があります。

これが私たちがそれを設定する方法です：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

このユースケースは非常に簡単なので、長い間それについては言及しません。

### ZIPアーカイブへのファイル出力の書き込み

また、ファイル(またはストリーム)を作成し、TexエンジンにZIPアーカイブとして使用して出力ファイルを保存することもできます。ここにあります：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

まず、zipファイルの出力ストリームを作成します。次に、変換オプションを作成した後、[outputzipdirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/OutputZipDirectory)クラスのインスタンスになるように[outputworkingdirectory](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getOutputWorkingDirectory--)オプションを設定します。

## 出力端子の概念

出力には別の重要な部分があります---端子出力。これに関しては、**asops.tex for java**一般[ioutputterminal](https://reference.aspose.com/tex/java/com.Aspose.TeX/IOutputTerminal)インターフェイスを2つのメソッドがあると定義します。そのうちの1人は[BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html)インスタンスを返します。別のものは、[outputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html)インスタンスを基礎となるストリームとして返します。インターフェイスの実装を以下で説明します。

### コンソールへの端子出力の書き込み

これを行うには、[OutputConsoleterminal](https://reference.aspose.com/tex/java/com.Aspose.TeX/OutputConsoleTerminal)クラスのインスタンスになるには、[Terminalout](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXOptions#getTerminalOut--)オプションを設定する必要があります。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

繰り返しますが、これはオプションのデフォルト値であるため、指定する必要はありません。このため、このセクションはデモンストレーションのみを提供します。

### ファイルへの端子出力の書き込み

入力端子とは異なり、**Java** for Java **は[ioutputterminal](https://reference.aspose.com/tex/java/com.Aspose.TeX/IOutputTerminal)の実装を提供します。これにより、出力ディレクトリのファイルに端子出力を書き込むことができます。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}} 

ここでは、TEXエンジンに、[<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trmという名前のファイルに端子出力を書き込むように依頼します。しかし、これは必要ありません。 [ioutputterminal](https://reference.aspose.com/tex/java/com.Aspose.TeX/IOutputTerminal)の実装の他のインスタンスをコンストラクターに渡すこともできます。