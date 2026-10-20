---
translation: true
template: /templates/_template-net.md
title: LaTeX 嵌入图形 | Aspose.TeX for .NET
linktitle: LaTeX 嵌入图形
weight: 18	
url: /net/latex-embedded-graphics/
keywords: 包含图形 LaTeX、LaTeX 嵌入 Base64 图形、LaTeX Base64 编码图形、write18、shell 转义、LaTeX shell 命令
description: 本文介绍了如何在 LaTeX 源代码中包含 Base64 编码的图像，以及实现此功能的 \write18 功能。
lastmod: "2026-04-03"
---

{{<section overview>}}

## 另一种包含图像的方法

某些 TeX/LaTeX 系统允许将图像直接包含在 LaTeX 文件本身中，而不是外部存储。然而，由于 TeX/LaTeX 文件是纯文本文件，不能包含二进制数据，我们需要一种方式将二进制数据以文本形式表示。换句话说，二进制数据必须编码为某种文本表示。问题在于 TeX 引擎无法直接解释这种编码后的图像。实际上，插入图像是通过 `graphicx` 包中的老式 `\includegraphics` 命令完成的。但该命令只能处理外部图像文件。是的，外部图像文件（以及另一个中间文件）仍会在 LaTeX 文件之外生成。关键在于您只需要分发单独的 LaTeX 文件。

好的，假设我们已经在 LaTeX 文件中放置了编码图像。那么我们如何解码该图像呢？遗憾的是，不能直接从 LaTeX 文件读取并写入外部图像文件来解码。表示编码图像的文本字符串必须首先写入一个外部文本文件，然后才能解码生成图像文件。

现在，我们可以概括出以下步骤来实现目标：

1. 编码图像。  
2. 将表示图像数据的文本字符串注入到 LaTeX 文件中。  
3. 将该文本字符串输出到外部文件。  
4. 解码第 3 步生成的外部文件。  
5. 包含已解码的图像。

前两步由 LaTeX 文件的作者完成。其余步骤由 TeX 引擎在正确指示的情况下完成。

让我们从最开始说起。如何将图像编码为字符字符串？一种常用且最流行的方法是 **Base64**。

## 使用 Base64 编码二进制数据

[**Base64**](https://en.wikipedia.org/wiki/Base64) 是一组二进制转文本的编码方案，可将二进制数据转换为可打印字符序列，字符集合限定为 64 个唯一字符。更具体地说，源二进制数据一次取 6 位，然后将这 6 位映射到 64 个唯一字符中的一个。和所有二进制转文本编码方案一样，**Base64** 旨在在仅可靠支持文本内容的通道中传输二进制格式的数据。

从上述简短说明可以看出 **Base64** 正是我们需要的。要将图像文件编码为 **Base64**，您可以使用命令行工具（如果系统上可用）、几乎所有编程语言的标准或第三方功能，或在线工具，例如 [Base64.guru](https://base64.guru/converter/encode/file) 等。

## 将编码图像放入 LaTeX 文件

您获得的字符字符串需要放在 LaTeX 文件前导区的标准 `filecontents` 环境中，示例如下：


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

至此第 2 步已经完成，图像已经嵌入到 LaTeX 文件中！但是在实际排版时会发生什么？

LaTeX 处理器会把环境中的字符字符串写入一个名为 `sample-image.64` 的外部文件。由于使用了 `overwrite` 选项，如果该文件已存在（例如之前的运行产生的），会被覆盖。这也同时完成了第 3 步。

## 解码 base64 字符串

第 4 步是不同 TeX 实现之间差异出现的地方。解码 Base64 字符串通常通过 `\write18` 功能实现。

### `\write18`

在经典 TeX 引擎中，`\write<number>(<token list>)` 是写入 *标记列表* 的原语。使用时，需要在后面跟一个整数。如果该数为负，则标记写入记录（日志）文件；如果大于 `15`，则写入终端；如果在 `0..15` 范围内，则写入由前面的 `\openout` 原语指定的文件。`\openout<4-bit integer>=<file name>` 原语将文件名映射到一个数字。

较新的 TeX 实现（如 PDF TeX）允许使用 `\write18`。此时，它将 `<token list>` 解释为要在操作系统 shell 中执行的命令行。由于此功能显然可能成为后门，在 TeX 相关文档或网络上提及时常会让人联想到神秘感。因此，PDF TeX/LaTeX 可执行文件提供了用于管理该功能可访问性的命令选项。

一般而言，有三种可访问性级别：禁用、受限启用和完全启用。

在 **Aspose.TeX** 中，有一个 TeX 作业选项叫 `ShellMode`，但仅有两个可用值：`NoShellEscape` 和 `ShellRestricted`。`NoShellEscape` 表示该功能被禁用。`ShellRestricted` 表示任何需要执行的命令都必须由用户通过实现 `Executable` 类的扩展来完成。这里我们不深入介绍这些实现细节，只说明 `base64` 命令的模拟已在 Aspose.TeX 中实现。默认情况下，您可以在 `TeXOptions` 类实例的 `Executables` 集合属性中找到其原型实例。

### 解码 Base64 编码的数据

要解码包含 Base64 编码数据的文件，通常使用以下命令行：


```
base64 -d  FILE1 > FILE2
```

其中 `FILE1` 为“编码”文件，`> FILE2` 表示将输出重定向到 `FILE2`。

因此，在 LaTeX 文件主体中应添加如下行：


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> `\immediate` 前缀是必需的，以确保在 TeX 扫描器遇到原语命令时立即执行 `\write` 操作。否则，它会在页面输出时才被处理。

如果现在运行文件的排版，您会看到 `sample-image.png` 图像文件被创建。快打开查看吧！

## 包含已解码的图像

正如文章开头所述，包含已解码图像使用的是熟知的 LaTeX 命令 `\includegraphics`：


```tex
\includegraphics[options]{sample-image.png}
```

于是，一个完整（几乎）符合要求的 LaTeX 文件可能如下所示：


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \write18{base64 -d  sample-image.64 > sample-image.png}
  \includegraphics[options]{sample-image.png}
\end{document}
```

对应的 C# 代码使用 **Aspose.TeX** API 与其他文章基本相同，只是多了 `ShellMode` 选项的指定：

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Examples_LaTeXEmbeddedBase64EncodedImage" >}}

至此，第 **5 步** 完成。想要获取更完整的示例，请浏览我们的 [Example project](https://github.com/aspose-tex/Aspose.TeX-for-.NET)。

**您也可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费转换 [web app](https://products.aspose.app/tex/conversion/latex/)。**
