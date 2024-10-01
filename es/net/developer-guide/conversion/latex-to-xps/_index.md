---
translation: true
template: /templates/_template-net.md
title: Látex a XPS | Aspose.TeX para .NET
linktitle: Látex a XPS
weight: 12
url: /net/latex-to-xps/
aliases: /net/otros-formatos-de-objetivo/
description: La funcionalidad de conversión de la solución API Aspose.TeX para .NET permite convertir archivos LaTeX al formato XPS. A continuación se muestran algunos ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}


Otro formato de destino es [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un archivo **XPS** es físicamente un paquete ZIP que contiene el contenido paginado de un documento, junto con los metadatos necesarios para que visores específicos (como Windows XPS Viewer) lo muestren correctamente y lo impriman. Todos los datos de un paquete están representados por archivos. Algunos de ellos son binarios y contienen recursos como imágenes, fuentes y perfiles ICC. Otros son archivos XML en varios esquemas específicos. Estos últimos incluyen archivos que contienen los datos del documento en sí. Los datos del documento constan de un conjunto de archivos: cada archivo contiene datos para una página individual del documento. Dichos archivos constan de un único elemento de página y un árbol de elementos secundarios: *Canvas*, *Path* y *Glyphs*. *Canvas* es un elemento de agrupación que puede contener otros *Canvases*, *Paths* y *Glyphs*. Sirve para controlar la apariencia de todos los elementos secundarios como grupo. Los elementos *Path* se utilizan para definir rutas de gráficos vectoriales. Y los elementos *Glifos* se utilizan para definir el contenido textual. Los tres elementos tienen propiedades para definir varios aspectos de la apariencia.

Existe la biblioteca [**Aspose.Page**](https://products.aspose.com/page/) que proporciona una API para manipular documentos XPS, así como convertirlos a formatos PDF y de imágenes rasterizadas.

## Cómo convertir LaTeX a XPS

La conversión de LaTeX a XPS es tan simple como la [conversión a formatos de imagen rasterizada](/tex/{{lang.url-fragment}}net/latex-to-image/), excepto que [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) DEBE establecerse en una instancia de clase [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (de forma predeterminada o explícitamente) y el dispositivo DEBE cambiarse a una instancia de la clase [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.cs" >}}

### Una forma alternativa de escribir el archivo XPS de salida principal

Hay otro constructor de la clase [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), que nos permite obtener el archivo XPS resultante de una forma alternativa.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.cs" >}}

El efecto es el mismo que obtenemos [aquí](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-xps) gratuita de conversión de LaTeX a XPS creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**