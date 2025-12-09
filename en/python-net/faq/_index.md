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
**A:** 

```python
import aspose.tex as tex

doc = tex.Document("sample.tex")          # load LaTeX source
doc.save("sample.pdf", tex.SaveFormat.PDF)  # write PDF
```  

You can also create a document from a string (`tex.Document(latex_source)`) or an in‑memory stream.  
<br><br>

**Q: Which output formats can Aspose TeX for Python generate?**  
<br>
**A:** PDF, XPS, SVG, PNG, JPEG, BMP, and TIFF. Each format can be controlled via specific `SaveOptions` objects (e.g., `PdfSaveOptions`, `ImageSaveOptions`, `SvgSaveOptions`).  
<br><br>

**Q: How do I embed custom fonts into the generated PDF?**  
<br>
**A:** Register a custom font folder before rendering:

```python
font_src = tex.FontSource()
font_src.add_folder(r"C:\MyFonts")   # or "/home/user/fonts"
tex.FontSettings.set_default_sources([font_src])
doc.save("out.pdf", tex.PdfSaveOptions())
```  

By default all used fonts are embedded; disable embedding with `PdfSaveOptions.embed_fonts = False`.  
<br><br>

**Q: What LaTeX packages and classes are supported out of the box?**  
<br>
**A:** More than 300 core packages (e.g., `amsmath`, `graphicx`, `hyperref`, `xcolor`, `tikz`, `pgfplots`, `booktabs`) and common classes (`article`, `report`, `book`, `memoir`).  
<br><br>

**Q: How can I use a third‑party `.sty` or class file that is not built‑in?**  
<br>
**A:** Place the `.sty`/`.cls` file in the same directory as the source document or add its folder to the document’s resource loaders:

```python
doc = tex.Document("mydoc.tex")
doc.resource_loaders.append(tex.FolderResourceLoader(r"C:\MyLatexPackages"))
```  

The engine will load the custom files automatically on the next conversion.  
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
**A:** Apply the license once per process:

```python
import aspose.tex as tex
tex.License().set_license("Aspose.Total.NET.lic")
```  

Licensing options: Free Trial (10‑page limit, no watermark), Developer/Single‑Machine (unlimited pages on one machine), Enterprise/Multi‑Seat (unlimited across organization with priority support).  
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
**A:** Use the `PageSetup` and `ImageSaveOptions` objects:

```python
doc.page_setup.size = tex.PageSize.A4
doc.page_setup.orientation = tex.PageOrientation.LANDSCAPE

opts = tex.ImageSaveOptions()
opts.dpi = 300
doc.save("out.png", opts)
```  
<br><br>

**Q: Can I render LaTeX directly from a string or an in‑memory stream?**  
<br>
**A:** Absolutely. Pass the LaTeX source string to the constructor or use a `io.BytesIO` stream:

```python
src = r"\section{Hello}\textbf{World}"
doc = tex.Document(src)          # from string
# or
stream = io.BytesIO(src.encode())
doc = tex.Document(stream)       # from stream
```  
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
