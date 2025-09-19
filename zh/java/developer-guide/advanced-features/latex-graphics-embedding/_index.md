---
translation: true
template: /templates/_template-java.md
title: 乳胶嵌入式图形| Java的Aspose.TeX
linktitle: 乳胶嵌入式图形
weight: 18
url: /java/latex-graphics-embedding/
keywords: 包括图乳胶，乳胶嵌入base64图形，乳胶base64编码图形，write18，shell-escape，latex shell命令
description: 在本文中，您将探讨如何在乳胶源代码中注入基本64编码的图像，并了解使此功能的\ Write18功能。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 包括图像的另一种方法


935 / 5,000
某些 TeX/LaTeX 系统允许包含并非存储在 LaTeX 文件外部的图像；相反，这些图像直接嵌入到 LaTeX 文件中。然而，由于 TeX/LaTeX 文件是纯文本，无法包含二进制数据，因此我们需要一种以文本格式表示二进制数据的方法。这意味着必须将二进制数据编码成文本表示形式。挑战在于 TeX 引擎无法直接解释这些编码的图像。最终，可以使用 `graphicx` 包中众所周知的 `\includegraphics` 命令来包含图像，但该命令仅限于处理外部图像文件。因此，仍然必须在 LaTeX 文件外部创建外部图像文件（以及一个额外的中间文件），但这只会在排版过程中发生。这样做的好处是，您只需分发 LaTeX 文件本身，而无需分发一组文件。

好吧，假设我们以某种方式嵌入了乳胶文件中的编码图像。我们如何解码此图像？不幸的是，我们无法通过从乳胶文件中读取它并将其写入外部图像文件来直接解码它。相反，代表编码图像的文本字符串必须首先写入外部文本文件，然后可以解码以生成图像文件。

在这一点上，我们可以概述以下步骤以实现预期的结果：

1. 编码图像。
2. 将代表图像数据的文本字符串插入到乳胶文件中。
3. 将代表图像数据的文本字符串写入外部文件。
4. 解码步骤3中创建的外部文件。
5. 包括解码图像。

前两个步骤由乳胶文件的作者进行。当然，只要正确指示，Tex发动机就会处理其余步骤。

让我们继续前进**步骤1**。我们如何编码图像以获取字符串？这样做的方法之一(可能是最受欢迎的)是**base64**。

## 使用base64编码二进制数据

[**base64**](https://en.wikipedia.org/wiki/Base64)是一组二进制编码方案，使用一组64个独特的字符将二进制数据转换为一系列可打印字符。具体而言，源二进制数据以6个位的组进行处理，每组映射到64个独特字符之一。像所有二进制到文本编码方案一样，base64旨在促进以二进制格式存储的数据的传输，而不是主要支持文本内容的通道。

此简短说明表明**base64**正是我们所需要的。要将图像文件编码为**base64**，您可以使用命令行实用程序(如果在操作系统上可用)，几乎每种编程语言的标准或第三方功能，或[Base64.guru](https://base64.guru/converter/encode/file)或类似的在线工具。

## 将编码的图像嵌入到乳胶文件中

从编码过程中生成的字符串必须放在标准乳胶`filecontents`乳胶文件的序言中''中，如下所示：

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

这里是！ **步骤2**已完成。我们已经成功地将图像嵌入了乳胶文件中！但是，当我们用乳胶运行该文件的排版时会发生什么？”
乳胶处理器将将来自环境的字符串写入名为`sample-image.64`的外部文件。由于具有`overwrite`选项，因此如果文件已经存在，则将覆盖该文件(例如，如果该文件是在上一个运行中创建的)。这就是**步骤3**的方式！

## 解码base64字符串

**步骤4**是我们计划的差异在其中发挥作用的地方。解码base64字符串是通过更常见的事物(称为\ write18`功能)执行的。

### `\ write18`

在经典的 TeX 引擎中，`\write<number>(<token list>)` 是用于写入 *token 列表* 的原语。使用时，此原语后跟一个整数。如果整数为负数，则将 token 写入记录（日志）文件。如果整数大于 `15`，则将 token 发送到终端。如果整数在 `0..15` 范围内，则将 token 写入一个文件，该文件的名称由 `\openout` 原语的前面出现指定。`\openout<4 位整数>=<file name>` 原语将文件名与数字关联。

较新的 TeX 实现（例如 PDF TeX）允许使用 `\write18`。在这种情况下，它们将 `<token list>` 解释为要在操作系统 shell 中执行的命令行。由于此功能显然存在潜在的安全风险，因此每当在 TeX 相关文档或互联网上引用它时，您可能会感到一丝神秘。因此，PDF TeX/LaTeX 可执行文件提供了命令选项来控制对此功能的访问。

通常，有三个级别的可访问性：禁用，受限制启用并完全启用。

在 **Aspose.TeX** 中，有一个名为 `ShellMode` 的 TeX 作业选项，它可以采用以下两个值之一：`NoShellEscape` 和 `ShellRestricted`。`NoShellEscape` 值表示该功能已禁用。后者表示任何需要执行的命令都必须由用户作为 `Executable` 类的扩展来实现。我们在此不讨论此类实现的细节，但需要注意的是，`base64` 命令模拟已在 Aspose.TeX 中实现，并且默认包含在 `TeXOptions` 类实例的 `Executables` 集合属性中。

### 解码base64编码数据

为了解码预期包含base64编码数据的文件的内容，我们通常会使用以下命令行：


```
base64 -d  FILE1 > FILE2
```

其中 FILE1 是“编码”文件，并且 `> FILE2` 将输出重定向到文件 `FILE2`。

因此，我们应该在乳胶文件的正文中包括以下行：


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> 需要使用 `\immediate` 前缀，以确保 TeX 扫描器遇到此原语时立即执行 `\write` 操作。否则，它将在页面输出过程中进行处理。

如果现在运行文件的排版，我们会发现已创建了图像文件`sample-image.png`。继续并在观众检查中打开它！

## 包括解码图像

正如我们在文章开头指出的那样，要包括解码图像，我们使用众所周知的乳胶命令`\includegraphics`：


```tex
\includegraphics[options]{sample-image.png}
```

因此，完整的(几乎)乳胶文件可能显示如下：


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

使用**Aspose.TeX** API的Java代码类似于其他文章中可以找到的，除了指定Shell Mode选项外：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.java" >}}

现在**步骤5**已完成。有关真正的全面示例，请探索我们的[示例项目](https://github.com/aspose-tex/Aspose.TeX-for-Java)。

**您还可以查看基于[Aspose.TeX for .NET api](https://products.aspose.com/tex/net/)的免费转换[Web应用](https://products.aspose.app/tex/conversion/latex/)。**