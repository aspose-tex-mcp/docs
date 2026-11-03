---
translation: true
template: /templates/_template-net.md
title: 用于 .NET 的 Aspose.TeX 转换器 – 常见问题解答
linktitle: 常见问题解答
type: docs
weight: 90
url: /net/conversion/faq/
description: 关于使用 Aspose.TeX for .NET 转换 TeX 和 LaTeX 文件的常见问题，包括支持的格式、转换代码、输出到流、图像选项、宏包、评估模式和运行时要求。
keywords: Aspose.TeX, .NET, FAQ, LaTeX 转换, LaTeX 转 PDF, LaTeX 转 XPS, LaTeX 转 SVG, LaTeX 转 PNG, TeXJob, 许可, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**问：Aspose.TeX for .NET 支持哪些输入和输出格式？**

**答：** Aspose.TeX 对 TeX 和 LaTeX 文档进行排版。主输入文件可以来自文件、流或终端；它所包含的文件可以来自文件夹或 ZIP 存档。单独的 API 用于渲染单个 LaTeX 数学公式或 LaTeX 片段。输出格式为 PDF、XPS、SVG、PNG、JPEG、BMP 和 TIFF。请参阅[支持的文件格式](/tex/{{lang.url-fragment}}net/supported-file-formats/)。
<br><br>

**问：Aspose.TeX 能否将 LaTeX 转换为 Word (DOCX) 或 HTML？**

**答：** 不能。Aspose.TeX 只生成 PDF、XPS、SVG 和光栅图像。如果需要其他格式，请使用支持该格式的库转换 PDF 输出。
<br><br>

**问：如何在 C# 中将 LaTeX 文件转换为 PDF？**

**答：** 为 ObjectLaTeX 格式创建 `TeXOptions`，设置输出目录和 `PdfSaveOptions`，然后使用 `PdfDevice` 运行 `TeXJob`：

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

结果以作业名称写入输出工作目录。请参阅 [LaTeX 转 PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/)。
<br><br>

**问：如何选择输出格式？**

**答：** 设置 `TeXOptions.SaveOptions`，并将对应的设备传给 `TeXJob`：

| 格式 | 保存选项 | 设备 |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG、JPEG、BMP、TIFF | `PngSaveOptions`、`JpegSaveOptions`、`BmpSaveOptions`、`TiffSaveOptions` | `ImageDevice` |

请参阅 [LaTeX 转 XPS](/tex/{{lang.url-fragment}}net/latex-to-xps/) 和 [LaTeX 转图像](/tex/{{lang.url-fragment}}net/latex-to-image/)。
<br><br>

**问：能否在内存中而不是在文件中获取结果？**

**答：** 可以。`PdfDevice` 和 `XpsDevice` 具有接受 `Stream` 的构造函数，文档会写入该流。`ImageDevice` 将渲染后的页面以字节数组的数组形式保存在 `Result` 属性中，每页一个。要从流中读取主输入，请将流传给 `TeXJob` 的构造函数。请参阅 [LaTeX 转 PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) 和[提供主 TeX 输入文件的其他方式](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/)。
<br><br>

**问：如何控制图像的分辨率和质量？**

**答：** 使用图像保存选项的以下属性：

- `Resolution` — 图像分辨率 (DPI)。
- `SmoothingMode` 和 `InterpolationMode` — 渲染质量。
- `TiffSaveOptions.Compression` 和 `TiffSaveOptions.Multipage` — TIFF 压缩以及是否将所有页面保存到一个文件中（`Aspose.TeX.Drawing` 包尚不支持多页 TIFF）。

例如，`new PngSaveOptions { Resolution = 300 }` 生成 300 DPI 的 PNG 图像。请参阅 [LaTeX 转图像](/tex/{{lang.url-fragment}}net/latex-to-image/)。
<br><br>

**问：如何知道转换是否成功？**

**答：** `TeXJob.Run()` 返回一个 `TeXJobResult` 值：`Spotless`、`WarningIssued`、`ErrorMessageIssued` 或 `FatalErrorStop`。详细信息会写入输出目录中的记录文件 (`.log`) 和输出终端。请参阅 [Aspose.TeX 的输出接口](/tex/{{lang.url-fragment}}net/aspose-tex-output/)。
<br><br>

**问：服务器上是否需要安装 LaTeX（例如 MiKTeX）？**

**答：** 不需要。Aspose.TeX 是一个独立的 .NET 库，拥有自己的 TeX 引擎、LaTeX 格式和字体，不需要任何外部 TeX 发行版。
<br><br>

**问：可以使用哪些 LaTeX 宏包？**

**答：** Aspose.TeX 包含一组内置的 LaTeX 宏包，请参阅[嵌入式LaTeX软件包](/tex/{{lang.url-fragment}}net/embedded-packages/)。要使用其他宏包，请将其文件放在文件夹或 ZIP 存档中，并将其指定为 `TeXOptions.RequiredInputDirectory`，请参阅[外部 LaTeX 包](/tex/{{lang.url-fragment}}net/external-latex-packages/)。
<br><br>

**问：能否只渲染单个公式或 LaTeX 片段，而不是整个文档？**

**答：** 可以。对数学公式使用 `PngMathRenderer` 或 `SvgMathRenderer`，对任意 LaTeX 片段使用 `PngFigureRenderer` 或 `SvgFigureRenderer`。它们会返回渲染图像的尺寸。请参阅 [LaTeX 数学公式渲染](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) 和 [LaTeX 图形渲染](/tex/{{lang.url-fragment}}net/latex-figure-rendering/)。
<br><br>

**问：运行时要求是什么？**

**答：**

- `Aspose.TeX` 包：Windows (x64/x86)；.NET Framework 4.0 或更高版本、.NET Standard 2.0、.NET 6 或更高版本。
- `Aspose.TeX.Drawing` 包：Windows、Linux 和 macOS (x64/Arm64)；.NET Framework 4.7.2 或更高版本、.NET 7 或更高版本。
- 不需要额外的本机库。在 Linux 上，XPS 和 SVG 输出需要 ICU。请参阅[系统要求](/tex/{{lang.url-fragment}}net/system-requirements/) 和 [Linux、macOS 和 Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/)。
<br><br>

**问：评估版有哪些限制？**

**答：** 没有许可证时，Aspose.TeX 以评估模式运行：最多输出文档的四页，并且页面带有评估水印。评估版就是同一个包；如需无限制地评估，请申请 [30 天临时许可证](https://purchase.aspose.com/temporary-license/)。请参阅[许可](/tex/{{lang.url-fragment}}net/licensing/)。
<br><br>

**问：如何在代码中应用许可证？**

**答：** 在首次转换之前应用一次许可证：

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

也可以从流中加载许可证，或使用计量 (metered) 许可证。请参阅[许可](/tex/{{lang.url-fragment}}net/licensing/)。有关价格，请参阅 [Aspose.TeX 价格页面](https://purchase.aspose.com/pricing/tex/)。
<br><br>

**问：在哪里可以找到 API 文档、示例和支持？**

**答：**

- [开发者指南](https://docs.aspose.com/tex/net/)
- [API 参考](https://reference.aspose.com/tex/net/)
- [社区论坛](https://forum.aspose.com/c/tex/)
<br><br>
