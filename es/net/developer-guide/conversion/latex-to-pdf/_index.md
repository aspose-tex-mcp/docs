---
translation: true
template: /templates/_template-net.md
title: Látex a PDF | .NET
linktitle: Látex a PDF
weight: 11
url: /net/latex-to-pdf/
keywords: LaTeX a pdf, LaTeX pdf, convertir LaTeX a pdf
description: Para convertir TeX a PDF usando la solución API Aspose.TeX para .NET, lea este artículo para ver cómo se hace esto y los ejemplos de código.
lastmod: "2026-04-22"
---

{{<section overview>}}


## Cómo convertir LaTeX a PDF

Echemos un vistazo detallado al código en C# que proporciona la forma más sencilla de convertir LaTeX a formato PDF.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

Entonces, lo primero que debemos hacer (bueno, a veces no lo primero) es crear una instancia de la clase [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). El único método estático que hace esto es [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), así que no nos dejemos desconcertar por el significado de su nombre. El método toma una [instancia](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) de la clase [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), que es exactamente adecuada para convertir un [archivo LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuración le dice al motor Object TeX que cargue el formato Object LaTeX y que esté listo para aceptar el archivo LaTeX. El formato Object LaTeX es en realidad solo el formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), excepto que utiliza primitivas específicas de [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar las métricas de la página.

La primera de las opciones requeridas es [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) que define el espacio o área donde se escribirá la salida TeX. [Aquí](/tex/{{lang.url-fragment}}net/aspose-tex-output/) se encuentran los detalles sobre el concepto de directorio de salida en **Aspose.TeX para .NET**. En este ejemplo, usamos la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), que nos permite escribir la salida en el directorio o carpeta especificado.

La segunda opción es una instancia de clase [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) que controlará la transformación del [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato de destino. Dado que estamos convirtiendo LaTeX a PDF, es la instancia de clase [PdfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Luego necesitamos crear una instancia de la clase [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Al querer convertir un archivo LaTeX almacenado en el sistema de archivos, utilizamos [esta](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) versión del constructor. Debemos especificar la ruta completa al archivo. De lo contrario, el motor lo buscará en el directorio actual (que es [CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)) y lo más probable es que no lo encuentre. No obstante, podremos omitir la extensión si nuestro archivo tiene la *.tex*. El motor lo agregará automáticamente. El segundo argumento del constructor es una instancia de clase [Dispositivo](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Dado que estamos convirtiendo LaTeX a PDF, es una instancia de clase [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/). Como último argumento, pasamos las opciones de conversión preparadas recientemente.

Todo lo que queda por hacer ahora es [ejecutar](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) el trabajo.

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

Encontraremos otros "frutos" del trabajo del motor en la carpeta que especificamos como directorio de salida. Ese será el archivo de transcripción y, **¡aquí está!**, el archivo PDF de salida principal.

## Una forma alternativa de escribir el archivo PDF de salida principal {#an-alternative-way-to-write-the-main-output-pdf-file}

Hay otro constructor de la clase [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/), que nos permite obtener el archivo PDF resultante de una forma alternativa.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Alternative.cs" >}}

El archivo *any-name.pdf* en el directorio especificado será nuestro archivo PDF de salida principal. Al mismo tiempo, a diferencia de [salida de imagen](/tex/{{lang.url-fragment}}net/latex-to-image/), no encontraremos ningún archivo PDF en el directorio de salida definido por las opciones de conversión. Excepción: *cualquier nombre.pdf* está ubicado (por su ruta) en el mismo directorio del sistema de archivos asignado a la opción [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) usando [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

## Acerca de las opciones de entrada

En caso de que nuestro archivo de entrada principal requiera dependencias, por ejemplo, paquetes, que no están incluidos en el sistema LaTeX básico y los paquetes compatibles, DEBEMOS configurar la opción [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) de la misma manera que configuramos [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/). opción y coloque las dependencias en ese directorio. Las dependencias pueden organizarse arbitrariamente en subdirectorios. En caso de que tengamos nuestros propios archivos para incluir durante el proceso de composición tipográfica, digamos archivos de gráficos externos, DEBEMOS también configurar [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) usando la ruta a la ubicación donde se recopilan esos archivos. También podemos colocar el archivo de entrada principal en algún lugar dentro del directorio de entrada y especificar la ruta relativa en el método `run()` (o no especificar ninguna ruta si el archivo de entrada principal está en la raíz). [Aquí](/tex/{{lang.url-fragment}}net/aspose-tex-input/) se encuentran los detalles sobre el concepto de directorio de entrada en **Aspose.TeX para .NET** y las implementaciones proporcionadas.

Otras opciones de trabajo TeX se analizan [aquí](/tex/{{lang.url-fragment}}net/other-options/).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-pdf) gratuita de conversión de LaTeX a PDF creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**
