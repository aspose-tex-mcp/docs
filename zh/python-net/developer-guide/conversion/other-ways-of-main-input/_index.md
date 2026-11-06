---
translation: true
template: /templates/_template-python-net.md
title: 提供主Tex输入文件的替代方法| 通过 .NET 为 Python 提供 Aspose.TeX
linktitle: 提供主Tex输入文件的其他方法
weight: 14
url: /python-net/other-ways-of-main-input/
description: Python的Aspose.TeX API解决方案包括一个接受流作为第一个参数的构造函数，提供了转换功能。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 使用流向Tex发动机提供主要输入文件

到目前为止，我们只学会了如何将[主输入文件](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)作为文件名提供给Tex引擎，无论是完整的形式还是以缩短形式，有或没有扩展名。但是，[Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/)类中可用[另一个构造函数](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions)接受流作为第一个参数。如果出于某种原因，主输入文件不在磁盘文件系统上的文件形式。这是如何实现它的示例：

将 `ASPOSE_TEX_OUTPUT_DIR` 设置为输出目录（默认 `output`）。请先应用许可证。 [Licensing](/tex/zh/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

将完整的 LaTeX 文档编码为二进制 `BytesIO` 流，传给使用 `TeXConfig.object_latex` 的 `TeXJob`。作业期间保持流打开。输出为 `texput.xps` 和 `texput.log`。

请注意，所有输出文件将命名为“ Texput”。这是因为该引擎无法访问任何其他名称。 `texput`是默认的作业名称。您可以找到有关作业名称[TEX输出](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)和[如何设置作业名称](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name)段落的更多详细信息。

## 通过终端输入主Tex输入文件

[Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/)类中有[另一个构造函数](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions)，它根本不允许我们指定输入。您可能想知道这样的Tex工作会发生什么。在这种情况下，我们需要使用输入终端。 TEX引擎将提示我们从终端输入文件名。

这是代码：

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

将以下 plain TeX 文本保存为 `hello-world.tex`，放在 `ASPOSE_TEX_INPUT_DIR` 中（默认 `input`）。示例使用 `TeXConfig.object_tex()`。出现提示时输入 `hello-world.tex` 并按 Enter，或通过标准输入提供文件名。输出为 `hello-world.xps` 和 `hello-world.log`。

```tex
Hello, World!
\end
```
