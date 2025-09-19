---
translation: true
template: /templates/_template-python-net.md
title: Aspose.TeXの入力インターフェイス| .NET経由でPython用のAspose.TeX
linktitle: Aspose.TeXの入力インターフェイス
weight: 15
url: /python-net/aspose-tex-input/
description: 入力形式として、Pythonを使用したPython用のAspose.TeX APIソリューションの変換機能については、コードの例で説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

> **Aspose.TeX for Python** の I/O 実装の正式な定義については、[API リファレンス](https://reference.aspose.com/tex/python-net/aspose.tex.io/) を参照してください。

## 入力ディレクトリの背後にあるアイデア

Tex言語のI/O Primitivesはファイル名のみを処理できることを考えると、**Python** Aspose.TeX **ディレクトリを名前とデータのコレクションのマッピングとして定義します。これらのデータコレクションは、ファイル、ストリーム、配列、またはその他のタイプです。 APIを使用すると、入力および出力作業ディレクトリの個別の仕様が可能になります。一般的な[inputworkingdirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/)クラスを提供します。これは、ユーザーが特定のニーズに合わせて実装できる。さらに、APIは組み込みの実装を提供します。これについては後で説明します。インターフェイスには、[get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool)メソッドが含まれます。これは、データストリームを取得し、特定の名前に基づいて完全なファイル名を決定します。これは、マッピングキーとして機能します。

### ディスクファイルシステムからファイル入力を取得します

これが私たちが取るアプローチです：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

この特定のユースケースはかなり簡単なので、今すぐ先に進むことができます。

### ZIPアーカイブからファイル入力を取得します

別のオプションは、入力ファイルをzipアーカイブに保存し、入力ディレクトリとして扱うことです。このようなシナリオでは、次の手順に従う必要があります。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

そもそも、zipファイルを含むストリームを作成します。その後、変換オプションを作成した後、[inputzipdirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/)クラスのインスタンスを[input_working_directory](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/input_working_directory/)プロパティに割り当てます。コンストラクターの2番目のパラメーターは、アーカイブ内のベースパスを表します。アーカイブ全体が入力ディレクトリとして機能することを望む場合は、引数として空の文字列を提供する必要があります。

## 入力端子の背後にあるアイデア

次に、ターミナル入力の概念を考えてみましょう。 **pythonのAspose.TeX**この目的のために特に一般的な[iinputterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/)インターフェイスを定義します。これには、[TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/)の実装のインスタンスを返す単一のプロパティが含まれます。利用可能な実装については、後で説明します。

### コンソールから端子入力を取得します

これを達成するには、[inputConsoleterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/)クラスのインスタンスを[Terminal_in](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/terminal_in/)オプションに割り当てる必要があります。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

ただし、正直なところ、これはオプションのデフォルト値であるため、明示的に指定する必要はありません。他の実装がないことを考えると、このセクションは純粋にデモンストレーションのためです。

理論的には、予測可能な動作を備えたインタラクティブなTEXファイル(またはスクリプト)がある場合、TEXエンジンの要求に応答する対応するスクリプトを含む入力端子のバージョンを実装することが望ましい場合があります。機会があれば、お気軽にお試しください！