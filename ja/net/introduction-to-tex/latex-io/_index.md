---
translation: true
template: /templates/_template-net.md
title: ラテックスI/O
linktitle: ラテックス入力/出力
weight: 17
url: /net/latex-io/
description: このページでは、ラテックスを出力または入力形式として操作することの特性と、 * .aux *ファイルがラテックスの必須部分としての特性について簡単に説明します。
keywords: ラテックスIO、ラテックスI、ラテックスO、ラテックス入力ファイル、ラテックスへの入力
lastmod: "2025-06-09"
---

{{<section overview>}}

## ラテックスファイル

次の構造を持つ[texファイル](/tex/{{lang.url-fragment}}net/tex-io/#tex-file)がある場合、このファイルを *latexファイル* と呼びます。


```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

ここで、 `<a document class>`は[ドキュメントクラス](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes)の名前です。これは、特定の種類のドキュメントに最も適した出力ドキュメントのページとマクロの外観を定義する入力TEXファイルです。

正直に言うと、 `\ documentClass {}`、`\ nonstopmode`などの前にプリミティブコントロールシーケンスを挿入できます。ただし、各ラテックスマクロは、ファイルの適切な部分にあるかどうかを確認します。

LaTexファイルを使用するというコンテキストでは、Tex [input](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)および[output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)について注目に値するものがいくつかあります。

## ラテックス出力ファイル

典型的なLaTeXジョブは、[ジョブ名](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)という名前と拡張子*.aux*を持つ補助出力ファイルを作成します。このファイルには、例えば数式（方程式）にラベルを設定し、それをテキスト内のどこかで参照する場合など、ジョブの実行中にエンジンが収集する参照データが含まれるのが一般的です。このようなデータを使用しない場合、このファイルにはTeXプリミティブの1つである`\relax`制御シーケンスのみが含まれます。ですから、驚かないでください。

`\openout`、 `\ write`、および` \ closeout`プリミティブは禁止されていませんが、パッケージはそれらに最も適した場所です。したがって、それらを開発している場合は、独自のカスタムパッケージでそれらをより適切に使用する必要があります。

出力の他の部分はarbitrary意的であり、一般的な[Tex出力](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)の概念にも従い、Texファイル(プログラム)が何をすべきか、使用しているパッケージ(以下を参照)などに依存します。

## ラテックス入力ファイル

前述の *.aux*ファイルは、LaTeXの入力として必須です。アルゴリズム上、LaTeXはこれらの参照関連のタスクを1回の実行で完了できないため、同じジョブを2回実行する必要があります。1回目はデータ収集、2回目はそれらのデータの使用です。多くのLaTeXベースのソフトウェアシステムは、LaTeXジョブを自動的に2回実行します。ちなみに、Aspose.TeX APIには、この動作を制御できる[オプション](/tex/{{lang.url-fragment}}net/other-options/#ジョブの繰り返し方法)があります。

別の必須部分は[ドキュメントクラス](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)です。ドキュメントクラスファイルは、他のファイルに暗黙的に依存する場合があります。これは、ラテックス入力にも含まれています。

基本的なラテックスとそのドキュメントクラスの範囲を超えて機能を使用したいが、特定のTexエンジンの実装でサポートされている場合は、通常、プリアンブルでエンジンに通知する必要があるパッケージを使用します。 * LaTexパッケージ *は、ファイル、または1つの名前で組み立てられたファイルのグループであり、そのような機能を提供します。エンジンに通知するには、パッケージが定義されている場合は、パッケージ名と省略オプションを使用して`\usepackage`コマンドを使用する必要があります。

例えば、


```tex
\usepackage[a6paper,landscape]{geometry}
```

`\input`、`\openin`、`\read`、`\closein` プリミティブは禁止されていませんが、パッケージ内での使用が最も適しています。したがって、これらのプリミティブを開発する場合は、独自のカスタムパッケージ内で使用することをお勧めします。

入力の他の部分はarbitrary意的であり、一般的な[Tex入力](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)の概念にも従っており、Texファイル(プログラム)が何をすべきか、使用しているパッケージなどに依存します。