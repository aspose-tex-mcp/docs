---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX Converters for .NET – FAQ
linktitle: FAQ
type: docs
weight: 90
url: /net/conversion/faq/
description: Frequently asked questions about Aspose.TeX for .NET covering supported formats, conversion examples, licensing, batch processing, image options, and more.
keywords: Aspose.TeX, .NET, FAQ, LaTeX conversion, PDF, Word, HTML, image export, licensing, batch conversion, API, documentation
lastmod: "2025-12-04"
---

{{<section overview>}}

<br><br>

**Q: What source and output formats does Aspose.TeX for .NET support?**  

**A:** Aspose.TeX can read LaTeX source files (`*.tex`), plain‑text LaTeX snippets, and inline math (`$$…$$`, `\(...\)`, `\[…\]`). It can output to PDF, XPS, SVG, PNG, JPEG, BMP, TIFF, DOCX, ODT, HTML‑5 (with CSS), and EPUB (via PDF→EPUB).  
<br><br>

**Q: How do I convert a `.tex` file to PDF in C#?**  

**A:** 
```csharp
using Aspose.TeX;

// Load LaTeX source
var tex = new TexDocument(@"C:\Input\sample.tex");

// Convert to PDF
using (var pdf = tex.ToPdf())
{
    pdf.Save(@"C:\Output\sample.pdf");
}
```  
<br><br>

**Q: Can I directly convert LaTeX to Word (DOC/DOCX) or HTML?**  

**A:** Yes. Use `TexDocument.ToWord()` for DOC/DOCX and `TexDocument.ToHtml()` for clean HTML‑5 output (styles are inlined by default).  
<br><br>

**Q: Are mathematical equations rendered accurately?**  

**A:** The built‑in LaTeX math parser renders equations as high‑quality vector graphics in PDF/SVG or as anti‑aliased bitmaps in PNG/JPEG. Full support is provided for complex environments such as `align`, `eqnarray`, `amsmath`, and `tikz`.  
<br><br>

**Q: Do I need a LaTeX installation (e.g., MiKTeX) on the server?**  

**A:** No. Aspose.TeX is a completely standalone .NET library and does not require any external TeX distribution.  
<br><br>

**Q: What are the runtime requirements?**  

**A:** 

• .NET Framework 4.6 or later **or** .NET Core 2.1 +/ .NET 5+.  
• Windows x64/x86, Linux (glibc 2.12+), macOS (Catalyst).  
• No additional native binaries are needed.  
<br><br>

**Q: How do I control image output resolution and quality?**  

**A:** 
```ccsharp
var opts = new ImageSaveOptions
{
    Resolution = 300,   // DPI
    Quality = 95        // JPEG quality (0‑100)
};
var img = tex.ToPng(opts);
img.Save(@"C:\Output\sample.png");
```  
<br><br>

**Q: Is there a free trial or evaluation version?**  

**A:** A 30‑day evaluation DLL is available from the Aspose website. It includes the full feature set but limits each conversion to 500 KB of input. No license key is required for the trial build.  
<br><br>

**Q: How is licensing handled in code?**  

**A:** 
```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```  
<br><br>

**Q: Can I perform batch conversions (multiple `.tex` files) efficiently?** 

**A:** Yes. Create a `TexDocument` per file or reuse a single instance for multiple fragments. The library is thread‑safe for read‑only operations, so you can parallelise work with `Parallel.ForEach`.  
<br><br>

**Q: Do I get any support for custom packages or user‑defined macros?**  

**A:** Core support includes common packages such as `amsmath`, `amssymb`, `graphicx`, `hyperref`, `tikz`, etc. For unsupported packages you can pre‑process LaTeX yourself or use the `ExternalPackageResolver` API to load custom `.sty` files at runtime.  
<br><br>

**Q: How do I add watermarks or page numbers to the generated PDF?**  

**A:** After conversion you can treat the result as an `Aspose.Pdf.PdfDocument`. Example:  
```csharp
var pdf = tex.ToPdf();
pdf.AddWatermarkText("Confidential");
pdf.AddPageNumbers();
pdf.Save(@"C:\Output\sample.pdf");
```  
The two Aspose libraries share the same namespace hierarchy, making interoperability seamless.  
<br><br>

**Q: What is the pricing model?**  

**A:** 

• Developer Small Business: $999 / year (up to 5 developers).  
• Developer OEM: perpetual license starting at $3 499 / year (includes source code).

Volume discounts and site licenses are available on request.  
<br><br>

**Q: Where can I find detailed API documentation and examples?**  
<br>
**A:** 

• [Official docs](https://docs.aspose.com/tex/net/)
• [GitHub samples](https://github.com/aspose-tex/Aspose.TeX-net) 
• [Community forum](https://forum.aspose.com/c/tex/31)  
<br><br>