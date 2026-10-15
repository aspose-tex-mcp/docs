---
translation: true
template: /templates/_template-java.md
title: LaTeX ファイルの修復 | Aspose.TeX for Java
linktitle: LaTeX ファイルの修復
weight: 30
url: /java/latex-repair/
description: Aspose.TeX API for Java の LaTeX ファイル修復機能について説明します。機能の使用方法のコード例をご覧ください。
lastmod: "2026-02-27"
---

{{<section overview>}}

## LaTeX ファイルのチェックと修復方法

テキストファイルが LaTeX ファイルかどうか確信が持てず、組版したい場合は、Aspose.TeX API for Java が提供する LaTeX のチェックおよび修復機能を利用できます。以下の例では、Aspose.TeX for Java のサンプルプロジェクトにある `invalid-latex.tex` というファイルをチェックし、修復します。

まず最初に、サンプルファイルは TeX 構文を使用していますが、LaTeX に必要な構造が欠けていることに注意してください。ご存知のとおり、LaTeX ファイルは `\documentclass` コマンドで始まるプリアンブルと、`\begin{document}` と `\end{document}` の間にある本文から構成されます。

`inputFile` に `invalid-latex.tex` の完全パス、`outputDirectory` に既存の出力フォルダー、`packagesDirectory` に `fancyhdr.sty` と依存ファイルを含むフォルダーを指定します。以下のコールバックを import 文とともに `PackageGuesser.java` として保存し、修復処理の前に `PackageGuesser packageGuesser = new PackageGuesser()` を作成します。使用する Aspose.TeX クラスをインポートし、例外を処理または宣言してください。[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用します。入出力ディレクトリは修復が終わるまで開いたままにし、その後閉じます。

{{< gist "aspose-com-gists" "e17f869aabed3881c74973f5e875d539" "Example-LaTeXRepairer.java" >}}

通常の TeX ジョブと同様に、まず処理に必要なオプションを保持するオブジェクトを作成します。これらのオプションは通常の TeX ジョブとほぼ同じです。たとえば、[setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-) メソッドで入力ファイルを読むディレクトリを指定しますが、この例ではファイルシステム上のメイン入力ファイルへのフルパスを直接渡すため使用していません。次に、[setOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-) メソッドで出力ファイルを書き込むディレクトリを指定します。必要に応じて、[setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) メソッドで、Aspose.TeX ライブラリに組み込まれていない LaTeX パッケージを格納できるディレクトリを指すことができます。最後に、[setGuessPackageCallback()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) メソッドについては後述します。

オプションが設定されたら、プロセスを実行します。

では、チェックと修復の流れはどのようになるのでしょうか。まず API は入力ファイル内に `\documentclass` があるか検索します。見つからなければ、API はファイルの先頭に `\documentclass{article}` を挿入すべきだと判断し、修復レポート（.log）にその情報を記録します。

次に、調整された入力ファイルの先頭からスキャンを開始します。LaTeX フォーマットが組み込まれた TeX エンジンは、途中で `\begin{document}` がまだ見つからないというエラーを出すことがあります。このとき、` \begin{document}` を挿入すべき位置が特定され、レポートに反映されます。

ファイルをさらに走査していくと、エンジンは未定義のコマンドや環境に出くわすことがあります。そのような場合、API は最も一般的なコマンドや環境に対して、[埋め込み必須パッケージ](/tex/{{lang.url-fragment}}net/embedded-packages/)（これらのコマンドや環境を定義するパッケージ）を自動的に推測して使用します。ただし、[IGuessPackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/) インターフェイスを実装したクラスを作成すれば、外部からこの推測ロジックをカスタマイズできます。そのクラスのインスタンスは `setGuessPackageCallback()` メソッドでプロセスに渡します。

この例は `\lhead` コマンドを `fancyhdr` パッケージに対応付けます。コールバックには先頭のバックスラッシュを除いた名前が渡され、未知のコマンドや環境には空文字列を返します。

{{< gist "aspose-com-gists" "e17f869aabed3881c74973f5e875d539" "Example-PackageGuessingCallback.java" >}}

サンプルファイルについて説明すると、エンジンは最初に `\chapter` コマンドに出会います。これは `article` クラスには定義されていませんが、`book` クラスには定義されています。そのため API はドキュメントクラスを `\documentclass{book}` に変更します。次に `\lhead` コマンドが見つかり、プリアンブルに `\usepackage{fancyhdr}` を挿入すべきと判断します。さらにファイル後半で `\href` と `\includegraphics` が現れたため、Repairer はそれぞれ `\usepackage{hyperref}` と `\usepackage{graphicx}` をプリアンブルに追加します。これらの判断は API の内部マッピングに基づいて行われ、すべての修復内容はレポートファイルに記録されます。

最終的に、LaTeX 文書の正しい終了部が欠如しているためエンジンは異常終了します。その結果、Repairer はファイル末尾に `\end{document}` を付加し、レポートにもその旨を記載します。

修復後、Repairer は最終確認のために TeX ジョブを実行します。この例の最終レポートには致命的なエラーがありません。`run()` の戻り値は元のスキャンの状態を示す場合があるため、修復レポートと修正済み `.tex` ファイルを確認してください。修復処理は不足している外部リソースを提供しません。たとえばサンプルが参照する `Figures/uet_logo.pdf` は、完全な組版のために別途用意する必要があります。

以下は完全なレポートです。

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

**また、[**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer) の無料ウェブアプリもぜひお試しください。このアプリは [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) に実装された機能をベースにしており、`IGuessPackageCallback` インターフェイスのより高度な実装が含まれています。**
