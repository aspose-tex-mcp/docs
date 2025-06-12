---
translation: true
template: /templates/_template-net.md
title: 外部乳胶软件包| .NET
linktitle: 外部乳胶软件包
weight: 20
url: /net/external-latex-packages/
description: aspose.tex for .NET允许使用外部软件包，即库本身不包含的api，例如fancybox和pgfplots软件包。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 外部乳胶软件包

**Aspose.TeX**库包含许多[常见的乳胶软件包](/tex/{{lang.url-fragment}}net/embedded-packages/)。因此，您不必担心如何将这些包装提供给图书馆的Tex引擎。但是有时(或经常)您的乳胶文件可能需要一个包裹以外的包装包装。如果是这种情况，您可以尝试通过[queldInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/)[texoptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)类实例提供所需的输入，即所需的包源文件。我们将看到这两个示例如何工作。

### 打开包装所需的输入(`fancybox`软件包)

假设我们有以下简单的乳胶文件，这是我们的[示例解决方案](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET)：


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

在第三行上，我们可以看到该文件需要“ fancybox”软件包，而不是“本地”支持。我们还假设我们有“ fancybox”软件包源文件。这是一个简单的软件包，因此它确实由一个文件组成。我们可以将此文件放在文件系统中的任何位置，并如下所示指定目录路径：


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

使用此选项运行Tex作业(不要忘记根据需要调整其他选项)后，我们将获得输出文档(即PNG图像)。

![输出文档](/tex/images/net/Conversion-RequiredInputFs.png)

这是该示例的完整源代码：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.cs" >}}

### 存档所需的输入(`pgfplots`软件包)

现在，我们说我们也有以下简单的乳胶文件，这是我们的示例解决方案中的“必需输入” zip.tex`：


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

第一个例子是并排绘制的 2D 和 3D 数学表达式。

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


在第三行上，我们可以看到该文件需要`pgfplots`软件包，这也不是“本地”支持的。同样，我们假设我们有“ PGFPLOTS”软件包源文件。如果您在任何乳胶排放应用程序的“安装目录”中找到两个位置，则大量文件在两个位置之间进行了分配。您可以在`\ tex \ generic`和`\ tex \ latex`文件夹上找到`pgfplots`文件夹。并且必须根据需要输入Aspose.TeX库提供两个文件夹的内容。我们希望将这些源文件包装在zip存档中，因此这是存档的布局：

![存档的布局](/tex/images/net/pgfplots-zip-layout.png)

这就是我们指定对这些源文件的访问的方式：


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

通过此选项运行Tex作业后，我们将获得输出文档：

![输出文档](/tex/images/net/Conversion-RequiredInputZip.png)

这是该示例的完整源代码：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.cs" >}}

> **_注意：_** 结果是使用 `pgfplots` 软件包版本 1.18.1 验证的。而 **Aspose.TeX** 库中包含的 `pfg` 软件包版本为 3.1.9a。

### 采用外部字体软件包

通常，乳胶分布提供一组可用于排版的默认字体。除这些字体外，**Aspose.TeX**包括许多非标准字体软件包。例如，`amsfonts'，`eurosym'和`wasysym`。如上所述，Aspose.TeX还允许使用外部包装。但是大多数情况下，我们在谈论不包含字体的软件包。

**Aspose.TeX**的*对象Tex*引擎扩展需要字体映射(以“约定”为“ .map”扩展为特定格式的文本文件)，以确定哪些物理字体对应于每个Tex的内部字体名称。这些字体图必须在初始化阶段加载到Tex的内存中。而且，当然，它们必须存在于您要插入的软件包的文件中。由于引擎不知道所有字体地图的名称，因此它可以在所有文件中查找所有文件。因此，用于[InsirceInputInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/)选项的[IinputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/)接口的实现必须提供一种通过扩展访问文件名的收集的方法。更具体地说，该实现还必须实现[IfileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/)接口。标准实现 -  [InputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)和[InputzipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) - 已经这样做。

下面，我们提供了一个自定义所需输入目录的说明性示例，该目录还实现了[IfileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/)接口。在专注于按扩展程序收集文件名的同时，我们故意省略了文件存储和检索的详细信息。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RequiredInputDirectory.cs" >}}

### 限制

可能会在 * latex3e *内核下开发乳胶文件所需的包装。这样的软件包很可能无法与**Aspose.TeX**库一起使用，因为后者基于*lastx2e*内核。

您的乳胶文件要求的软件包可能会直接调用**Aspose.TeX**库的*对象Tex*引擎不支持设备的原始命令。不幸的是，这样的软件包无法确定。