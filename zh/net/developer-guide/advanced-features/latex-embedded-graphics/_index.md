---
translation: true
template: /templates/_template-net.md
title: 乳胶嵌入式图形| .NET的Aspose.TeX
linktitle: 乳胶嵌入式图形
weight: 18
url: /net/latex-embedded-graphics/
keywords: 包括图乳胶，乳胶嵌入base64图形，乳胶base64编码图形，write18，shell-escape，latex shell命令
description: 本文介绍了如何在乳胶源代码中包含基本64编码的图像，以及\ write18功能使得这是可能的。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 包括图像的另一种方法

某些TEX/乳胶系统允许包括相对于乳胶文件本身而在外部存储的图像，而是直接包含在乳胶文件中。但是，由于TEX/LATEX文件是纯文本文件，因此不能包含二进制数据，因此我们需要一种用文本形式表示二进制数据的方法。换句话说，二进制数据必须编码为某些文本表示。问题在于，Tex引擎无法直接解释此类编码的图像。实际上，使用`graphicx`软件包中的良好旧 `\includegraphics`命令来完成包括图像。但是，此命令只能处理外部图像文件。是的，外部图像文件(以及另一个中介文件)仍将在乳胶文件之外创建。关键点是您只需要单独分发乳胶文件即可。

好的，假设我们以某种方式将编码的图像放在乳胶文件中。但是，我们如何将图像解码呢？不幸的是，我们无法通过从乳胶文件中读取文件并将其写入外部图像文件来解码。代表编码图像的文本字符串必须首先写入外部文本文件，然后可以解码以产生图像文件。

到现在为止，我们可以概述以下步骤以获得所需的结果：

1. 编码图像。
2. 将代表图像数据的文本字符串注入到乳胶文件中。
3. 输出代表图像数据的文本字符串到外部文件。
4. 从步骤3解码外部文件。
5. 包括解码图像。

前两个步骤由乳胶文件的作者完成。当然，如果正确指示，Tex发动机将负责其余步骤。

让我们从一开始就开始。我们如何编码图像以获取字符串？这样做的方法之一(可能是最受欢迎的)是**base64**。

## 使用base64编码二进制数据

[**base64**](https://en.wikipedia.org/wiki/Base64)是一组二进制的编码方案，将二进制数据转换为一系列可打印字符，仅限于64个独特字符。更具体地说，源二进制数据一次是6位，然后将这组6位映射到64个独特字符之一。与所有二进制编码方案一样，**base64**旨在携带以二进制格式存储的数据，这些数据仅可靠地支持文本内容。

从这个简短的解释中，我们可以看到**base64**是我们所需要的。要将图像文件编码为**base64**，您可以使用命令行实用程序(如果在OS上可用)，几乎每种编程语言的标准或第三方功能，或[Base64.guru](https://base64.guru/converter/encode/file)或类似的在线工具。

## 将编码的图像放入乳胶文件中

您由于编码而获得的字符串必须放在标准乳胶``filecontents``乳胶文件序言中''中，如下所示：


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

这里是。步骤2已完成。我们在乳胶文件中有图像！但是，当我们使用乳胶运行该文件的排版时会发生什么？

乳胶处理器会将环境中的字符串写入名为“ sample-image.64”的外部文件。由于使用“ oftrite”选项，如果文件已经存在，将覆盖该文件(例如，如果由以前的运行产生)。这也是第3步！
## 解码base64字符串

我们计划的第4步是TEX实施中差异的地方。解码base64字符串是通过更常见的事物(称为\ write18`功能)完成的。

### `\ write18`

在经典的Tex发动机中，`\ write <数字>(<token list>)`是写下令牌 *列表 *的原始版本。使用时，此原始性后面是整数。如果此数字为负，则将令牌写入成绩单(日志)文件。如果数字大于15，则将令牌写入终端。如果数字在范围内`0..15`，则将令牌写入其名称的文件，该文件是由`\openOut`原始词的先前出现的。 `\openOUT <4-t-bit Integer> = <文件名>`原始映射到一个数字。

较新的Tex实施(例如PDF TEX)允许使用`\ write18`。在这种情况下，他们将`<token list>`将其解释为要在OS Shell中执行的命令行。由于此功能显然是一个潜在的后门，因此，每当与Tex相关文档或Internet上提到它时，您可能会感觉到神秘感。因此，PDF Tex/latex可执行文件具有管理此功能可访问性的命令选项。

通常，可访问性有三个级别：禁用，启用了限制并完全启用。

在**Aspose.TeX**中，有一个称为“ shellmode”的Tex作业选项，但是只有两个合适的值：`noshellescape'和``shellRenter`。 `nosheLlesCape`值表示该功能已禁用。第二个值表明必须执行任何需要执行的命令，用户必须实现“可执行”类的扩展。在这里，我们不会深入研究此类实现的详细信息，但是我们将提到`base64`命令仿真已经在aspose.tex中实现了。默认情况下，您可以在``texoptions``class实例的`ofutables`Collection属性中找到其原型实例。

### 解码base64编码数据

为了解码应该是某些Base64编码数据的文件的内容，我们通常会使用以下命令行：


```
base64 -d  FILE1 > FILE2
```

其中file1是“编码”文件，而`> file2`表示必须将输出重定向到文件`file2`。

因此，在我们的乳胶文件的正文中，我们应该添加以下行：


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> 需要使用 `\immediate` 前缀，以确保 TeX 扫描器遇到原始命令时立即执行 `\write` 操作。否则，它将在页面输出时进行处理。

如果现在运行文件的排版，我们将看到创建图像文件`sample-image.png`。来吧，在观众检查中打开它！

## 包括解码图像

正如我们在文章开头提到的，要包括解码图像，我们使用众所周知的乳胶命令`\includegraphics`：


```tex
\includegraphics[options]{sample-image.png}
```

因此，完整的(几乎)乳胶文件可能如下：


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

并且使用**Aspose.TeX** API与其他文章中的C＃代码相似，除了指定`shellmode`选项：

{{< gist "aspose-com-gists" "7f54d335270200ebf5987d071bad028a" "Examples_LaTeXEmbeddedBase64EncodedImage" >}}

现在，我们已经完成了**步骤5**。有关真正完整的示例，请探索我们的[示例项目](https://github.com/aspose-tex/Aspose.TeX-for-.NET)。

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费转换 [web 应用程序](https://products.aspose.app/tex/conversion/latex/)。**
