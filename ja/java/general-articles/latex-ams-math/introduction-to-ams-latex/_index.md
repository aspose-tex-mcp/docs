---
translation: true
template: /templates/_template-java.md
linktitle: AMS-Latex
title: 1。AMS-Latexの紹介
weight: 10
url: /java/introduction-to-ams-latex/
keywords: AMS-Latex、AMSMATH、AMSMATHオプション、AMSOPN、AMSTEXT、AMSCD、AMSTHM、AMSXTRA、UPREF
description: この記事は、AMSMATHパッケージの簡単な紹介であり、そのオプションと利用可能なサブパッケージと拡張機能を簡単に説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}


*AMS*-LATEX バージョン 1.0 は 1990 年にリリースされ、Michael Spivak の *AMS*-TEX の数式機能を LaTeX に変換する最初のツールとして、*AMS* のコンサルタントを務めていた Frank Mittelbach と Rainer Schopf が、*AMS* 技術スタッフの Michael Downes の協力を得て開発しました。1994 年には、David M. Jones と共にさらなる作業が行われました。

*Amsmath* パッケージは、主に様々な数式演算子の *limits* の位置や数式タグの位置に影響を与えるいくつかのオプションを受け入れます。

## 利用可能な *amsmath* パッケージオプション

以下の 3 つのオプションは、ドキュメント全体のオプション（`\documentclass` コマンドで指定）として、または `\usepackage` コマンドで読み込まれた *amsmath* パッケージオプションとして使用できます。

|||
|---|---|
| `reqno` **(デフォルト)** | 数式番号 (タグ) を右側に配置します。 |
| `leqno` | 数式番号 (タグ) を左側に配置します (デフォルト、*AMS*-LATEX 文書クラスを使用する場合)。 |
| `fleqn` | 数式をテキスト列の中央揃えではなく、左余白から固定インデントして配置します。 |

## 利用可能なサブパッケージ

*AMS*-LATEX分布では、`\usepackage`コマンドによって個別にロードできるコンポーネントを見つけることもできます。次の小さなパッケージは、 *amsmath*パッケージのいくつかの機能を提供します。

|||
|---|---|
| `amsopn` | `\Ker` や `\esssup` などの新しい演算子名を定義するための `\DeclareMathOperator` を提供します。|
| `amstext` | テキストの一部を正しいサイズでタイプセットするための `\text` コマンドを提供します。|

## 拡張パッケージ

以下にリストされているパッケージは追加機能を提供し、明示的にロードする必要があります。
|||
|---|---|
| `amscd` | 可換図を簡単に生成するためのコマンドをいくつか定義します。 |
| `amsthm` | 定理のような構造を宣言する方法を提供し、`proof` 環境を提供します。 |
| `amsxtra` | `\fracwithdelims`、`\accentedsymbol`、アクセントを上付き文字として配置するコマンドなど、歴史的な互換性のために必要ないくつかの追加機能を提供します。 |
| `upref` | `\ref` がコンテキストに関係なく直立/ローマンフォントで相互参照番号を印刷するようにします。 |