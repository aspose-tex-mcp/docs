---
translation: true
template: /templates/_template-net.md
title: Aspose TeX for Python – FAQ
linktitle: FAQ
type: docs
weight: 80
url: /python-net/faq/
description: Comprehensive Frequently Asked Questions for Aspose TeX for Python, detailing how to install the pure‑Python API, convert LaTeX, manage fonts, supported packages, and much more.
keywords: Aspose TeX Python, LaTeX conversion, PDF generation, Python .NET, pythonnet, document rendering, font embedding, licensing, multi-threading, supported formats
lastmod: "2025-12-08"
---

{{<section overview>}}

<br><br>

**Q: What is Aspose TeX for Python?**  
<br>
**A:** Aspose TeX for Python is a pure‑Python API (built on top of the Aspose TeX .NET library via pythonnet) that renders and converts LaTeX/TeX documents to PDF, XPS, SVG, PNG, JPEG, BMP, TIFF and other image formats without requiring any external TeX distribution. It runs in‑process and is suited for web services, desktop apps, and automated report generators.  
<br><br>

**Q: How do I install Aspose TeX for Python?**  
<br>
**A:** Run `pip install aspose-tex-python-net`. The package bundles the required `pythonnet` runtime automatically. Install it inside any virtual environment (Windows, Linux, macOS) with Python 3.8 or later. Verify the installation with:

```python
import aspose.tex as tex
print(tex.__version__)
```  
<br><br>

**Q: Do I need a local TeX distribution (MiKTeX, TeX Live, etc.)?**  
<br>
**A:** No. All parsing and rendering logic is built into Aspose TeX, so you never need an external TeX engine. The library includes over 300 core LaTeX packages and common class files out of the box.  
<br><br>

**Q: How can I convert a `.tex` file to PDF with a few lines of code?**  
<br>
**A:** Create a `TeXJob` with the Object LaTeX configuration, `PdfSaveOptions` and a `PdfDevice`. Set `ASPOSE_TEX_INPUT_FILE` to your input file and `ASPOSE_TEX_OUTPUT_DIR` to the output directory, or edit the default paths. Apply a license before conversion as described in [Licensing](/tex/python-net/licensing/).

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

The default output filename follows the input stem: `hello-world.ltx` produces `hello-world.pdf`. See [LaTeX to PDF](/tex/python-net/latex-to-pdf/) for details.
<br><br>

**Q: Which output formats can Aspose TeX for Python generate?**  
<br>
**A:** PDF, XPS, SVG, PNG, JPEG, BMP, and TIFF. Each format can be controlled via specific `SaveOptions` objects (e.g., `PdfSaveOptions`, `PngSaveOptions`, `SvgSaveOptions`).
<br><br>

