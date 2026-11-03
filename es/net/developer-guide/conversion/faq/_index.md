---
translation: true
template: /templates/_template-net.md
title: Convertidores Aspose.TeX para .NET – Preguntas frecuentes
linktitle: Preguntas frecuentes
type: docs
weight: 90
url: /net/conversion/faq/
description: Preguntas frecuentes sobre la conversión de archivos TeX y LaTeX con Aspose.TeX para .NET, incluidos los formatos admitidos, el código de conversión, la salida a secuencias, las opciones de imagen, los paquetes, el modo de evaluación y los requisitos de ejecución.
keywords: Aspose.TeX, .NET, FAQ, conversión de LaTeX, LaTeX a PDF, LaTeX a XPS, LaTeX a SVG, LaTeX a PNG, TeXJob, licencias, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**P: ¿Qué formatos de entrada y salida admite Aspose.TeX para .NET?**

**R:** Aspose.TeX compone documentos TeX y LaTeX. El archivo de entrada principal puede proceder de un archivo, una secuencia o un terminal; los archivos que incluye pueden proceder de una carpeta o de un archivo ZIP. Hay API independientes que renderizan una sola fórmula matemática de LaTeX o un fragmento de LaTeX. Los formatos de salida son PDF, XPS, SVG, PNG, JPEG, BMP y TIFF. Consulte [Formatos de archivo admitidos](/tex/{{lang.url-fragment}}net/supported-file-formats/).
<br><br>

**P: ¿Puede Aspose.TeX convertir LaTeX a Word (DOCX) o HTML?**

**R:** No. Aspose.TeX solo genera PDF, XPS, SVG e imágenes rasterizadas. Si necesita otro formato, convierta la salida PDF con una biblioteca que lo admita.
<br><br>

**P: ¿Cómo convierto un archivo LaTeX a PDF en C#?**

**R:** Cree `TeXOptions` para el formato ObjectLaTeX, establezca el directorio de salida y `PdfSaveOptions`, y ejecute un `TeXJob` con un `PdfDevice`:

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

El resultado se escribe en el directorio de trabajo de salida con el nombre del trabajo. Consulte [Látex a PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/).
<br><br>

**P: ¿Cómo elijo el formato de salida?**

**R:** Establezca `TeXOptions.SaveOptions` y pase el dispositivo correspondiente a `TeXJob`:

| Formato | Opciones de guardado | Dispositivo |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG, JPEG, BMP, TIFF | `PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions` | `ImageDevice` |

