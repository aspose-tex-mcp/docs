---
translation: true
template: /templates/_template-net.md
title: Látex a XPS | .NET
linktitle: Látex a XPS
weight: 12
url: /net/latex-to-xps/
description: La funcionalidad de conversión de la solución API Aspose.TeX para .NET permite convertir archivos LaTeX al formato XPS.
lastmod: "2026-11-02"
---

{{<section overview>}}


Otro formato de destino es [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un archivo **XPS** es físicamente un paquete ZIP que contiene el contenido paginado de un documento, junto con los metadatos necesarios para que visores específicos (como Windows XPS Viewer) lo muestren correctamente y lo impriman. Todos los datos de un paquete están representados por archivos. Algunos de ellos son binarios y contienen recursos como imágenes, fuentes y perfiles ICC. Otros son archivos XML en varios esquemas específicos. Estos últimos incluyen archivos que contienen los datos del documento en sí. Los datos del documento constan de un conjunto de archivos: cada archivo contiene datos para una página individual del documento. Dichos archivos constan de un único elemento de página y un árbol de elementos secundarios: *Canvas*, *Path* y *Glyphs*. *Canvas* es un elemento de agrupación que puede contener otros *Canvases*, *Paths* y *Glyphs*. Sirve para controlar la apariencia de todos los elementos secundarios como grupo. Los elementos *Path* se utilizan para definir rutas de gráficos vectoriales. Y los elementos *Glifos* se utilizan para definir el contenido textual. Los tres elementos tienen propiedades para definir varios aspectos de la apariencia.

Existe la biblioteca [**Aspose.Page**](https://products.aspose.com/page/) que proporciona una API para manipular documentos XPS, así como convertirlos a formatos PDF y de imágenes rasterizadas.

## Cómo convertir LaTeX a XPS

La conversión de LaTeX a XPS es tan simple como la [conversión a formatos de imagen rasterizada](/tex/{{lang.url-fragment}}net/latex-to-image/), excepto que [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) DEBE establecerse en una instancia de clase [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (de forma predeterminada o explícitamente) y el dispositivo DEBE cambiarse a una instancia de la clase [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

**Ejemplo de conversión más sencillo**

El siguiente ejemplo muestra cómo convertir un archivo LaTeX a XPS en pocos pasos:

1. Cree `TeXOptions` para el formato ObjectLaTeX con `TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX)`.
2. Especifique el directorio de trabajo de salida, por ejemplo, un `OutputFileSystemDirectory`.
3. Establezca `SaveOptions` en una instancia de `XpsSaveOptions`.
4. Ejecute un `TeXJob` para el archivo fuente `.tex` con un `XpsDevice`. El archivo XPS se escribe en el directorio de trabajo de salida.

Este código muestra la forma más directa de generar un archivo XPS desde LaTeX.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Una forma alternativa de escribir el archivo XPS de salida principal

Hay otro constructor de la clase [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), que nos permite obtener el archivo XPS resultante de una forma alternativa.

**Ejemplo de conversión alternativo**

Este fragmento muestra el uso del constructor `XpsDevice` que acepta un `Stream`. Los pasos son:

1. Abra la secuencia en la que se escribirá el documento XPS (aquí, una secuencia de archivo; un `MemoryStream` funciona igual).
2. Cree `TeXOptions`, especifique el directorio de trabajo de salida y establezca `SaveOptions` en una instancia de `XpsSaveOptions`, como en el ejemplo anterior.
3. Ejecute un `TeXJob` con un `XpsDevice` creado con la secuencia. El documento XPS se escribe en la secuencia; los demás archivos de salida, como la transcripción, siguen yendo al directorio de trabajo de salida.

Este método es útil cuando necesita escribir el documento XPS en una secuencia de su elección, por ejemplo, para mantenerlo en memoria o enviarlo por red.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

El efecto es el mismo que obtenemos [aquí](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-xps) gratuita de conversión de LaTeX a XPS creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**
