---
translation: true
template: /templates/_template-java.md
title: LaTeX a la imagen | Java
linktitle: LaTeX a imagen
weight: 10
url: /java/latex-to-image/
keywords: LaTeX a png, LaTeX png, LaTeX a imagen, imagen de LaTeX, LaTeX a jpg, LaTeX jpg, LaTeX a jpeg, LaTeX jpeg, LaTeX a tiff, LaTeX tiff, LaTeX a bmp, LaTeX bmp
description: Para convertir TeX a formatos de imagen utilizando la Aspose.TeX paraJava, aprenda este artículo que describe cómo hacerlo y los ejemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

**Aspose.TeX for Java** provides features for converting LaTeX files to a number of raster image formats.

## Cómo convertir LaTeX a PNG

Echemos un vistazo más de cerca al código Java que proporciona la forma más sencilla de convertir LaTeX al formato PNG.

Establezca `inputFile` en la ruta completa de su archivo LaTeX, como `hello-world.ltx`, y `outputDirectory` en una carpeta de salida existente. Importe las clases de `com.aspose.tex` y `com.aspose.tex.rendering` utilizadas en el fragmento. El método que realiza la llamada debe capturar o declarar las excepciones. Aplique una licencia como se describe en la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación. El ejemplo utiliza un procesamiento no interactivo y cierra sus recursos de salida. El ejemplo PNG utiliza 300 DPI. Para la entrada de una página `hello-world.ltx`, los archivos de salida automáticos son `hello-world.png`, `hello-world.jpg`, `hello-world.tif`, `hello-world.bmp` o `hello-world.svg`, según el formato elegido.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToPNG-Simplest.java" >}}

Entonces, lo primero que debemos hacer (a veces no lo primero, como descubriremos más adelante) es crear una instancia de la clase [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). El único método estático que hace esto es [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#consoleAppOptions-com.aspose.tex.TeXConfig-), así que no nos molestemos con el significado de su nombre. El método toma la [instancia de objectLaTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectLaTeX--) de la clase [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/), que es exactamente adecuada para convertir un [archivo LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuración indica al motor Object TeX que cargue el formato Object LaTeX y que esté listo para aceptar el archivo LaTeX. El formato Object LaTeX es en realidad solo el formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), excepto que utiliza primitivas específicas de [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar las métricas de la página.

La primera de las opciones requeridas es [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) que define el espacio o área donde se escribirá la salida TeX. [Aquí](/tex/{{lang.url-fragment}}java/aspose-tex-output/) están los detalles sobre el concepto de directorio de salida en **Aspose.TeX para Java**. En este ejemplo, utilizamos la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/), que nos permite escribir la salida en el directorio o carpeta especificado.

