---
translation: true
template: /templates/_template-java.md
linktitle: AMS-LATEX
title: 1. AMS-LATEX简介|乳胶手册
weight: 10
url: /java/introduction-to-ams-latex/
keywords: AMS-LATEX，AMSMATH，AMSMATH选项，AMSOPN，AMSTEXT，AMSCD，AMSTHM，AMSXTRA，UPREF
description: 本文简要介绍了AMSMATH软件包，并简要介绍其选项以及可用的子包和扩展。
lastmod: "2025-06-10"
---

{{<section overview>}}


*AMS*-latex版本1.0于1990年发行，并在Michael Spivak的*AMS*-Tex中介绍了乳胶的原始转换，由Frank Mittelbach和Rainer Schopf在*AMS*Tech员工的Michael Downes的帮助下，曾担任*AMS*的顾问。 1994年，戴维·M·琼斯(David M. Jones)进行了进一步的工作。

* amsmath*软件包接受一些选项，这些选项主要影响在各种数学运算符或方程式标签的位置上*限制*的位置。

## 可用 * amsmath *软件包选项

以下三个选项可以用作全局文档选项(在`\documentclass`命令中指定)或使用`\usepackage`命令加载时 * amsmath * package选项。

|||
|---|---|
| `reqno` **（默认）** | 将公式编号（标签）放在右侧。|
| `leqno` | 将公式编号（标签）放在左侧（使用 *AMS*-LATEX 文档类时的默认设置）。|
| `fleqn` | 将公式放置在距左边距固定缩进的位置，而不是文本列的中央。|

## 可用的子包

在 *AMS *-LATEX分发中，您还可以找到可以由`\usepackage`命令独立加载的组件。以下较小的软件包提供了 * amsmath *软件包的某些功能：

|||
|---|---|
| `amsopn` | 提供 `\DeclareMathOperator` 用于定义新的运算符名称，例如 `\Ker` 和 `\esssup`。|
| `amstext` | 提供 `\text` 命令，用于以正确的字体大小排版一段文本。|

## 扩展程序包

下面列出的软件包提供了其他功能，必须明确加载。
|||
|---|---|
| `amscd` | 定义一些命令以便更轻松地生成交换图。|
| `amsthm` | 提供一种声明类定理结构的方法，并提供 `proof` 环境。|
| `amsxtra` | 提供一些历史兼容性所需的零碎功能，例如 `\fracwithdelims`、`\accentedsymbol` 以及将重音符号设置为上标的命令。|
| `upref` | 使 `\ref` 以直立/罗马字体打印交叉引用编号，而不管上下文如何。|