---
translation: true
template: /templates/_template-net.md
title: ラテックスファイルの修理| .netのAspose.TeX
linktitle: ラテックスファイルの修理
weight: 30
url: /net/latex-repair/
description: .NETラテックス修復用のAspose.TeX APIソリューションについては、この記事で説明します。機能の使用方法に関するコードの例を学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}

## ラテックスファイルを確認して修復する方法

ラテックスファイルであると思われるテキストファイルがあり、それがタイプセットになりたいが、それが実際にラテックスファイルであるかどうかはわかりません(おそらくあなたはラテックスの世界に新しくなっています)。次の例では、.NET例プロジェクトのAspose.TeXから、サンプルファイル「Invalid-Latex.tex」を確認して修復します。

まず第一に、サンプルファイルはTex構文を使用しているように見えますが、LaTexに必要な構造がないことに言及する価値があります。ご存知かもしれませんが、ラテックスファイルには、`documentClass`コマンドと「Document」環境内のボディ、つまり `\ begin {document}`と `\ end {document}`の間にボディから始まる前文が必要です。

次に、C＃コードサンプルを見てみましょう。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-LaTeXRepairer.cs" >}}

通常のTexの仕事と同様に、最初に実行しようとしているプロセスのオプションを含むオブジェクトを作成します。それらのほとんどは、通常のTexジョブのオプションと同じです。実際、[inputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/)は、入力ファイルを読み取るスペースです。ファイルシステムのメイン入力ファイルへのフルパスを提供し、メイン入力ファイルにカスタムファイルが含まれていないため、ここでは使用しません。次に、[outputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/)は、出力ファイルを書き込む必要があるスペースです。 [rebulyinputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/)が割り当てられた場合、Asoppes.texライブラリに埋め込まれていないラテックスパッケージを保存できるスペースを指します。 [推測PackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/)プロパティについては後で説明します。

オプションを割り当てた後、プロセスを実行するだけです！

それで、チェックと修復のプロセスはどのようなものですか？まず、APIは入力ファイルを検索して`documentClass`の発生を検索します。失敗した場合、 `\ documentclass {article}`をファイルの最初に挿入する必要があると想定しています。この事実は、修理レポートファイル( `.log`)に反映されています。

次に、最初から調整された入力ファイルのスキャンを開始します。ラテックス形式で充電されたTEXエンジンは、ある時点でエラーを投げる可能性があり、「{document} `がこれまでに発見されていないことを示していますが、すでに発生するはずです。したがって、「{document}」を挿入する必要がある位置が定義され、レポートに反映されます。

エンジンがファイルをさらにスキャンすると、未定義のコマンドまたは環境が見つかる場合があります。 APIは、最も一般的なコマンドと環境の一部について、[埋め込まれた必須パッケージ](/tex/{{lang.url-fragment}}net/embedded-packages/)(これらのパッケージが含まれるまで定義されていないコマンドと環境を定義するもの)で仮定を作成できます。ただし、[iguesspackagecallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/)インターフェイスを実装することにより、そのような仮定を外部から行う方法があります。このようなクラスのインスタンスは、「buesspackagecallback」オプションに割り当てる必要があります。

`fancehdr`パッケージに`\ head`コマンドをマップするだけの非常に簡単な例があります。


{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.cs" >}}


サンプルファイルに関しては、エンジンは最初に`\ Chapter`コマンドに遭遇します。これは、「記事」ドキュメントクラスで定義されていないが、`Book`ドキュメントクラスで定義されています。 APIはドキュメントクラスを調整して、固定ファイルの最終バージョンが「\ documentClass {book}」で始まるようになります。次に、エンジンは前述の`\ lhead`コマンドを見つけ、 `\ usepackage {fancyhdr}`をプリアンブルに挿入する必要があると判断します。後で発生する`\ href`および `\ increctgraphics`コマンドは、修理業者を挿入するようにします。これらの決定は、APIの内部マッピングに基づいています。繰り返しますが、そのような修正はすべてレポートファイルに記録されます。

最後に、ラテックスドキュメントの通常の終了が欠落しているため、エンジンは異常に終了します。これにより、修理業者は`\ end {document}`をファイルの最後に追加し、レポートにこの事実を反映させます。

元のファイルの固定バージョンが構築されると、修理業者は最終チェックのためにTEXジョブを実行します。この例では、この実行には重要なエラーが見つかりません。そのため、固定バージョンは予想通りに多かれ少なかれタイプセットされる可能性があります。

これが完全なレポートです：


```
Trying to repair the original file...
--------------------------------------------------------------------------------
\documentclass is missing in the original file. Inserted at the beginning.
\begin{document} is missing in the original file. Inserted at line 3, pos. 0.
The command \chapter at line 3, pos. 0 is undefined. Consider using \usepackage{package_name} in the preamble,
    where 'package_name' is the name of the package which defines this command.
The command \lhead at line 5, pos. 0 is undefined. \usepackage{fancyhdr} is inserted in the preamble
    since the 'fancyhdr' package supposedly defines the command.
The command \href at line 8, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 17, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 20, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 27, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 32, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \includegraphics at line 54, pos. 2 is undefined. \usepackage{graphicx} is inserted in the preamble
    since the 'graphicx' package supposedly defines the command.
The command \href at line 67, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 95, pos. 57 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 96, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 98, pos. 100 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
\end{document} is missing in the original file. Inserted at the end.

Checking the repaired file...
--------------------------------------------------------------------------------
There are no critical errors in the fixed file.
```

**無料[** ai latex Repairer **](https://products.aspose.ai/tex/latex-repairer)Webアプリもチェックしてください。これは、[.NET APIのAspose.TeX]内に実装された機能に基づいて構築され、「Iguesspackagecalback」インターフェースのより高度な実装を伴います。