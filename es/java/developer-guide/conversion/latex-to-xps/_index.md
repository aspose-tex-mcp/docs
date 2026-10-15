---
translation: true
template: /templates/_template-java.md
title: Látex a XPS | Java
linktitle: Látex a XPS
weight: 12
url: /java/latex-to-xps/
description: La funcionalidad de conversión de la solución API Aspose.TeX para Java le permite convertir archivos LaTeX al formato XPS. Conozca los ejemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}


Otro formato de destino es [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un archivo **XPS** es físicamente un paquete ZIP que contiene contenido paginado de un documento, así como los metadatos necesarios para que visores específicos (como Windows XPS Viewer) lo muestren correctamente y lo impriman. Todos los datos de un paquete están organizados como archivos en directorios. Algunos de ellos contienen recursos como imágenes, fuentes y perfiles ICC. Otros son archivos XML en varios esquemas específicos. Estos últimos incluyen archivos que contienen los datos del documento en sí. Los datos del documento son un conjunto de archivos: cada archivo contiene datos para una página individual del documento. Dichos archivos constan de un único elemento de página y un árbol de elementos secundarios: *Canvas*, *Path* y *Glyphs*. *Canvas* es un elemento de agrupación que puede contener otros *Canvases*, *Paths* y *Glyphs*. Su propósito es controlar la apariencia de todos los elementos secundarios como grupo. Los elementos *Path* se utilizan para definir rutas de gráficos vectoriales. Y los elementos *Glifos* se utilizan para definir el contenido del texto. Los tres elementos tienen propiedades para definir varios aspectos de la apariencia.

Existe la biblioteca [**Aspose.Page**](https://products.aspose.com/page/) que proporciona una API para manipular documentos XPS, así como convertirlos a formatos PDF y de imágenes rasterizadas.

## Cómo convertir LaTeX a XPS

La conversión a XPS es tan simple como la [conversión a formatos de imagen rasterizada](/tex/{{lang.url-fragment}}java/latex-to-image/), excepto que además de [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), tenemos que usar una instancia de la clase [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) .

Establezca `inputFile` en la ruta completa de su archivo LaTeX, como `hello-world.ltx`, y `outputDirectory` en una carpeta de salida existente. Importe las clases de `com.aspose.tex` y `com.aspose.tex.rendering` utilizadas en el fragmento. El método que realiza la llamada debe capturar o declarar las excepciones. Aplique una licencia como se describe en la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación. El ejemplo utiliza un procesamiento no interactivo y cierra sus recursos de salida. Para el archivo de entrada independiente `hello-world.ltx`, la salida predeterminada es `hello-world.xps`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### Una forma alternativa de escribir el archivo XPS de salida principal

Existe otro constructor de la clase [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-), que nos permite obtener el archivo XPS resultante de una forma alternativa.

Utilice los mismos valores de `inputFile` y `outputDirectory` que arriba. Establezca `xpsFile` en un `java.nio.file.Path`, por ejemplo `Paths.get(outputDirectory, "any-name.xps")`. Además de las clases de Aspose.TeX, importe `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path` y `java.nio.file.Paths`. El flujo controla el destino del archivo XPS; los archivos auxiliares se escriben en `outputDirectory`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

El efecto es el mismo que obtenemos [aquí](/tex/{{lang.url-fragment}}java/latex-to-pdf/#una-forma-alternativa-de-escribir-el-archivo-pdf-de-salida-principal).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-xps) gratuita de conversión de LaTeX a XPS creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) es la página de la versión de Java.**