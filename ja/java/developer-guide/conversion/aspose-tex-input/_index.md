---
translation: true
template: /templates/_template-java.md
title: Aspose.TeXの入力インターフェイス| Java
linktitle: Aspose.TeXの入力インターフェイス
weight: 15
url: /java/aspose-tex-input/
description: 入力形式として、Texを使用したJava用のAspose.TeX APIソリューションの変換機能については、コードの例で説明します。
lastmod: "2026-04-21"
---

{{<section overview>}}

I/O実装の正式な定義については、Java **[API Reference](https://reference.aspose.com/tex/java/com.aspose.tex/)の** Aspose.TeXを参照してください。

ファイルシステムと ZIP の例は `hello-world.tex` を `hello-world.xps` に組版します。`inputDirectory` に TeX ファイルを含むフォルダーを、`outputDirectory` に既存の出力フォルダーを指定します。ZIP 入力では、`inputZip` に `in/hello-world.tex` を含むアーカイブを指す `java.nio.file.Path` を指定します。 選択した例で使用する Aspose.TeX クラス、`com.aspose.tex.rendering.XpsDevice`、必要な `java.io` と `java.nio.file` のクラスをインポートします。呼び出し元のメソッドは例外を処理するか宣言する必要があります。評価版の制限を避けるため、[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用してください。

## 入力ディレクトリの概念

Tex言語のI/O Primitivesはファイル名のみを扱うことができるため、**Java** Aspose.TeXは、ディレクトリを名前とデータのバルクのマッピングとして定義します。データの大部分は、ファイル、ストリーム、配列などであるはずです。APIにより、入力および出力作業ディレクトリを個別に指定できます。一般的な[iinputworkingdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/)インターフェイスを提供します。これは、ユーザーが独自の目的で実装できる。また、独自の実装も提供します。これについては、以下で説明します。インターフェイスは[getFile()](https://reference.aspose.com/tex/java/com.Aspose.TeX/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-)メソッドを定義します。これは、データストリームを返してファイルのフルネームを決定しますが、仮説的に異なる名前を最初の引数として使用します。実際、マッピングキーです。

### ディスクファイルシステムからファイル入力を取得します

これが私たちがそれをする方法です：

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputFileSystemDirectory.java" >}}

このユースケースは非常に簡単なので、長い間それについては言及しません。

### ZIPアーカイブからファイル入力を取得します

また、入力ファイルをZIPアーカイブに配置して、入力ディレクトリと見なすこともできます。この場合、次のように進める必要があります。

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputZipDirectory.java" >}}

最初に、zipファイルを含むストリームを作成します。次に、変換オプションを作成した後、[inputzipdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/)クラスのインスタンスになるように[inputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--)オプションを設定します。コンストラクターの2番目の引数は、アーカイブ内のベースパスです。アーカイブ全体を入力ディレクトリにしたい場合は、空の文字列を渡す必要があります。 この例は TeX ジョブが終了するまで ZIP ストリームと入力ディレクトリを開いたままにし、その後に閉じます。対話なしで実行され、端末出力をメモリに保存します。

## 入力端子の概念

次に、端子入力もあることを覚えておいてください。これに関しては、**Aspose.TeX for java**一般[iinputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/)インターフェイスを2つのメソッドがあると定義します。そのうちの1人は[BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html)インスタンスを返します。別のメソッドは、[inputstream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html)を基礎となるストリームとして返します。インターフェイスの実装を以下で説明します。

### コンソールから端子入力を取得します

これを行うには、[inputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/)クラスのインスタンスになるには、[Terminalin](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--)オプションを設定する必要があります。

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputConsoleTerminal.java" >}}

`InputConsoleTerminal` はこのオプションのデフォルト値です。この例は端末の設定のみを示し、ジョブは実行しません。端末入力を要求するジョブには、ユーザー入力または独自の端末実装が必要です。上記のファイルシステムと ZIP の例は、完全な入力ファイルを使用して対話なしで実行されます。

理論的には、予測可能な動作を備えたインタラクティブなTEXファイル(またはスクリプト)がある場合、TEXエンジンの要求に応答するための補完的なスクリプトを含む入力端子のバージョンを実装することをお勧めします。時間があるときは手を試してみてください！