---
translation: true
template: /templates/_template-java.md
linktitle: フォント選択スキーム
title: LaTeX フォント選択スキーム | Aspose.TeX チュートリアル
weight: 60
url: /java/latex-font-selection/
keywords: latex、latex フォント、latex フォント選択、nfss
description: この記事では、文書処理における LaTeX フォントの使用について簡単に説明します。また、TeX フォントのメトリクスと文字形状についても説明します。
lastmod: "2026-02-28"
---

{{<section overview>}}

ソース文書を処理する際、LaTeX タイポグラフィシステムは使用しているフォントについてあまり情報を持ちません。文字の形状を知る必要はなく、文字の位置だけを計算します。最も重要な情報は文字の *ブラックボックス* であり、幅・高さ・深さで定義されます。これらの寸法は、各フォントに対して `.tfm`（TeX フォントメトリック）という拡張子の外部ファイルに別途保存されています。

文字の形状は後の段階で利用されます。LaTeX システムが `.dvi` ファイルを生成する場合、*ドライバ* プログラムが `.dvi` ファイルの文字配置データと、`.pk` ファイルやアウトライン記述（たとえば PostScript）から得られる文字形状情報を組み合わせて、出力媒体上に文字画像を生成します。しかし、**PDF TeX** や **VTEX** のような他の LaTeX システムは `.dvi` ファイルの生成を省き、直接 **PDF** や **PostScript** 出力を生成します。その場合、文字形状は対応するフォーマッタが最終出力を作成する際に埋め込まれます。
