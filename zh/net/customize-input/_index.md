---
translation: true
template: /_templates/_customize-input-net.md
title: 创建自定义输入 TeX | .NET API 解决方案
url: /net/customize-input/
description: ".NET API 解决方案与 TeX 一起工作。通过示例了解如何使用几行 C# 代码为 TeX 文件创建自定义输入。"
keywords: 自定义输入tex net api, C# api 自定义tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 自定义输入
h2: ".NET API 解决方案来自定义 TeX 文件的输入"
---

{{<section overview>}}
---
p1: "TeX 被称为排版语言。这意味着您不对文档中的文本进行格式化，而是将纯文本与命令一起输入。正如文档的文章 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 中所述，TeX 作业在明确指定的 TeX 文件上运行。因此，我们将这个文件包含在某个 TeX 作业的输入中。"
p2: "在此页面上，您将找到一个代码示例，说明如何自定义 TeX 源文件的输入，同时考虑到输入应遵循 TeX 语法，并且理想情况下，仅包含引擎已知的命令。"
p3: "要自定义 .tex 文件输入，我们需要："
p4: "Aspose.TeX for .NET API 是一个功能丰富、功能强大且易于使用的 C# 平台文档操作和转换 API。"
p5: "打开 NuGet 包管理器，搜索 Aspose.TeX 并安装。您也可以从包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: "自定义 TeX 输入 C# 的步骤："
h3: "用于 TeX 输入自定义的 C# 代码"
item1: "使用 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 的方法 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 类，在 ObjectTeX 引擎扩展上创建无格式的 TeX 引擎选项。"
item2: "使用 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 类，为输入指定一个文件系统工作目录。"
item3: "借助 [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) 方法，创建自定义格式。"
---