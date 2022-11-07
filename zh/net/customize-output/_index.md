---
translation: true
template: /_templates/_customize-output-net.md
title: 创建自定义输出 TeX | .NET API 解决方案
url: /net/customize-output/
description: ".NET API 解决方案与 TeX 一起工作。阅读示例如何使用几行 C# 代码为 TeX 文件创建自定义输出。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 自定义输出
h2: ".NET API 解决方案来自定义 TeX 文件的输出"
---

{{<section overview>}}
---
p1: "TeX 被称为排版语言。这意味着您不对文档中的文本进行格式化，而是将纯文本与命令一起输入。"
p2: "文档的文章 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 告诉我们，TeX 文件可能不包含任何要排版的数据，而只包含控制序列.然而它通常包含这样的数据，并且目标格式的文件具有排版文本。该文件还将与指定为输入的文件具有相同的名称，并且是主输出文件。对于原始的 TeX，这是一个 DVI 格式的文件。我们将调用输入和输出文件的名称，而不扩展作业名称。"
p3: "在此页面上，您将找到一个解释创建自定义 TeX 格式文件的代码示例，您可以在其中看到如何自定义 TeX 文件的输出。要自定义 .tex 文件输出，我们需要："
p4: "Aspose.TeX for .NET API 是一个功能丰富、功能强大且易于使用的 C# 平台文档操作和转换 API。"
p5: "打开 NuGet 包管理器，搜索 Aspose.TeX 并安装。您也可以从包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: "自定义 TeX 输出 C# 的步骤："
h3: "用于 TeX 输出自定义的 C# 代码"
item1: "借助 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 方法的 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 类，在 ObjectTeX 引擎扩展上创建无格式的 TeX 引擎选项。"
item2: "使用 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 类为输入指定文件系统工作目录。"
item3: "使用 [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 类为输出指定文件系统工作目录。"
item4: "要创建新格式，请使用 [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) 方法。"
item5: 细化输出。
---