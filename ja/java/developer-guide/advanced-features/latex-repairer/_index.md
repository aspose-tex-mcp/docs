---
translation: true
template: /templates/_template-java.md
title: ラテックスファイルの修理| Java用のAspose.TeX
linktitle: ラテックスファイルの修理
weight: 30
url: /java/latex-repair/
description: JavaのAspose.TeX API内のラテックスファイル修理機能については、この記事で説明します。機能の使用方法のコード例を学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}

## ラテックスファイルを確認して修復する方法

テキストファイルがLaTexファイルであるかどうかがわからず、それをタイプセットにしたい場合は、JavaのAspose.TeX APIが提供するチェックと修復のラテックス機能を利用できます。以下の例では、Java ExampleプロジェクトのAspose.TeXからサンプルファイル「Invalid-Latex.tex」を確認して修復します。

そもそも、サンプルファイルはTex構文を使用しているように見えるが、LaTexに必要な構造がないことに注意することが重要です。ご存知かもしれませんが、ラテックスファイルには、\ DocumentClassコマンドから始まる前文と、特に\ begin {document}と\ end {document}の間にドキュメント環境に囲まれたボディを含める必要があります。

次に、Javaコードサンプルを見てみましょう。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

通常のTexジョブと同様に、実行しようとしているプロセスのオプションを保持するオブジェクトを作成することから始めます。これらのオプションのほとんどは、通常のTEXジョブのオプションと同じです。実際、[setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.Aspose.TeX.features/latexrepaireroptions/#setInputWorkingDirectory-com.Aspose.TeX.IInputWorkingDirectory-)メソッドを呼び出して、入力ファイルを読み取るスペースを指定します。ただし、この例では、ファイルシステムのメイン入力ファイルへのフルパスを提供し、メイン入力ファイルにカスタムファイルを含めることはないため、ここでは使用しません。次に、[SetOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.Aspose.TeX.features/latexrepaireroptions/#setOutputWorkingDirectory-com.Aspose.TeX.IOutputWorkingDirectory-)メソッドを呼び出して、出力ファイルの書き込みスペースを指定します。呼び出された場合、[setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.Aspose.TeX.features/latexrepaireroptions/#setRequiredInputDirectory-com.Aspose.TeX.IInputWorkingDirectory-)メソッドにより、オプションは、Aspose.TeXライブラリに埋め込まれていないラテックスパッケージを保存できるスペースを指します。最後に、[setguesspackagecallback()](https://reference.aspose.com/tex/java/com.Aspose.TeX.features/latexrepaireroptions/#setGuessPackageCallback-com.Aspose.TeX.features.IGuessPackageCallback-)メソッドについては後で説明します。

オプションが割り当てられたら、プロセスの実行を進めることができます。

それで、チェックと修復のプロセスはどのようなものですか？ APIが入力ファイルで`documentClass`の発生を検索することから始まります。発見されていない場合、APIは、`documentClass {article}`をファイルの開始時に挿入する必要があると想定しています。この情報は、修理レポートファイル(.log)に記録されます。

次に、プロセスが最初から調整された入力ファイルのスキャンを開始します。 LaTex形式を装備したTEXエンジンは、ある時点で、「{document}」が既にあるべきである場合にまだ見つかっていないことを示すエラーを投げることができます。このようにして、「{document}」を挿入する必要がある位置が定義され、レポートに反映されます。

ファイルをさらにスキャンしている間、エンジンは未定義のコマンドや環境に遭遇する可能性があります。そのような場合、APIは、最も一般的なコマンドと環境のいくつかについて、[これらのパッケージが含まれるまで定義されていないコマンドと環境を定義するものを埋め込んだ](/tex/{{lang.url-fragment}}net/embedded-packages/)(5)(5)(5)(5)(5)で仮定することができます。ただし、[iguesspackagecallback](https://reference.aspose.com/tex/java/com.Aspose.TeX.features/iguesspackagecallback/)インターフェイスを実装するクラスによって、そのような仮定を外部から行うことができます。このようなクラスを開発したら、`setguesspackagecallback()`メソッドを呼び出すことにより、そのインスタンスをプロセスに渡す必要があります。

`fancehdr`パッケージに`\ head`コマンドを単純にマップする基本的な例があります。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}

サンプルファイルに関しては、エンジンは最初に`\ Chapter`コマンドに遭遇します。これは、「記事」ドキュメントクラスで定義されていないが、`Book`ドキュメントクラスで定義されています。 APIはドキュメントクラスを調整して、修復されたファイルの最終バージョンが `\ documentclass {book}`で始まるようになります。次に、エンジンは前述の`\ lhead`コマンドを見つけ、 `\ usepackage {fancyhdr}`をプリアンブルに挿入する必要があると判断します。ファイルの後半で発生する`\ href`および `\ increctgraphics`コマンドは、修理業者に` \ usepackage {hyperRef} `および` \ usepackage {graphics} `を挿入します。これらの決定は、APIの内部マッピングに基づいて行われます。前と同様に、これらのすべての修理はレポートファイルに記録されています。

最後に、ラテックス文書の適切な結論が欠落しているため、エンジンは異常に終了します。その結果、修理業者は`\ end {document}`をファイルの最後に追加し、レポートにこの情報を含めます。

元のファイルの固定バージョンを作成した後、修理業者は最終検証のためにTEXジョブを実行します。この例では、この実行は重要なエラーを検出しないため、固定バージョンを予想どおりに多かれ少なかれタイプセットすることができます。

これが完全なレポートです：

```
元のファイルを修復しています...
--------------------------------------------------------------------------------
    \documentclass が元のファイル内に見つかりません。先頭に挿入しました。
    \begin{document} が元のファイル内に見つかりません。3 行目の 0 番目に挿入しました。
    3 行目の 0 番目にあるコマンド \chapter は未​​定義です。プリアンブルで \usepackage{package_name} を使用することを検討してください。
    ここで 'package_name' は、このコマンドを定義するパッケージの名前です。
    5 行目の 0 番目にあるコマンド \lhead は未定義です。\usepackage{fancyhdr} がプリアンブルに挿入されています。
    'fancyhdr' パッケージがこのコマンドを定義していると思われるためです。
    8 行目の 0 番目にあるコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
    'hyperref' パッケージがコマンドを定義していると思われるため。
17行目の位置 0 にあるコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
    'hyperref' パッケージがコマンドを定義していると思われるため。
20行目の位置 0 にあるコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
    'hyperref' パッケージがコマンドを定義していると思われるため。
27行目の位置 0 にあるコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
    'hyperref' パッケージがコマンドを定義していると思われるため。
32行目の位置 0 にあるコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
    'hyperref' パッケージがコマンドを定義していると思われるため。
54 行目、位置 2 のコマンド \includegraphics は未定義です。\usepackage{graphicx} がプリアンブルに挿入されています。
    'graphicx' パッケージがコマンドを定義していると思われるため。
67 行目、位置 0 のコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
    'hyperref' パッケージがコマンドを定義していると思われるため。
95 行目、位置 57 のコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
   'hyperref' パッケージがコマンドを定義していると思われるため。
96 行目、位置 0 のコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
    'hyperref' パッケージがコマンドを定義しているはずなので。
98行目、100番目のコマンド \href は未定義です。\usepackage{hyperref} がプリアンブルに挿入されています。
    'hyperref' パッケージがコマンドを定義しているはずなので。
\end{document} が元のファイルにありません。末尾に挿入されています。

修復されたファイルを確認しています...
--------------------------------------------------------------------------------
修正されたファイルには重大なエラーはありません。
```

**無料[** ai latex Repairer **](https://products.aspose.ai/tex/latex-repairer)Webアプリもチェックしてください。これは、[.NET APIのAspose.TeX]内に実装された機能に基づいて構築され、「Iguesspackagecalback」インターフェースのより高度な実装を伴います。