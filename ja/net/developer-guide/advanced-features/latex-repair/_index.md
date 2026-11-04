---
translation: true
template: /templates/_template-net.md
title: LaTeX ファイル修復 | Aspose.TeX for .NET
linktitle: LaTeX ファイル修復
weight: 30
url: /net/latex-repair/
description: Aspose.TeX API の .NET 用 LaTeX 修復ソリューションについて説明しています。機能の使用方法を示すコード例をご覧ください。
lastmod: "2026-11-04"
---

{{<section overview>}}

## LaTeX ファイルのチェックと修復方法

テキストファイルが LaTeX ファイルだと思われ、組版したいが本当に LaTeX ファイルか確信が持てない（LaTeX の世界に不慣れな場合など）場合は、Aspose.TeX API for .NET が提供する LaTeX のチェックと修復機能を試すことができます。以下の例では、Aspose.TeX for .NET のサンプルプロジェクトに含まれる `invalid-latex.tex` というサンプルファイルをチェックし、修復します。

まず最初に、サンプルファイルは TeX 構文を使用しているように見えても、LaTeX が要求する構造を持っていないことを指摘しておきます。ご存知のとおり、LaTeX ファイルは `\documentclass` コマンドで始まるプレアンブルと、`document` 環境内の本文（`\begin{document}` と `\end{document}` の間）を持つ必要があります。

それでは C# のコードサンプルを見てみましょう。

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Examples_LaTeXRepairerExample" >}}

通常の TeX ジョブと同様に、まずは実行したいプロセスのオプションを含むオブジェクトを作成します。ほとんどのオプションは通常の TeX ジョブの場合と同じです。たとえば、[InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/) は入力ファイルを読み取るべき場所を示します。ここでは、ファイルシステム上のメイン入力ファイルへのフルパスを指定しているため使用しません。また、[OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/) は出力ファイルを書き込む場所です。[RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/) を設定すると、Aspose.TeX ライブラリに組み込まれていない LaTeX パッケージを保存できる場所を指します。[GuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/) プロパティについては後述します。

オプションを設定したら、単にプロセスを実行するだけです！

では、チェックと修復のプロセスはどのように行われるのでしょうか。まず API は入力ファイル内に `\documentclass` があるか検索します。見つからなければ、ファイルの先頭に `\documentclass{article}` を挿入したとみなします。この事実は修復レポートファイル（`.log`）に記録されます。

次に、調整された入力ファイルの先頭からスキャンを開始します。LaTeX 形式で動作する TeX エンジンは、途中で `\begin{document}` が見つからないことを示すエラーを出すことがあります。その場合、`\begin{document}` を挿入すべき位置が決定され、レポートに反映されます。

エンジンがファイルをさらに走査すると、未定義のコマンドや環境が見つかることがあります。API は、最も一般的なコマンドや環境に対して、[埋め込み必須パッケージ](/tex/{{lang.url-fragment}}net/embedded-packages/)（これらのコマンドや環境を定義するパッケージ）を推測できます。ただし、外部から [IGuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/) インターフェイスを実装してその推測ロジックを提供することも可能です。`GuessPackageCallback` オプションにそのクラスのインスタンスを割り当てます。

以下は、`\lhead` コマンドを `fancyhdr` パッケージにマッピングする非常にシンプルな例です。

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Examples_PackageGuessingCallback" >}}

サンプルファイルの場合、エンジンは最初に `\chapter` コマンドに遭遇します。これは `article` クラスには定義されていませんが、`book` クラスには定義されています。したがって API は文書クラスを `\documentclass{book}` に変更します。続いてエンジンは `\lhead` コマンドを見つけ、プレアンブルに `\usepackage{fancyhdr}` を挿入すべきと判断します。後に出現する `\href` と `\includegraphics` コマンドに対しては、プレアンブルにそれぞれ `\usepackage{hyperref}` と `\usepackage{graphicx}` を挿入します。これらの判断は API の内部マッピングに基づいており、すべての修正はレポートファイルに記録されます。

最後に、LaTeX 文書の通常の終了が欠落しているためエンジンは異常終了します。このため Repairer はファイルの末尾に `\end{document}` を追加し、レポートにその事実を反映させます。

修正された元ファイルが生成されたら、Repairer は最終チェックのためにそのファイルで再度 TeX ジョブを実行します。この例では、致命的なエラーは見つからず、修正後のファイルはほぼ期待通りに組版できます。

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

## LaTeX数式修復AIエージェントの構築

このワークフローは、Aspose.TeXネイティブ修復APIの構造検証とLLMコアのコンテキスト推論を組み合わせることで、エラーのないレンダリングパイプラインを実現します。既存のLaTeXファイルのエラーをチェックして修正する独立したエージェントとして、または数式作成プロセスの一部として使用できます。

### LaTeX構文を修復するAIエージェントのワークフローアーキテクチャ

![AIによるLaTeX修復ワークフローのブロックスキーム](/tex/images/net/tutorial/blockscheme-for-math-repairing.png)

1. 構文処理とインテント抽出（LLMレイヤー）
ユーザーは、対話形式の指示、生のテキストスニペット、コピーした数式、または`.latex`ファイルを提供します。エージェントはLLMにコアとなる数式インテントを抽出するよう指示し、最適化されたLaTeX数式ブロックを出力します。

2. ネイティブ構造の自動修正（Aspose.TeXリペアラー）
生成された数式断片は、ネイティブのAspose.TeX修復ライフサイクルを通して処理され、開発者が正規表現ラッパーをハードコーディングすることなく、標準的な構造境界が構築されます。

エージェントはフラグメントをファイルに保存し、そのファイルに対して `LaTeXRepairer` を実行します。Repairer は不足している `\documentclass`、`\begin{document}`、`\end{document}` を挿入し、修正済みファイル (`-fixed.tex`) とレポート (`.log`) を出力ディレクトリに書き込みます。数式モードには切り替えないため、数式はあらかじめ `$...$` などの数式区切り文字で囲んでおく必要があります。

3. 実行とアセット/レポートの生成（レンダリングエンジン）
`LaTeXRepairer.Run()` は元のファイルに対する結果を返すため、エージェントは修正済みファイルのチェック結果をレポートから読み取ります。重大なエラーがなければ、エージェントはレポートを作成するか、`TeXJob` を実行して修正済みファイルを目的のビジュアル形式に変換します。

**無料の **[**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer)** ウェブアプリもぜひお試しください。このアプリは [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) の機能を基に構築されており、`IGuessPackageCallback` インターフェイスの高度な実装を取り入れています。**
