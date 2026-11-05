---
translation: true
template: /templates/_template-net.md
title: LaTeX 入出力 | Aspose.TeX チュートリアル
linktitle: LaTeX I/O 
weight: 17
url: /net/latex-io/
description: このページでは、LaTeX を出力または入力フォーマットとして使用する際の特有の点と、必須となる *.aux* ファイルについて簡潔に説明します。
keywords: latex 入出力, latex 入力, latex 出力, latex 入力ファイル, latex 入力
lastmod: "2026-04-22"
---

{{<section overview>}}

## LaTeX ファイル {#latex-file}

もし、次の構造を持つ[TeX ファイル](/tex/{{lang.url-fragment}}net/tex-io/#tex-file)がある場合、このファイルを *LaTeX ファイル* と呼びます:


```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

`<a document class>` は、[ドキュメントクラス](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes) の名前で、出力ドキュメントのページの外観や、特定の文書タイプに最も適したマクロを定義する入力 TeX ファイルです。

正直に言うと、`\documentclass{}` の前に `\nonstopmode` などのプリミティブ制御シーケンスを挿入することは可能です。ただし、各 LaTeX マクロは自分がファイルの適切な位置にあるかどうかを確認します。

LaTeX ファイルを扱う際の TeX の[入力](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)および[出力](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)について、いくつか留意すべき点があります。

## LaTeX 出力ファイル {#latex-output-file}

典型的な LaTeX ジョブは、[ジョブ名](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) をファイル名とし、拡張子 *.aux* を持つ補助出力ファイルを作成します。このファイルには、エンジンがジョブ実行中に収集する参照データが含まれ、例えば数式（方程式）のラベルを設定し、テキスト中で参照した場合などです。もしこのようなデータを使用しない場合、このファイルには `\relax` 制御シーケンス（TeX のプリミティブの一つ）だけが含まれます。したがって驚かないでください。

`\openout`、`\write`、`\closeout` プリミティブは禁止されているわけではありませんが、これらはパッケージで使用するのが最適です。したがって、独自のカスタムパッケージを開発している場合は、そちらで使用する方が良いでしょう。

出力の他の部分は任意であり、一般的な[TeX 出力](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) の概念に従い、あなたの TeX ファイル（プログラム）が具体的に何を行うべきか、どのパッケージ（下記参照）を使用しているかなどに依存します。

## LaTeX 入力ファイル

前述の *.aux* ファイルは、LaTeX において入力の必須部分でもあります。アルゴリズム的に、LaTeX は単一の実行で参照関連のタスクを完了できないため、同じジョブを2回実行する必要があります ── 最初の実行でデータを収集し、2回目の実行でそれらのデータを使用します。多くの LaTeX ベースのソフトウェアは、LaTeX ジョブを自動的に2回実行します。ネタバレですが、Aspose.TeX API にはこの動作を制御できる[オプション](/tex/{{lang.url-fragment}}net/other-options/#how-to-repeat-the-job)があります。

もう一つの必須部分は[ドキュメントクラス](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)です。ドキュメントクラスのファイルは、暗黙的に他のファイルに依存することがあり、これらも LaTeX の入力に含まれます。

基本的な LaTeX とそのドキュメントクラスの範囲を超える機能を使用したい場合、そしてそれが特定の TeX エンジン実装でサポートされている場合、通常はパッケージを使用します。パッケージは、プレアンブルでエンジンに通知する必要があります。*LaTeX パッケージ* は、1 つの名前の下にまとめられたファイル（またはファイル群）で、これらの機能を提供します。エンジンに通知するには、パッケージ名とオプション（パッケージが定義していれば）を指定して `\usepackage` コマンドを使用します。

```tex
\usepackage[a6paper,landscape]{geometry}
```

`\input`、`\openin`、`\read`、`\closein` プリミティブは禁止されているわけではありませんが、これらもパッケージで使用するのが最適です。したがって、独自のカスタムパッケージを開発している場合は、そちらで使用する方が良いでしょう。

入力の他の部分は任意であり、一般的な[TeX 入力](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) の概念に従い、あなたの TeX ファイル（プログラム）が具体的に何をすべきか、どのパッケージを使用しているかなどに依存します。
