---
translation: true
template: /templates/_template-python-net.md
title: Látex a XPS | Aspose.TeX para Python
linktitle: Látex a XPS
weight: 12
url: /python-net/latex-to-xps/
description: La solución API Aspose.TeX para Python proporciona una funcionalidad de conversión para convertir archivos LaTeX al formato XPS.
lastmod: "2024-10-30"
---

{{<section overview>}}

Otro formato de destino es [**XPS**](https://docs.aspose.com/page/net/what-is-xps-file/). Un archivo [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) es esencialmente un paquete ZIP que contiene todo el contenido paginado de un documento, junto con los metadatos necesarios para su correcta visualización por parte de visores específicos (como Windows XPS Viewer) e impresión. El paquete consta de varios archivos, algunos de los cuales son binarios y contienen recursos como imágenes, fuentes y perfiles ICC. Otros son archivos XML en esquemas específicos, incluidos archivos que contienen los datos del documento. Los datos del documento se dividen en varios archivos, y cada archivo representa una página individual del documento. Estos archivos constan de un único elemento de página y un árbol de elementos secundarios, incluidos *Canvas*, *Path* y *Glyphs*. El elemento *Canvas* es un elemento de agrupación que puede contener otros *Canvases*, *Paths* y *Glyphs*, y controla la apariencia de todos los elementos secundarios como un grupo. Los elementos *Path* se utilizan para definir rutas de gráficos vectoriales, mientras que los elementos *Glyphs* se utilizan para definir contenido textual. Los tres elementos tienen propiedades que definen varios aspectos de la apariencia.

Existe la biblioteca [**Aspose.Page**](https://products.aspose.com/page/), que ofrece una API para manipular documentos XPS y también permite la conversión de estos documentos a formatos PDF y de imágenes rasterizadas.

## Conversión de LaTeX a XPS

El proceso de conversión de LaTeX a XPS es igualmente sencillo, similar a la [conversión a formatos de imágenes rasterizadas](/tex/{{lang.url-fragment}}python-net/latex-to-image/). Sin embargo, requiere configurar [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) en una instancia de la clase [XpsSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/) (ya sea de forma predeterminada o explícitamente) y cambiar el dispositivo a una instancia de la clase [XpsDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### Una forma alternativa de escribir el archivo XPS de salida principal

Hay un constructor alternativo disponible para la clase *XpsDevice*, que permite obtener el archivo XPS resultante de una manera diferente.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

El efecto es el mismo que obtenemos [aquí](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**También puede explorar la [aplicación web gratuita para la conversión de LaTeX a XPS](https://products.aspose.app/tex/conversion/latex-to-xps), que se desarrolla utilizando [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**