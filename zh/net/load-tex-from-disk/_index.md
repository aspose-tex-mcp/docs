---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: 从磁盘加载 TeX | .NET API 解决方案 | Aspose API 解决方案
url: /net/load-tex-from-disk/
description: ".NET API 解决方案与 TeX 一起工作。通过示例了解如何使用几行 C# 代码从磁盘加载 TeX 文件。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 从磁盘加载 TeX 源文件
h2: ".NET API 解决方案从磁盘加载 TeX/LaTeX 文件"
---

{{<section overview>}}
---
p1: "TeX 被称为排版语言。这意味着您不对文档中的文本进行格式化，而是将纯文本与命令一起输入。作为输出，您将获得所需(指定)格式的格式化文件。 [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) 是出版集系统(计算机排版)的核心。 TeX 作业在明确指定的 TeX 文件上运行。要进一步了解 TeX 输入和输出，请学习文档的 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/)。"
p2: "众所周知，TeX 的主要目的是帮助创建数学或技术文本写作。但在进行任何操作之前，应首先加载文件。在这里，您将找到代码片段，解释如何使用文件系统目录从磁盘加载 TeX 源文件进行输入和输出，输出到 XPS 设备，将终端输出写入控制台。"
p3: "要运行我们需要的示例："
p4: "Aspose.TeX for .NET API 是一个功能丰富、功能强大且易于使用的 C# 平台文档操作和转换 API。"
p5: "打开 NuGet 包管理器，搜索 Aspose.TeX 并安装。您也可以从包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: 从磁盘 C# 加载 TeX 的步骤。
h3: "用于加载 TeX 的 C# 代码"
item1: "使用 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 的 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 类。"
item2: "为输入指定文件系统工作目录。为此使用 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 类。"
item3: "使用 [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 类为输出指定文件系统工作目录。"
item4: "使用 [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) 类将控制台指定为输出终端。"
item5: "如果需要，将内存终端指定为输出终端。为此使用 [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) 类。"
item6: "运行作业 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 方法 [*XpsDevice*](https://reference.aspose.com/tex/网/aspose.tex.presentation.xps/xpsdevice/)。"
item7: 细化输出。
---