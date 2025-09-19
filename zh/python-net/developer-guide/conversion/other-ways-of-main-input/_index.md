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

到目前为止，我们只学会了如何将[主输入文件](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)作为文件名提供给Tex引擎，无论是完整的形式还是以缩短形式，有或没有扩展名。但是，[Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob)类中可用[另一个构造函数](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions)接受流作为第一个参数。如果出于某种原因，主输入文件不在磁盘文件系统上的文件形式。这是如何实现它的示例：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

请注意，所有输出文件将命名为“ Texput”。这是因为该引擎无法访问任何其他名称。 `texput`是默认的作业名称。您可以找到有关作业名称[TEX输出](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)和[如何设置作业名称](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name)段落的更多详细信息。

## 通过终端输入主Tex输入文件

[Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob)类中有[另一个构造函数](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions)，它根本不允许我们指定输入。您可能想知道这样的Tex工作会发生什么。在这种情况下，我们需要使用输入终端。 TEX引擎将提示我们从终端输入文件名。

这是代码：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

运行后，引擎将暂停并等待我们输入文件名(有或没有路径，以及或不带扩展名)：


![终端窗口](/tex/images/python-net/.png)

这是输出终端(控制台)上显示的方式：

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```