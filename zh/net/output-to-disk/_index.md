---
translation: true
template: /_templates/_output-to-disk-net.md
title: 将 TeX 输出写入磁盘 | .NET API 解决方案
url: /net/output-to-disk/
description: ".NET API 解决方案与 TeX 一起工作。通过示例了解如何使用几行 C# 代码为 TeX 文件创建自定义输出。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 将 TeX 输出写入磁盘
h2: "通过 C# .NET 将 TeX 文件转换的结果保存为磁盘"
---

{{<section overview>}}
---
p1: "TeX 被称为排版语言，这意味着您无需格式化文档中的文本，而是输入纯文本和命令。从文档的文章 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 中得知，TeX 作业在明确指定的 TeX 文件上运行。在那里，您还可以找到有关 TeX 交互模式和与 TeX 输入和输出相关的原语的信息。"
p2: "TeX 的主要用途是帮助创建数学或技术文本写作。但是当文件已经创建并且您不希望对其进行任何进一步的操作时，您可能希望将其转换为不同的、更流行的格式。"
p3: "在此页面上，您将找到一个代码示例，解释使用文件系统目录进行输入和输出、输出到 XPS 设备、覆盖作业名称、将终端输出写入磁盘。简而言之，它是一种将输出写入磁盘的转换。要运行这样的操作，我们需要："
p4: "Aspose.TeX for .NET API 是一个功能丰富、功能强大且易于使用的 C# 平台文档操作和转换 API。"
p5: "打开 NuGet 包管理器，搜索 Aspose.TeX 并安装。您也可以从包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: "将终端输出写入磁盘 C# 的步骤："
h3: "用于转换 TeX 并将输出写入磁盘的 C# 代码"
item1: "使用 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 的 [*TeXOptions*](https://) 方法在 ObjectTeX 引擎扩展上创建转换选项参考.aspose.com/tex/net/aspose.tex/texoptions/) 类。"
item2: "如果您不希望将 TeXJob 构造函数的第一个参数作为作业名称，请指定作业名称。"
item3: "为输入指定文件系统工作目录。为此使用 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 类。"
item4: "借助 [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 类的实体为输出指定文件系统工作目录。"
item5: "指定必须将终端输出写入输出工作目录中的文件。"
item6: "运行作业 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 方法 [*XpsDevice*](https://reference.aspose.com/tex/网/aspose.tex.presentation.xps/xpsdevice/)。"
---