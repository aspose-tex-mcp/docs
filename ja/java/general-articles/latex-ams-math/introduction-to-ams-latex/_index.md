---
translation: true
template: /templates/_template-java.md
linktitle: AMS-LATEX
title: 1. AMS-LATEX の紹介
weight: 10
url: /java/introduction-to-ams-latex/
keywords: ams-latex, amsmath, amsmath options, amsopn, amstext, amscd, amsthm, amsxtra, upref
description: この記事は amsmath パッケージの簡単な紹介であり、そのオプションや利用可能なサブパッケージ、拡張機能について簡潔に説明します。
lastmod: "2026-02-19"
---

{{<section overview>}}


*AMS*-LATEX バージョン 1.0 は 1990 年にリリースされ、Michael Spivak の *AMS*-TEX の数式機能を LaTeX に初めて変換した機能を Frank Mittelbach と Rainer Schopf が提供しました。彼らは *AMS* のコンサルタントとして活動し、*AMS* 技術スタッフの Michael Downes の協力を得ていました。1994 年には、David M. Jones と共にさらなる作業が行われました。

*Amsmath* パッケージは、主に様々な数式演算子の *limits* の位置や方程式タグの位置に影響を与えるいくつかのオプションを受け入れます。

## 利用可能な *amsmath* パッケージオプション

以下の3つのオプションは、グローバルドキュメントオプション（`\documentclass` コマンドで指定）として、または `\usepackage` コマンドでロードされた *amsmath* パッケージオプションとして使用できます。

|||
|---|---|
| `reqno` **(default)** | 式番号（タグ）を右側に配置します。 |
| `leqno` | 式番号（タグ）を左側に配置します（*AMS*-LATEX 文書クラスを使用する場合のデフォルト）。 |
| `fleqn` | 式を左余白から固定されたインデントで配置し、テキスト列の中央に置かないようにします。 |

## 利用可能なサブパッケージ

*AMS*-LATEX ディストリビューションには、`\usepackage` コマンドで独立してロードできるコンポーネントも含まれています。以下の小さなパッケージは、*amsmath* パッケージの一部の機能を提供します。

|||
|---|---|
| `amsopn` | `\DeclareMathOperator` を提供し、`\Ker` や `\esssup` などの新しい演算子名を定義できます。 |
| `amstext` | `\text` コマンドを提供し、正しいサイズでテキストの断片を組版できます。 |

## 拡張パッケージ

The packages listed below provide additional features and must be loaded explicitly.

|||
|---|---|
| `amscd` | 可換図式を生成しやすくするいくつかのコマンドを定義します。 |
| `amsthm` | 定理類似の構造を宣言する方法を提供し、`proof` 環境を提供します。 |
| `amsxtra` | `\fracwithdelims`、`\accentedsymbol`、アクセントを上付き文字として配置するコマンドなど、歴史的互換性のために必要な様々な機能を提供します。 |
| `upref` | `\ref` が文脈に関係なく立体/ローマン体で相互参照番号を表示するようにします。 |
