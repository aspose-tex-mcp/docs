---
translation: true
template: /templates/_template-java.md
title: Látex a PDF | Java
linktitle: Látex a PDF
weight: 11
url: /java/latex-to-pdf/
keywords: LaTeX a pdf, LaTeX pdf, convertir LaTeX a pdf
description: Para convertir TeX a PDF usando la solución API Aspose.TeX para Java, lea este artículo para ver cómo se hace esto y los ejemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}


## Cómo convertir LaTeX a PDF

Echemos un vistazo más de cerca al código Java que proporciona la forma más sencilla de convertir LaTeX a formato PDF.

Establezca `inputFile` en la ruta completa de su archivo LaTeX, como `hello-world.ltx`, y `outputDirectory` en una carpeta de salida existente. Importe las clases de `com.aspose.tex` y `com.aspose.tex.rendering` utilizadas en el fragmento. El método que realiza la llamada debe capturar o declarar las excepciones. Aplique una licencia como se describe en la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación. El ejemplo utiliza un procesamiento no interactivo y cierra sus recursos de salida.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToPDF-Simplest.java" >}}

Entonces, lo primero que debemos hacer (a veces no lo primero, como descubriremos más adelante) es crear una instancia de la clase [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). El único método estático que hace esto es [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#consoleAppOptions-com.aspose.tex.TeXConfig-), así que no nos molestemos con el significado de su nombre. El método toma una [instancia](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectLaTeX--) de la clase [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/), que es exactamente adecuada para convertir un [archivo LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuración indica al motor Object TeX que cargue el formato Object LaTeX y que esté listo para aceptar el archivo LaTeX. El formato de objeto LaTeX es solo el formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), excepto que utiliza primitivas específicas de [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar las métricas de la página.

La primera de las opciones requeridas es [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) que define el espacio o área donde se escribirá la salida TeX. [Aquí](/tex/{{lang.url-fragment}}java/aspose-tex-output/) están los detalles sobre el concepto de directorio de salida en **Aspose.TeX para Java**. En este ejemplo, utilizamos la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/), que nos permite escribir la salida en el directorio o carpeta especificado.

La segunda opción es una instancia de clase [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/saveoptions/) que controlará la transformación del [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato de destino. Dado que estamos convirtiendo LaTeX a PDF, es la instancia de clase [PdfSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions).

Luego necesitamos crear una instancia de la clase [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/). Al querer convertir un archivo LaTeX almacenado en el sistema de archivos, utilizamos [esta](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) versión del constructor. Deberíamos especificar la ruta completa al archivo. De lo contrario, el motor lo buscará en el directorio actual (que está definido [aquí](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) y lo más probable es que no lo encuentre. No obstante, podremos omitir la extensión si nuestro archivo tiene la *.tex*. El motor lo agregará automáticamente. El segundo argumento del constructor es una instancia de clase [Dispositivo](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/device/). Dado que estamos convirtiendo LaTeX a PDF, es una instancia de clase [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice). Como último argumento, pasamos las opciones de conversión preparadas recientemente.

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

Encontraremos otros productos de ejecución del motor en la carpeta que especificamos como directorio de salida. Esos serán el archivo de transcripción (.log) y, **¡Voilá!**, el archivo PDF de salida principal.

## Una forma alternativa de escribir el archivo PDF de salida principal

Hay otro constructor de la clase [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice#PdfDevice-java.io.OutputStream-), que nos permite obtener el archivo PDF resultante de una forma alternativa.

Utilice los mismos valores de `inputFile` y `outputDirectory` que arriba. Establezca `pdfFile` en un `java.nio.file.Path`, por ejemplo `Paths.get(outputDirectory, "any-name.pdf")`. Además de las clases de Aspose.TeX, importe `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path` y `java.nio.file.Paths`.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToPDF-Alternative.java" >}}

El archivo *any-name.pdf* en el directorio especificado será nuestro archivo PDF de salida principal. Al mismo tiempo, a diferencia de [salida de imagen](/tex/{{lang.url-fragment}}java/latex-to-image/), no encontraremos ningún archivo PDF en el directorio de salida definido por las opciones de conversión. Excepción: *cualquier nombre.pdf* está ubicado (por su ruta) en el mismo directorio del sistema de archivos asignado a la opción [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) usando [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

## Acerca de las opciones de entrada

En caso de que nuestro archivo de entrada principal requiera dependencias, por ejemplo, paquetes, que no están incluidos en el sistema LaTeX básico y los paquetes compatibles, DEBEMOS configurar la opción [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) de la misma manera que configuramos [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--). opción y coloque las dependencias en ese directorio. Las dependencias pueden organizarse arbitrariamente en subdirectorios. En caso de que tengamos nuestros propios archivos para incluir durante el proceso de composición tipográfica, digamos archivos de gráficos externos, DEBEMOS también configurar [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) usando la ruta a la ubicación donde se recopilan esos archivos. También podemos colocar el archivo de entrada principal en algún lugar dentro del directorio de entrada y pasar la ruta relativa al constructor de `TeXJob` (o no especificar ninguna ruta si el archivo de entrada principal está en la raíz). [Aquí](/tex/{{lang.url-fragment}}java/aspose-tex-input/) se encuentran los detalles sobre el concepto de directorio de entrada en **Aspose.TeX para Java** y las implementaciones proporcionadas.

Otras opciones de trabajo TeX se analizan [aquí](/tex/{{lang.url-fragment}}java/other-options/).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-pdf) gratuita de conversión de LaTeX a PDF creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) es la página de la versión de Java.**