---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX Converters for .NET – FAQ
linktitle: FAQ
type: docs
weight: 90
url: /net/conversion/faq/
description: Frequently asked questions about converting TeX and LaTeX files with Aspose.TeX for .NET, including supported formats, conversion code, output to streams, image options, packages, evaluation mode and runtime requirements.
keywords: Aspose.TeX, .NET, FAQ, LaTeX conversion, LaTeX to PDF, LaTeX to XPS, LaTeX to SVG, LaTeX to PNG, TeXJob, licensing, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**Q: What input and output formats does Aspose.TeX for .NET support?**

**A:** Aspose.TeX typesets TeX and LaTeX documents. The main input file can come from a file, a stream or a terminal; files it includes can come from a folder or a ZIP archive. Separate APIs render a single LaTeX math formula or a LaTeX fragment. The output formats are PDF, XPS, SVG, PNG, JPEG, BMP and TIFF. See [Supported File Formats](/tex/{{lang.url-fragment}}net/supported-file-formats/).
<br><br>

**Q: Can Aspose.TeX convert LaTeX to Word (DOCX) or HTML?**

**A:** No. Aspose.TeX produces PDF, XPS, SVG and raster images only. If you need another format, convert the PDF output with a library that supports it.
<br><br>

**Q: How do I convert a LaTeX file to PDF in C#?**

**A:** Create `TeXOptions` for the ObjectLaTeX format, set the output directory and `PdfSaveOptions`, and run a `TeXJob` with a `PdfDevice`:

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

The result is written to the output working directory under the job name. See [LaTeX to PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/).
<br><br>

**Q: How do I choose the output format?**

**A:** Set `TeXOptions.SaveOptions` and pass the matching device to `TeXJob`:

| Format | Save options | Device |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG, JPEG, BMP, TIFF | `PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions` | `ImageDevice` |

See [LaTeX to XPS](/tex/{{lang.url-fragment}}net/latex-to-xps/) and [LaTeX to image](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**Q: Can I get the result in memory instead of a file?**

**A:** Yes. `PdfDevice` and `XpsDevice` have constructors that accept a `Stream` to write the document to. `ImageDevice` keeps the rendered pages in its `Result` property as an array of byte arrays, one per page. To read the main input from a stream, pass the stream to the `TeXJob` constructor. See [LaTeX to PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) and [Other ways to provide main TeX input](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/).
<br><br>

**Q: How do I control image resolution and quality?**

**A:** Use the properties of the image save options:

- `Resolution` — image resolution in DPI.
- `SmoothingMode` and `InterpolationMode` — rendering quality.
- `TiffSaveOptions.Compression` and `TiffSaveOptions.Multipage` — TIFF compression and whether all pages go into one file (multipage TIFF is not yet supported by the `Aspose.TeX.Drawing` package).

For example, `new PngSaveOptions { Resolution = 300 }` produces 300 DPI PNG images. See [LaTeX to image](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**Q: How do I know whether the conversion succeeded?**

**A:** `TeXJob.Run()` returns a `TeXJobResult` value: `Spotless`, `WarningIssued`, `ErrorMessageIssued` or `FatalErrorStop`. Details are written to the transcript (`.log`) file in the output directory and to the output terminal. See [Aspose.TeX's output interface](/tex/{{lang.url-fragment}}net/aspose-tex-output/).
<br><br>

**Q: Do I need a LaTeX installation (e.g., MiKTeX) on the server?**

**A:** No. Aspose.TeX is a standalone .NET library with its own TeX engine, LaTeX format and fonts. It does not require any external TeX distribution.
<br><br>

**Q: Which LaTeX packages can I use?**

**A:** Aspose.TeX includes a set of embedded LaTeX packages; see [Embedded packages](/tex/{{lang.url-fragment}}net/embedded-packages/). To use other packages, put their files in a folder or ZIP archive and specify it as `TeXOptions.RequiredInputDirectory`; see [External LaTeX packages](/tex/{{lang.url-fragment}}net/external-latex-packages/).
<br><br>

**Q: Can I render a single formula or a LaTeX fragment instead of a whole document?**

**A:** Yes. Use `PngMathRenderer` or `SvgMathRenderer` for math formulas and `PngFigureRenderer` or `SvgFigureRenderer` for arbitrary LaTeX fragments. They return the size of the rendered image. See [LaTeX math formula rendering](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) and [LaTeX figure rendering](/tex/{{lang.url-fragment}}net/latex-figure-rendering/).
<br><br>

**Q: What are the runtime requirements?**

**A:**

- `Aspose.TeX` package: Windows (x64/x86); .NET Framework 4.0 or later, .NET Standard 2.0, .NET 6 or later.
- `Aspose.TeX.Drawing` package: Windows, Linux and macOS (x64/Arm64); .NET Framework 4.7.2 or later, .NET 7 or later.
- No additional native binaries are needed. On Linux, XPS and SVG output requires ICU. See [System Requirements](/tex/{{lang.url-fragment}}net/system-requirements/) and [Linux, macOS and Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).
<br><br>

**Q: What are the limitations of the evaluation version?**

**A:** Without a license, Aspose.TeX works in evaluation mode: it outputs no more than four pages of a document, and the pages carry an evaluation watermark. The evaluation version is the same package; to evaluate without limitations, request a [30-day temporary license](https://purchase.aspose.com/temporary-license/). See [Licensing](/tex/{{lang.url-fragment}}net/licensing/).
<br><br>

**Q: How do I apply a license in code?**

**A:** Apply the license once, before the first conversion:

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

You can also load the license from a stream or use a metered license. See [Licensing](/tex/{{lang.url-fragment}}net/licensing/). For prices, see the [Aspose.TeX pricing page](https://purchase.aspose.com/pricing/tex/).
<br><br>

**Q: Where can I find API documentation, examples and support?**

**A:**

- [Developer guide](https://docs.aspose.com/tex/net/)
- [API reference](https://reference.aspose.com/tex/net/)
- [Community forum](https://forum.aspose.com/c/tex/)
<br><br>
