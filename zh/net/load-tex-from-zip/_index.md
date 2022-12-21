---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: 从 ZIP 加载 TeX | .NET API 解决方案 | Aspose API 解决方案
url: /net/load-tex-from-zip/
description: ".NET API 解决方案与 TeX 一起工作。通过示例了解如何使用几行 C# 代码从 ZIP 加载 TeX 文件。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 从 ZIP 加载 TeX 源文件
h2: ".NET API 解决方案从 ZIP 存档加载 TeX 文件"
---

{{<section overview>}}
---
p1: "TeX 被称为排版语言。这意味着您不对文档中的文本进行格式化，而是将纯文本与命令一起输入。作为输出，您将获得所需(指定)格式的格式化文件。要进一步了解 TeX 输入和输出，请学习文档的 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/)。"
p2: "众所周知，TeX 的主要目的是帮助创建数学或技术文本写作。但在进行任何操作之前，应首先加载文件。在这里，您将找到代码片段，解释如何使用 ZIP 目录从 ZIP 加载 TeX 源文件进行输入和输出、输出到 PDF 设备、将终端输出写入控制台。"
p3: "要加载 .tex 文件，我们需要："
p4: "Aspose.TeX for .NET API 是一个功能丰富、功能强大且易于使用的 C# 平台文档操作和转换 API。"
p5: "打开 NuGet 包管理器，搜索 Aspose.TeX 并安装。您也可以从包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: "从 ZIP 存档 C# 加载 TeX 的步骤："
h3: "用于加载 TeX 的 C# 代码"
item1: "打开 ZIP 存档上的流以将其用作输入工作目录。"
item2: "打开 ZIP 存档上的流以将其用作输出工作目录。"
item3: "使用 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 的 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 类。"
item4: "为输入指定 ZIP 存档工作目录或/并指定存档内的路径。为此，请使用 [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) 类的构造函数。"
item5: "为输出指定 ZIP 存档工作目录或/并指定存档内的路径。为此，请使用 [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) 类的构造函数。"
item6: "使用 [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) 类将控制台指定为输出终端。"
item7: "使用 [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) 类定义保存选项。"
item8: "运行作业 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 方法 [*XpsDevice*](https://reference.aspose.com/tex/网/aspose.tex.presentation.xps/xpsdevice/)。"
item9: 细化输出。
---