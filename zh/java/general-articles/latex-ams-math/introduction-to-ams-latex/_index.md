---
translation: true
template: /templates/_template-java.md
linktitle: AMS-LATEX
title: 1. AMS-LATEX 介绍
weight: 10
url: /java/introduction-to-ams-latex/
keywords: ams-latex, amsmath, amsmath options, amsopn, amstext, amscd, amsthm, amsxtra, upref
description: 本文简要介绍 amsmath 包，并简要概述其选项以及可用的子包和扩展包。
lastmod: "2026-02-19"
---

{{<section overview>}}


*AMS*-LATEX 1.0 版于 1990 年发布，首次将 Michael Spivak 的 *AMS*-TEX 中的数学功能转换为 LaTeX，工作由 Frank Mittelbach 与 Rainer Schopf 完成，他们在 *AMS* 担任顾问，并得到 *AMS* 技术人员 Michael Downes 的协助。1994 年，David M. Jones 继续了该工作。

*Amsmath* 包接受一些选项，主要影响各种数学运算符的 *limits* 位置或公式标签（编号）的放置方式。

## 可用的 *amsmath* 包选项

以下三个选项可作为全局文档选项（在 `\documentclass` 命令中指定）或在使用 `\usepackage` 加载 *amsmath* 包时作为包选项使用。

|||
|---|---|
| `reqno` **(default)** | 将公式编号（标签）放在右侧。 |
| `leqno` | 将公式编号（标签）放在左侧（默认，当使用 *AMS*-LATEX 文档类时）。 |
| `fleqn` | 将公式相对于左边距固定缩进，而不是在文本列中居中。 |

## 可用的子包

在 *AMS*-LATEX 发行版中，还可以找到可通过 `\usepackage` 命令独立加载的组件。以下较小的包提供了 *amsmath* 包的部分功能：

|||
|---|---|
| `amsopn` | 提供 `\DeclareMathOperator` 用于定义新运算符名称，如 `\Ker` 和 `\esssup`。 |
| `amstext` | 提供 `\text` 命令用于在正确的字体大小中排版文本片段。 |

## 扩展包

以下列出的包提供了额外的功能，必须显式加载。

|||
|---|---|
| `amscd` | 定义一些命令，使生成交换图更容易。 |
| `amsthm` | 提供声明类似定理结构的方法，并提供 `proof` 环境。 |
| `amsxtra` | 提供一些为历史兼容性所需的零碎功能，例如 `\fracwithdelims`、`\accentedsymbol`，以及将重音符号放置为上标的命令。 |
| `upref` | 使 `\ref` 在任何上下文中都以正体/罗马字体打印交叉引用编号。 |
