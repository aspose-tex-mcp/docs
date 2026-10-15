---
translation: true
template: /templates/_template-java.md
title: 提供主TeX输入文件的其他方法 | Java
linktitle: 提供主TeX输入文件的其他方法
weight: 14
url: /java/other-ways-of-main-input/
description: Java的Aspose.TeX API解决方案的转换功能具有一个构造函数，该构造函数接受流作为第一个参数。这是一些代码示例。
lastmod: "2026-04-21"
---

{{<section overview>}}

## 将主要输入文件作为流提供给TeX引擎

到目前为止，我们只知道如何将[主输入文件](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)传递给TeX引擎作为文件名，无论是完全指定还是简短形式，无论是扩展名还是没有扩展名。但是，“ Texjob”类中还有另一个[构造函数](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)，它接受流作为第一个参数。如果出于某种原因，我们将主要输入文件中的主要输入文件中的其他形式除外，则很方便。这是我们可以处理的方法：

将 `outputDirectory` 设置为现有的输出文件夹。导入示例使用的 Aspose.TeX 类、`com.aspose.tex.rendering.XpsDevice`、`com.aspose.tex.rendering.XpsSaveOptions`，以及流输入所需的 `java.io.ByteArrayInputStream` 和 `java.nio.charset.StandardCharsets`。调用方法必须处理或声明异常。按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证，以避免评估版限制。流示例包含完整的 LaTeX 文档，因此无需输入工作目录。流和设备在作业结束前保持打开，随后关闭或释放。

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-StreamInput-LaTeX.java" >}}

如果流输入没有显式指定作业名称，引擎会使用默认名称 *texput*。此示例创建 `texput.xps` 和 `texput.log`。使用 `options.setJobName(...)` 可以选择其他作业名称。有关作业名称的详细信息，请参见 [此处](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) 和 [此处](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name)。

## 从终端输入主TeX输入文件

“ Texjob”类还有另一个[构造函数](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) ，它根本不允许我们指定输入。那么，您可能会想知道什么是这样的TeX工作？这次我们将需要一个输入终端。 TeX引擎将要求我们从终端输入文件名。

将 `inputDirectory` 设置为包含名为 `hello-world.ltx` 的完整 LaTeX 文档的文件夹，将 `outputDirectory` 设置为现有的输出文件夹。在控制台运行示例，在 `**` 提示符处输入 `hello-world.ltx` 并按 Enter。示例创建 `hello-world.xps`，并将终端输出写入控制台。两个示例均使用 `NonstopMode` 进行处理，但终端构造函数仍需要初始文件名。对于无人值守运行，请提供 `IInputTerminal` 实现，或使用文件或流输入。

这是代码：

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-MainInputTerminal.java" >}}

一旦运行，发动机都会粘贴，等待我们输入文件名(有或没有路径，有或没有扩展的情况)：


![终端窗口](/tex/images/java/Conversion-MainInputTerminal.png)

这就是它在输出终端上的外观，即控制台：

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