Consulte [Látex a XPS](/tex/{{lang.url-fragment}}net/latex-to-xps/) y [LaTeX a imagen](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**P: ¿Puedo obtener el resultado en memoria en lugar de en un archivo?**

**R:** Sí. `PdfDevice` y `XpsDevice` tienen constructores que aceptan un `Stream` en el que se escribe el documento. `ImageDevice` guarda las páginas renderizadas en su propiedad `Result` como una matriz de matrices de bytes, una por página. Para leer la entrada principal desde una secuencia, pase la secuencia al constructor de `TeXJob`. Consulte [Látex a PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) y [Otras formas de proporcionar el archivo de entrada TeX principal](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/).
<br><br>

**P: ¿Cómo controlo la resolución y la calidad de las imágenes?**

**R:** Use las propiedades de las opciones de guardado de imágenes:

- `Resolution`: resolución de la imagen en DPI.
- `SmoothingMode` e `InterpolationMode`: calidad de renderizado.
- `TiffSaveOptions.Compression` y `TiffSaveOptions.Multipage`: compresión TIFF y si todas las páginas van a un solo archivo (el paquete `Aspose.TeX.Drawing` todavía no admite TIFF de varias páginas).

Por ejemplo, `new PngSaveOptions { Resolution = 300 }` genera imágenes PNG de 300 DPI. Consulte [LaTeX a imagen](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**P: ¿Cómo sé si la conversión se ha realizado correctamente?**

**R:** `TeXJob.Run()` devuelve un valor `TeXJobResult`: `Spotless`, `WarningIssued`, `ErrorMessageIssued` o `FatalErrorStop`. Los detalles se escriben en el archivo de transcripción (`.log`) del directorio de salida y en el terminal de salida. Consulte [Interfaz de salida de Aspose.TeX](/tex/{{lang.url-fragment}}net/aspose-tex-output/).
<br><br>

**P: ¿Necesito una instalación de LaTeX (por ejemplo, MiKTeX) en el servidor?**

**R:** No. Aspose.TeX es una biblioteca .NET independiente con su propio motor TeX, formato LaTeX y fuentes. No requiere ninguna distribución TeX externa.
<br><br>

**P: ¿Qué paquetes de LaTeX puedo usar?**

**R:** Aspose.TeX incluye un conjunto de paquetes LaTeX integrados; consulte [Paquetes LaTeX integrados](/tex/{{lang.url-fragment}}net/embedded-packages/). Para usar otros paquetes, coloque sus archivos en una carpeta o un archivo ZIP y especifíquelo como `TeXOptions.RequiredInputDirectory`; consulte [Paquetes externos de LaTeX](/tex/{{lang.url-fragment}}net/external-latex-packages/).
<br><br>

**P: ¿Puedo renderizar una sola fórmula o un fragmento de LaTeX en lugar de un documento completo?**

**R:** Sí. Use `PngMathRenderer` o `SvgMathRenderer` para fórmulas matemáticas y `PngFigureRenderer` o `SvgFigureRenderer` para fragmentos arbitrarios de LaTeX. Devuelven el tamaño de la imagen renderizada. Consulte [Renderizado de fórmulas matemáticas en LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) y [Renderizado de figuras en LaTeX](/tex/{{lang.url-fragment}}net/latex-figure-rendering/).
<br><br>

**P: ¿Cuáles son los requisitos de ejecución?**

**R:**

- Paquete `Aspose.TeX`: Windows (x64/x86); .NET Framework 4.0 o posterior, .NET Standard 2.0, .NET 6 o posterior.
- Paquete `Aspose.TeX.Drawing`: Windows, Linux y macOS (x64/Arm64); .NET Framework 4.7.2 o posterior, .NET 7 o posterior.
- No se necesitan bibliotecas nativas adicionales. En Linux, la salida en XPS y SVG requiere ICU. Consulte [Requisitos del sistema](/tex/{{lang.url-fragment}}net/system-requirements/) y [Linux, macOS y Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).
<br><br>

**P: ¿Cuáles son las limitaciones de la versión de evaluación?**

**R:** Sin licencia, Aspose.TeX funciona en modo de evaluación: genera como máximo cuatro páginas de un documento, y las páginas llevan una marca de agua de evaluación. La versión de evaluación es el mismo paquete; para evaluarlo sin limitaciones, solicite una [licencia temporal de 30 días](https://purchase.aspose.com/temporary-license/). Consulte [Licencias](/tex/{{lang.url-fragment}}net/licensing/).
<br><br>

**P: ¿Cómo aplico una licencia en el código?**

**R:** Aplique la licencia una vez, antes de la primera conversión:

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

También puede cargar la licencia desde una secuencia o usar una licencia medida (metered). Consulte [Licencias](/tex/{{lang.url-fragment}}net/licensing/). Para conocer los precios, consulte la [página de precios de Aspose.TeX](https://purchase.aspose.com/pricing/tex/).
<br><br>

**P: ¿Dónde puedo encontrar documentación de la API, ejemplos y soporte?**

**R:**

- [Guía para desarrolladores](https://docs.aspose.com/tex/net/)
- [Referencia de la API](https://reference.aspose.com/tex/net/)
- [Foro de la comunidad](https://forum.aspose.com/c/tex/)
<br><br>