La segunda opción es una instancia de clase [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/saveoptions/) que controlará la transformación del [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato de destino. Dado que estamos convirtiendo LaTeX a PNG, es la instancia de clase [PngSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/pngsaveoptions/), que nos permite especificar la resolución de las imágenes de salida.

A continuación, necesitamos crear una instancia de la clase [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/). Al querer convertir un archivo LaTeX almacenado en el sistema de archivos, utilizamos [esta](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) versión del constructor. Deberíamos especificar la ruta completa al archivo. De lo contrario, el motor lo buscará en el directorio actual (que está definido [aquí](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) y lo más probable es que no lo encuentre. No obstante, podremos omitir la extensión si nuestro archivo tiene la *.tex*. El motor lo agregará automáticamente. El segundo argumento del constructor es una instancia de clase [Dispositivo](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/device/). Dado que estamos convirtiendo LaTeX a PNG, es una instancia de clase [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/imagedevice/) (que es común a todos los formatos de imagen admitidos). Como último argumento, pasamos las opciones de conversión preparadas recientemente.

Todo lo que tenemos que hacer ahora es [ejecutar](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#run--) el trabajo.

Independientemente de si la ejecución fue exitosa o no, el primer resultado que veremos será la salida del terminal. En caso de éxito, se verá así:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Encontraremos otros productos de ejecución del motor en la carpeta que especificamos como directorio de salida. Esos serán el archivo de transcripción (.log) y, **¡Voila!**, los archivos de imagen PNG de salida principal.

## Una forma alternativa de escribir los archivos PNG de salida principales

Hay otra forma de obtener datos de imagen como una matriz de matrices de bytes; cada matriz en la segunda dimensión representa datos de imagen para una página separada.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToPNG-Alternative.java" >}}

El ejemplo manual también requiere `java.nio.file.Files` y `java.nio.file.Paths`. Guarda los datos de las páginas de `ImageDevice.getResult()` como `page-1.png`, `page-2.png`, etc. Al establecer `deviceWritesImages(false)`, se desactiva la salida PNG automática y las páginas guardadas manualmente no se duplican en el directorio de salida. Esto difiere de la [salida PDF mediante un flujo](/tex/{{lang.url-fragment}}java/latex-to-pdf/#una-forma-alternativa-de-escribir-el-archivo-pdf-de-salida-principal), donde el flujo define el destino de un único documento PDF.

## Acerca de las opciones de entrada

En caso de que nuestro archivo de entrada principal requiera dependencias, por ejemplo, paquetes, que no están incluidos en el sistema LaTeX básico y los paquetes compatibles, DEBEMOS configurar la opción [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) de la misma manera que configuramos [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--). opción y coloque las dependencias en ese directorio. Las dependencias pueden organizarse arbitrariamente en subdirectorios. En caso de que tengamos nuestros propios archivos para incluir durante el proceso de composición tipográfica, digamos archivos de gráficos externos, DEBEMOS también configurar [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) usando la ruta a la ubicación donde se recopilan esos archivos. También podemos colocar el archivo de entrada principal en algún lugar dentro del directorio de entrada y pasar la ruta relativa al constructor de `TeXJob` (o no especificar ninguna ruta si el archivo de entrada principal está en la raíz). [Aquí](/tex/{{lang.url-fragment}}java/aspose-tex-input/) se encuentran los detalles sobre el concepto de directorio de entrada en **Aspose.TeX para Java** y las implementaciones proporcionadas.

Otras opciones de trabajo en TeX se analizan [aquí](/tex/{{lang.url-fragment}}java/other-options/).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-png) gratuita de conversión de LaTeX a PNG creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) está la página de la versión de Java.**

A continuación, analizamos la conversión de LaTeX a otros formatos de imágenes rasterizados compatibles. No entraremos en detalles sólo porque en realidad no hay ningún detalle. La única diferencia está en el tipo de propiedad [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) en las opciones de conversión.

## Cómo convertir LaTeX a JPG

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToJPEG.java" >}}

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-jpg) gratuita de conversión de LaTeX a JPG creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) es la página de la versión de Java.**

## Cómo convertir LaTeX a TIFF

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToTIFF.java" >}}

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-tiff) gratuita de conversión de LaTeX a TIFF creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) es la página de la versión de Java.**

## Cómo convertir LaTeX a BMP

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToBMP.java" >}}

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-bmp) gratuita de conversión de LaTeX a BMP creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) es la página de la versión de Java.**


## Cómo convertir LaTeX a SVG

Y otro formato de destino admitido es [**SVG**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** es un formato de imagen vectorial basado en XML para definir gráficos bidimensionales, con soporte para interactividad y animación.

Las imágenes **SVG** se definen en un formato de gráficos vectoriales y se almacenan en archivos de texto XML. Esto significa que las imágenes **SVG** se pueden escalar en tamaño sin pérdida de calidad, y los archivos **SVG** se pueden buscar, indexar, codificar y comprimir. Los archivos de texto XML se pueden crear y editar con editores de texto o editores de gráficos vectoriales. Son renderizados por los navegadores web más utilizados.

Además, existe la biblioteca [**Aspose.SVG**](https://products.aspose.com/svg/) que tiene varias características basadas en el formato **SVG**. Estos incluyen crear, cargar, editar y convertir documentos **SVG**.

La conversión a SVG es tan simple como la [conversión a formatos de imagen rasterizada](/tex/{{lang.url-fragment}}java/latex-to-image/), excepto que además de [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), tenemos que cambiar el dispositivo a una instancia de [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/svgdevice/) clase.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToSVG-Simplest.java" >}}

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-svg) gratuita de conversión de LaTeX a SVG creada en base a [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) es la página de la versión de Java.**