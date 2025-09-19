---
translation: true
template: /templates/_template-net.md
title: Aspose.TeXの入力インターフェイス| .NET
linktitle: Aspose.TeXの入力インターフェイス
weight: 15
url: /net/aspose-tex-input/
description: 入力形式として、Texを使用した.NET用のAspose.TeX APIソリューションの変換機能については、コードの例で説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

I/O実装の正式な定義については、.NET **[API参照](https://reference.aspose.com/tex/net/aspose.tex.io/)の** Aspose.TeXを参照してください。

## 入力ディレクトリの概念

Tex言語のI/O Primitivesはファイル名のみを扱うことができるため、**Aspose.TeX for .net**ディレクトリを名前とデータのバルクの間のマッピングとして定義します。データの大部分は、ファイル、ストリーム、配列などであるはずです。APIにより、入力および出力作業ディレクトリを個別に指定できます。一般的な[iinputworkingdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/)インターフェイスを提供します。これは、ユーザーが独自の目的で実装できる。また、独自の実装も提供します。これについては、以下で説明します。インターフェイスは[getFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/)メソッドを定義します。これは、データストリームを返してファイルのフルネームを決定しますが、仮説的に異なる名前を最初の引数として使用します。実際、マッピングキーです。

### ディスクファイルシステムからファイル入力を取得します

これが私たちがそれをする方法です：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.cs" >}}

このユースケースは非常に簡単なので、もうそれに集中する必要はありません。

### ZIPアーカイブからファイル入力を取得します

また、入力ファイルをZIPアーカイブに配置して、入力ディレクトリと見なすこともできます。この場合、次のように進める必要があります。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InputZipDirectory.cs" >}}

最初に、zipファイルを含むストリームを作成します。次に、変換オプションを作成した後、[inputzipdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/)クラスのインスタンスになるように[inputWorkingDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/inputworkingdirectory/)オプションを設定します。コンストラクターの2番目の引数は、アーカイブ内のベースパスです。アーカイブ全体を入力ディレクトリにしたい場合は、空の文字列を渡す必要があります。 

## 入力端子の概念

さて、端子入力もあることを覚えておく時が来ました。これについては、**asops.tex for .net**が一般[iinputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/)インターフェイスを定義します。実装を以下で説明します。

### コンソールから端子入力を取得します

これを行うには、[inputConsoleterminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/)クラスのインスタンスになるには、[Terminalin](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/terminalin/)オプションを設定する必要があります。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.cs" >}}


しかし、真実を伝えるために、これはオプションのデフォルト値であるため、指定する必要はありません。この事実のため、および他の実装がない限り、このセクションはデモンストレーションのみを提供します。

理論的には、予測可能な動作を備えたインタラクティブなTEXファイル(またはスクリプト)がある場合、TEXエンジンの要求に応答するための補完的なスクリプトを含む入力端子のバージョンを実装することをお勧めします。時間があるときは手を試してみてください！