---
translation: true
template: /templates/_template-python-net.md
title: 外部乳胶软件包| Python
linktitle: 外部乳胶软件包
weight: 19
url: /python-net/external-latex-packages/
description: python的Aspose.TeX API支持使用库本身中未包含的外部软件包的使用，例如Fancybox和PGFPLOTS软件包
lastmod: "2025-06-10"
---

{{<section overview>}}

## 外部乳胶软件包

**Aspose.TeX**库带有各种[常见的乳胶包裹](/tex/{{lang.url-fragment}}net/embedded-packages/)，因此无需手动向Tex发动机提供这些软件包。但是，在某些情况下，您的乳胶文件需要一个包装中未包含的软件包。在这种情况下，您可以尝试通过[queld_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/)[texoptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/)类实例提供必要的输入，例如所需软件包的源文件。我们将探讨这两个示例的工作方式。

### 所需的输入以未包装的形式(``Fancybox''软件包)提供。

假设我们有以下名为`ruild-Input-fs.tex`的基本乳胶文件，这是我们[示例解决方案](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET)的一部分：

```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

文件的第三行表示它需要`fancybox“软件包，fancybox”包中未包含在“本机”支持中。假设我们有“ Fancybox”软件包的源文件。由于这是一个由单个文件组成的简单软件包，我们可以将此文件放在文件系统中的任何位置，并指定目录路径如下：


```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

一旦我们使用此选项运行TEX作业(请记住要根据需要调整其他选项)，我们将获得输出文档，在这种情况下，这是PNG图像。

![输出文档](/tex/images/python-net/Conversion-RequiredInputFs.png)

这是该示例的完整源代码：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### 提供所需的输入以存档的形式(``pgfplots'软件包)提供

现在，假设我们有以下名为“必需input-zip.tex”的乳胶文件，这也是我们示例解决方案的简单文件：


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```

在第三行上，可以观察到该文件需要“ PGFPLOTS”软件包，而不是“本地”支持。再一次，假设我们拥有“ PGFPLOTS”软件包的源文件，这些文件很多，并且位于任何乳胶排放应用程序的安装目录中的两个不同目录中。可以在`\ tex \ generic`和`\ tex \ latex`目录”中找到“ pgfplots”文件夹。为了使aspose.tex库正确运行，必须提供两个文件夹的内容作为输入。为了实现这一目标，我们希望将这些源文件包装到ZIP档案中。以下是档案的所需布局：

![存档的布局](/tex/images/python-net/pgfplots-zip-layout.png)

这是我们定义这些源文件的可访问性的方法：

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

通过此选项运行Tex作业后，我们将获得输出文档：

![输出文档](/tex/images/python-net/Conversion-RequiredInputZip.png)

这是该示例的完整源代码：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_注意：_** 结果是使用 `pgfplots` 软件包版本 1.18.1 验证的。而 **Aspose.TeX** 库中包含的 `pfg` 软件包版本为 3.1.9a。

<!--
### 使用外部字体包

通常，LaTeX 发行版会预定义一组可用于排版的字体。然而，除了这些默认字体之外，**Aspose.TeX** 还包含一些非标准字体包，例如 `amsfonts`、`eurosym` 和 `wasysym`。正如我们之前讨论的，Aspose.TeX 也支持使用外部字体包，尽管我们之前的大部分讨论都集中在不包含字体的字体包上。

**Aspose.TeX** 的 *Object TeX* 引擎扩展需要字体映射，这些字体映射是特定格式的文本文件，扩展名为 `.map`，用于确定每个 TeX 内部字体名称对应的物理字体。这些字体映射需要在初始化阶段加载到 TeX 内存中，并且应包含在您使用的软件包中。由于引擎无法识别所有字体映射的名称，它会搜索扩展名为 `.map` 的文件。因此，在为 [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) 选项提供值时，[IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) 接口的实现应该允许按扩展名访问文件名集合。此外，此实现还应实现 [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/) 接口。标准实现（例如 [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) 和 [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/）已满足这些要求。

下面是一个自定义必需输入目录的示例，演示了如何实现 [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/) 接口。此示例重点介绍按扩展名收集文件名，并有意省略了文件存储和检索的细节。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}
-->

### 限制

如果您遇到乳胶文件所需的*latex3e*kernel an的软件包，则不太可能与**Aspose.TeX**库一起使用。这是因为库基于 *latex2e*内核。

此外，在某些情况下，您的乳胶文件要求的包装直接使用了**Aspose.TeX** library的*object tex*引擎不支持设备的原始命令。在这种情况下，该软件包将无法与库一起使用。