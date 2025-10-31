---
translation: true
template: /templates/_template-net.md
title: Látex a XPS | .NET
linktitle: Látex a XPS
weight: 12
url: /net/latex-to-xps/
description: La funcionalidad de conversión de la solución API Aspose.TeX para .NET permite convertir archivos LaTeX al formato XPS.
lastmod: "2024-10-30"
---

{{<section overview>}}


Otro formato de destino es [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un archivo **XPS** es físicamente un paquete ZIP que contiene el contenido paginado de un documento, junto con los metadatos necesarios para que visores específicos (como Windows XPS Viewer) lo muestren correctamente y lo impriman. Todos los datos de un paquete están representados por archivos. Algunos de ellos son binarios y contienen recursos como imágenes, fuentes y perfiles ICC. Otros son archivos XML en varios esquemas específicos. Estos últimos incluyen archivos que contienen los datos del documento en sí. Los datos del documento constan de un conjunto de archivos: cada archivo contiene datos para una página individual del documento. Dichos archivos constan de un único elemento de página y un árbol de elementos secundarios: *Canvas*, *Path* y *Glyphs*. *Canvas* es un elemento de agrupación que puede contener otros *Canvases*, *Paths* y *Glyphs*. Sirve para controlar la apariencia de todos los elementos secundarios como grupo. Los elementos *Path* se utilizan para definir rutas de gráficos vectoriales. Y los elementos *Glifos* se utilizan para definir el contenido textual. Los tres elementos tienen propiedades para definir varios aspectos de la apariencia.

Existe la biblioteca [**Aspose.Page**](https://products.aspose.com/page/) que proporciona una API para manipular documentos XPS, así como convertirlos a formatos PDF y de imágenes rasterizadas.

## Cómo convertir LaTeX a XPS

La conversión de LaTeX a XPS es tan simple como la [conversión a formatos de imagen rasterizada](/tex/{{lang.url-fragment}}net/latex-to-image/), excepto que [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) DEBE establecerse en una instancia de clase [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (de forma predeterminada o explícitamente) y el dispositivo DEBE cambiarse a una instancia de la clase [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

**Ejemplo de conversión más sencillo**

El siguiente ejemplo muestra cómo convertir un archivo LaTeX a XPS en pocos pasos:

1. Cree una instancia `TexDocument`.
2. Cargue el archivo fuente `.tex` mediante `TexDocument.Load`.
3. (Opcional) Configure `XpsSaveOptions`, como la configuración de compresión.
4. Guarde el documento en XPS llamando a `document.Save` con un `XpsDevice`.

Este código muestra la forma más directa de generar un archivo XPS desde LaTeX.

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Una forma alternativa de escribir el archivo XPS de salida principal

Hay otro constructor de la clase [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), que nos permite obtener el archivo XPS resultante de una forma alternativa.

**Ejemplo de conversión alternativo**

Este fragmento muestra el uso del constructor `XpsDevice` que acepta un `Stream`. Los pasos son:

1. Cree un `TexDocument` y cargue el archivo fuente LaTeX.
2. Cree un `MemoryStream` para almacenar la salida XPS. 3. Cree una instancia de `XpsDevice` con la secuencia.
4. Guarde el documento en el dispositivo para poder usar la secuencia (por ejemplo, enviarlo por red o almacenarlo en una base de datos).

Este método es útil cuando necesita los datos XPS en memoria en lugar de como un archivo en disco.

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

El efecto es el mismo que obtenemos [aquí](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-xps) gratuita de conversión de LaTeX a XPS creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**