**Q: How do I embed custom fonts into the generated PDF?**  
<br>
**A:** Fonts are selected by the TeX or LaTeX document and its packages. For package resources, see [External LaTeX packages](/tex/{{lang.url-fragment}}python-net/external-latex-packages/). To control whether only used glyphs are embedded, use the [`subset_fonts`](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/) property of `PdfSaveOptions`; this is different from selecting a custom font. See [Subsetting fonts](/tex/{{lang.url-fragment}}python-net/other-options/#subsetting-fonts) for a complete XPS example using the same option.
<br><br>

**Q: What LaTeX packages and classes are supported out of the box?**  
<br>
**A:** The library includes common LaTeX packages and classes. Consult the [embedded package list](/tex/{{lang.url-fragment}}net/embedded-packages/) for coverage. The [external package example](/tex/{{lang.url-fragment}}python-net/external-latex-packages/) for `pgfplots` supplies its package sources externally through `required_input_directory`.
<br><br>

**Q: How can I use a third‑party `.sty` or class file that is not built‑in?**  
<br>
**A:** Set `TeXOptions.required_input_directory` to an `InputFileSystemDirectory` containing the required package files. The complete example below loads `fancybox.sty` from `ExternalLaTeXPackages/packages` and converts `required-input-fs.tex` to PNG. Set `ASPOSE_TEX_INPUT_DIR` to the parent of `ExternalLaTeXPackages` (default: `input`) and `ASPOSE_TEX_OUTPUT_DIR` to the output folder (default: `output`). Apply a [license](/tex/{{lang.url-fragment}}python-net/licensing/) first.

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

For ZIP archives and package compatibility restrictions, see [External LaTeX packages](/tex/{{lang.url-fragment}}python-net/external-latex-packages/).
<br><br>

**Q: What are the main limitations of the engine?**  
<br>
**A:**  

| Limitation | Details |
|------------|---------|
| Shell escape (`\write18`) | Disabled for security. |
| Full TikZ externalization | Not supported; most TikZ graphics render in‑process, but extremely complex drawings may fail. |
| Unicode font coverage | Only TrueType/OpenType fonts with complete glyph sets are fully supported; legacy Type 1 fonts may need conversion. |
| Very large documents (> 500 pages) | Can consume significant memory; consider streaming pages with `Document.save(output_stream, options)`. |  
<br><br>

**Q: How do I apply a license key and what licensing models are available?**  
<br>
**A:** Apply the license before using other Aspose.TeX classes. Set `ASPOSE_TEX_PYTHON_NET_LICENSE_PATH` to your license file, or place `Aspose.TeX.Python-net.lic` in the working directory:

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-LoadLicenseFromFile.py" >}}

For file, stream and metered examples and evaluation limitations, see [Licensing](/tex/python-net/licensing/).
<br><br>

**Q: Is the library thread‑safe for parallel conversions?**  
<br>
**A:** Yes, provided each thread creates its own `Document` instance. Static objects such as the `License` must be set before any parallel work starts.  
<br><br>

**Q: Which .NET runtime version does Aspose TeX for Python require?**  
<br>
**A:** The package ships with the **.NET 6 (x64)** runtime binaries. They are loaded automatically by pythonnet on the first import; you do not need to install .NET manually.  

<br><br>

**Q: How can I set page size, orientation, and DPI for raster outputs?**  
<br>
**A:** Define page size and orientation in the LaTeX source. For example, save this A4 landscape document as `landscape.ltx`:

```latex
\documentclass{article}
\usepackage[a4paper,landscape]{geometry}
\begin{document}
Hello, World!
\end{document}
```

Set `PngSaveOptions.resolution` before assigning the save options to the job. This example uses 300 DPI. Set `ASPOSE_TEX_INPUT_FILE` to `landscape.ltx` and `ASPOSE_TEX_OUTPUT_DIR` to your output directory, or use the example's default paths:

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPng-PageLayout.py" >}}

The result is `landscape.png`, approximately 3508 by 2480 pixels.
<br><br>

**Q: Can I render LaTeX directly from a string or an in‑memory stream?**  
<br>
**A:** Encode a complete LaTeX document into a binary `BytesIO` stream and pass it to `TeXJob` with `TeXConfig.object_latex`. Set `ASPOSE_TEX_OUTPUT_DIR` to the output folder, or use the default `output`. Apply a license first as described in [Licensing](/tex/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

The example creates `texput.xps` and `texput.log`. See [Other ways to provide main input](/tex/python-net/other-ways-of-main-input/) for details.
<br><br>

**Q: Where can I find official documentation, code samples, and support channels?**  
<br>
**A:**  Check the next resources:

- [Official Documentation ](https://docs.aspose.com/tex/python-net/)
- [Getting Started Guide](https://docs.aspose.com/tex/python-net/getting-started/)
- [Code Samples & GitHub Gists](https://github.com/aspose-com-gists)
- [Support Forum](https://forum.aspose.com/c/tex/)
- Issue Tracker (private for customers) - Provided after purchase 

All examples are available in both Python and C#; the C# code can be directly translated thanks to pythonnet.  
