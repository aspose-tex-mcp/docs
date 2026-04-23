---
translation: true
template: /templates/_template-net.md
title: 提供主 TeX 输入文件的其他方式 | .NET
linktitle: 提供主 TeX 输入文件的其他方式
weight: 14
url: /net/other-ways-of-main-input/
description: Aspose.TeX API 解决方案 for .NET 的转换功能提供了一个接受流作为第一个参数的构造函数。这儿有一些代码示例。
lastmod: "2026-04-22"
---

{{<section overview>}}

## 将主输入文件作为流提供给 TeX 引擎

到目前为止，我们只知道如何将[主输入文件](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)以文件名的形式传递给 TeX 引擎，无论是完整路径还是简写形式，无论是否带扩展名。但还有另一个[构造函数](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) `TeXJob` 类，它接受一个流作为第一个参数。如果因某种原因我们拥有的主输入文件不是磁盘文件系统中的文件，这将非常方便。下面是实现方式：

{{< gist "aspose-com-gists" "4e3bae6ecbe041bcb411e0cf4c98dc71" "Example-StreamInput-LaTeX.cs" >}}

需要注意的是，所有输出文件的名称都会是 *texput*。因为引擎在任何地方都无法获取其他名称。*texput* 是默认的作业名称。[这里](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)和[这里](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name)提供了有关作业名称的详细信息。

## 从终端输入主 TeX 输入文件

还有另一个[构造函数](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) `TeXJob` 类，它根本不允许我们指定输入。那么这样一个 TeX 作业会处理什么呢？你可能会好奇。这一次我们需要一个输入终端。TeX 引擎会要求我们从终端输入文件名。

下面是代码示例：

{{< gist "aspose-com-gists" "4e3bae6ecbe041bcb411e0cf4c98dc71" "Example-MainInputTerminal.cs" >}}

一运行它，引擎就会卡住，等待我们输入文件名（可以带路径，也可以不带，带扩展名或不带）：

![终端窗口](/tex/images/net/Conversion-MainInputTerminal.png)

这就是在输出终端（控制台）上的显示效果：

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
