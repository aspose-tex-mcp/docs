---
translation: true
template: /templates/_template-java.md
title: LaTeX 嵌入式图形 | Aspose.TeX for Java
linktitle: LaTeX 嵌入式图形
weight: 18	
url: /java/latex-graphics-embedding/
keywords: includegraphics latex, LaTeX 嵌入 base64 图形, LaTeX base64 编码图形, write18, shell-escape, LaTeX shell 命令
description: 在本文中，您将了解如何在 LaTeX 源代码中注入 Base64 编码的图像，并学习实现此功能的 \write18 特性。
lastmod: "2026-02-27"
---

{{<section overview>}}

## 包含图像的另一种方式

某些 TeX/LaTeX 系统允许将图像直接嵌入到 LaTeX 文件中，而不是相对于 LaTeX 文件本身存储在外部。但是，由于 TeX/LaTeX 文件是纯文本，不能包含二进制数据，我们需要一种方法将二进制数据以文本形式表示。这意味着二进制数据必须编码为文本表示。挑战在于 TeX 引擎无法直接解释这些编码后的图像。最终，图像仍然是通过 `graphicx` 包中的著名 `\includegraphics` 命令来包含的，但该命令仅限于处理外部图像文件。因此，仍需在 LaTeX 文件之外创建外部图像文件（以及一个中间文件），但这只会在排版时发生。优势在于您只需分发 LaTeX 文件本身，而不是一组文件。

好的，假设我们已经以某种方式在 LaTeX 文件中嵌入了编码的图像。我们该如何解码这幅图像？遗憾的是，不能直接从 LaTeX 文件读取并写入外部图像文件来解码。相反，表示编码图像的文本字符串必须首先写入外部文本文件，然后才能解码生成图像文件。

此时，我们可以概述以下步骤来实现期望的结果：

1. 编码图像。
2. 将表示图像数据的文本字符串插入到 LaTeX 文件中。
3. 将表示图像数据的文本字符串写入外部文件。
4. 解码步骤 3 中创建的外部文件。
5. 包含已解码的图像。

前两步由 LaTeX 文件的作者完成。其余步骤由 TeX 引擎处理，只要正确指示它即可。

让我们进入 **步骤 1**。我们如何对图像进行编码以获得字符字符串？最常用（也可能是最流行）的方法是 **Base64**。

## 使用 Base64 编码二进制数据

[**Base64**](https://en.wikipedia.org/wiki/Base64) 是一组二进制转文本的编码方案，将二进制数据转换为可打印字符序列，使用 64 个唯一字符。具体来说，源二进制数据按 6 位一组处理，每组映射到 64 个唯一字符中的一个。和所有二进制转文本编码方案一样，Base64 旨在促进在主要支持文本内容的通道上传输以二进制格式存储的数据。

这段简要说明表明 **Base64** 正是我们需要的。要将图像文件编码为 **Base64**，您可以使用命令行工具（如果您的操作系统提供），几乎所有编程语言的标准或第三方功能，或像 [Base64.guru](https://base64.guru/converter/encode/file) 之类的在线工具。

## 将编码的图像嵌入到 LaTeX 文件中

从编码过程生成的字符字符串必须放置在 LaTeX 标准的 `filecontents` 环境中，并置于 LaTeX 文件的导言区，如下所示：

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

就这样！**步骤 2** 完成。我们已经成功将图像嵌入到 LaTeX 文件中！但是，当我们使用 LaTeX 排版此文件时会发生什么？

LaTeX 处理器会将环境中的字符字符串写入名为 `sample-image.64` 的外部文件。由于使用了 `overwrite` 选项，如果文件已存在（例如在上一次运行时已创建），它将被覆盖。这就是 **步骤 3** 也随之完成的方式！

## 解码 Base64 字符串

我们的计划中 **步骤 4** 是 TeX 实现差异发挥作用的地方。解码 Base64 字符串是通过更常见的 `\write18` 特性实现的。

### `\write18`

在经典 TeX 引擎中，`\write<number>(<token list>)` 是用于写入 *令牌列表* 的原语。当使用时，需要在其后跟随一个整数。如果整数为负，则令牌写入转录（日志）文件；如果大于 `15`，则发送到终端；如果在 `0..15` 范围内，则写入由之前出现的 `\openout` 原语指定的文件。`\openout<4-bit integer>=<file name>` 原语将文件名与数字关联。

较新的 TeX 实现（例如 PDF TeX）允许使用 `\write18`。在这种情况下，它将 `<token list>` 解释为在操作系统 shell 中执行的命令行。由于此特性显然存在潜在的安全风险，在 TeX 相关文档或互联网上提及时，您可能会感到一丝神秘。因此，PDF TeX/LaTeX 可执行文件提供了控制对该特性访问的命令选项。

通常，有三种访问级别：禁用、受限启用和完全启用。

在 **Aspose.TeX** 中，有一个 TeX 作业选项叫做 `ShellMode`，它可以取两个可能的值：`NoShellEscape` 和 `ShellRestricted`。`NoShellEscape` 表示该特性被禁用。`ShellRestricted` 则意味着任何需要执行的命令必须由用户实现为 `Executable` 类的扩展。这里我们不详细讨论此类实现，但需要注意的是，`base64` 命令的模拟已经在 Aspose.TeX 中实现，并默认包含在 `TeXOptions` 类实例的 `Executables` 集合属性中。 内置的 `base64` 模拟在 Aspose.TeX 内部运行，不需要操作系统的 Base64 工具。

### 解码 Base64 编码的数据

要解码预期包含 Base64 编码数据的文件内容，通常使用以下命令行：

```
base64 -d  FILE1 > FILE2
```

其中 FILE1 为“已编码”文件，`> FILE2` 将输出重定向到 FILE2。

因此，我们应在 LaTeX 文件的主体中加入以下行：

```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> 必须使用 `\immediate` 前缀，以确保当 TeX 扫描器遇到此原语时立即执行 `\write` 操作。否则，它将在页面输出阶段才被处理。

如果现在排版此文件，您会发现图像文件 `sample-image.png` 已被创建。打开它查看即可！

## 包含已解码的图像

正如文章开头所述，要包含已解码的图像，我们使用广为人知的 LaTeX 命令 `\includegraphics`：

```tex
\includegraphics[options]{sample-image.png}
```

以下示例展示文档结构。请将缩短的 Base64 行替换为完整图像数据；省略点是占位符，无法解码：

```tex
\documentclass{article}
\usepackage{graphicx}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \immediate\write18{base64 -d sample-image.64 > sample-image.png}
  \includegraphics[width=\textwidth]{sample-image.png}
\end{document}
```

Java 示例将完整的 `embedded-base64-image.tex` 文档转换为 PDF。将 `inputFile` 设置为输入文件的完整路径，将 `outputDirectory` 设置为现有输出文件夹。导入所用的 `com.aspose.tex` 类、`com.aspose.tex.rendering.PdfDevice` 和 `com.aspose.tex.rendering.PdfSaveOptions`，处理或声明异常，并按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证。示例为内置 Base64 命令启用 `ShellRestricted`，以非交互方式处理，并将终端输出保存在内存中。PDF 设备和输出目录在作业完成后释放或关闭。输出文件夹包含 `sample-image.64`、解码后的 `sample-image.png`、PDF 和 TeX 日志：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-EmbeddedBase64Image.java" >}}

现在 **步骤 5** 完成。欲获取更完整的示例，请查看我们的 [示例项目](https://github.com/aspose-tex/Aspose.TeX-for-Java)。

**您还可以尝试基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费转换 [Web 应用](https://products.aspose.app/tex/conversion/latex/)。**
