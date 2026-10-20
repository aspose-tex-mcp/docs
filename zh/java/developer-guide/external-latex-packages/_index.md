---
translation: true
template: /templates/_template-java.md
title: 外部乳胶软件包| Java的Aspose.TeX
linktitle: 外部乳胶软件包
weight: 30
url: /java/external-latex-packages/
description: Java的Aspose.TeX API允许使用外部软件包，即未包含在库本身(例如Fancybox或PGFPLOTS软件包)中的软件包。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 外部乳胶软件包

**Aspose.TeX**库中包含许多[常见的乳胶软件包](/tex/{{lang.url-fragment}}net/embedded-packages/)。因此，您不必关心如何将这些包装提供给图书馆的Tex引擎。但是有时(可能经常)您的乳胶文件可能需要一个包裹以外的包装包装。在这种情况下，您可以尝试使用[setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-)[TexOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/)类实例的方法提供所需的输入，即所需的软件包的源文件。我们将看到这两个示例如何工作。

将 `inputFile` 设置为对应 LaTeX 文档的完整路径，将 `outputDirectory` 设置为现有的输出文件夹。两个转换示例均生成 150 DPI 的 PNG。导入所选示例使用的 Aspose.TeX 类、`com.aspose.tex.rendering.ImageDevice`、`com.aspose.tex.rendering.PngSaveOptions`，以及 ZIP 输入所需的 `java.io.InputStream` 和 `java.nio.file.Files`。在调用方法中处理或声明异常。按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证。

### 打开包装所需的输入(`fancybox`软件包)

假设我们有以下简单的乳胶文件，这是我们的[示例解决方案](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java)：

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
  \begin{Beqnarray}
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

第三行需要外部软件包 `fancybox`。将 `packagesDirectory` 设置为包含 `fancybox.sty` 及其依赖文件的本地文件夹。下面的完整示例将此文件夹设置为 `RequiredInputDirectory`，并生成 PNG 图像。设备和工作目录在作业结束前保持打开，随后释放或关闭。

![输出文档](/tex/images/java/Conversion-RequiredInputFs.png)

这是该示例的完整源代码：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-FileSystem.java" >}}

### 存档所需的输入(`pgfplots`软件包)

现在，让我们假设我们也有以下简单的乳胶文件，这是我们的示例解决方案中的“必需输入” zip.tex。


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

在第三行上，我们看到该文件需要“ PGFPLOTS”软件包，这也不是“本地”支持的。同样，我们假设我们有“ PGFPLOTS”软件包源文件。如果您在任何乳胶排放应用程序的安装目录中找到两个位置，则在两个位置之间进行了大量文件。您可以在`\ tex \ generic`和`\tex\latex`文件夹上找到`pgfplots`文件夹。并且必须根据需要输入Aspose.TeX库提供两个文件夹的内容。我们希望将这些源文件包装在zip存档中，因此这是存档的布局：

![存档的布局](/tex/images/java/pgfplots-zip-layout.png)

将 `packagesZip` 设置为指向包含软件包 generic 和 LaTeX 源文件的归档的 `java.nio.file.Path`。下面的完整 Java 示例使用 `Files.newInputStream(...)` 打开归档，并将 `InputZipDirectory` 设置为 `RequiredInputDirectory`。空的基本路径参数选择整个归档。在 TeX 作业结束前保持 ZIP 流和目录打开，随后关闭它们。结果是包含两个图表的 PNG 图像。

![输出文档](/tex/images/java/Conversion-RequiredInputZip.png)

这是该示例的完整源代码：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-Zip.java" >}}

> **_注意：_** 结果是使用 `pgfplots` 软件包版本 1.18.1 验证的。而 **Aspose.TeX** 库中包含的 `pfg` 软件包版本为 3.1.9a。

### 使用外部字体软件包

通常，乳胶发行版带有一系列可用于排版的默认字体。除了这些字体外，**Aspose.TeX**还提供几个非标准字体软件包，例如“ amsfonts”，“ eurosym”和“ wasysym”。如前所述，**Aspose.TeX**也支持使用外部软件包的使用，尽管我们的重点主要集中在不包括字体的软件包上。
**Aspose.TeX**中的*对象Tex*引擎扩展名需要字体映射，它是带有`.map`扩展名的文本文件，该文件指定了与每个Tex的内部字体名称相对应的物理字体。这些字体地图需要在初始化阶段加载到TEX的内存中，并且必须包含在软件包文件中。由于引擎不知道所有字体映射的名称，因此它搜索了具有`.map'扩展名的任何文件。因此，将[IinputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/)用作[InsultInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--)选项的接口的实现必须提供一种基于其扩展名的访问文件名的收集的方法。具体而言，此实现还必须实现[IfileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/)接口。标准实现，[InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/)和[InputzipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/)，已经满足此要求。

下面的自定义 `RequiredInputDirectory` 实现两个接口，并读取显式注册的本地文件。将它连同所含的导入保存为 `RequiredInputDirectory.java`。使用 `storeFileName(...)` 注册每个文件，通过 `options.setRequiredInputDirectory(...)` 设置实例，并在作业结束后关闭它。这是一个扁平注册表：不使用完整路径请求文件时，文件名必须唯一。扩展名匹配不区分大小写；可选的收集路径选择文件系统目录。注册所有必要的软件包、字体映射、度量和实际字体文件。文件收集使映射可被发现，但不会提供缺失的字体数据。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInputDirectory.java" >}}

### 限制

您的乳胶文件要求的包装可以在 *LaTeX3e*内核下开发。这样的软件包很可能无法与**Aspose.TeX**库一起使用，因为后者基于*LaTeX2e*内核。

此外，您的乳胶文件要求的软件包可以直接调用**Aspose.TeX**库*对象Tex*引擎不支持的设备依赖的原始命令。不幸的是，这样的软件包无法确定。