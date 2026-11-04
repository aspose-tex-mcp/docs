---
translation: true
template: /templates/_template-net.md
title: LaTeX a la imagen | .NET
linktitle: LaTeX a imagen
weight: 10
url: /net/latex-to-image/
keywords: LaTeX a png, LaTeX png, LaTeX a imagen, imagen de LaTeX, LaTeX a jpg, LaTeX jpg, LaTeX a jpeg, LaTeX jpeg, LaTeX a tiff, LaTeX tiff, LaTeX a bmp, LaTeX bmp
description: Para convertir TeX a formatos de imagen usando la Aspose.TeX para .NET, lea este artículo para ver que describe cómo hacer esto y los ejemplos de código.
lastmod: "2026-11-04"
---

{{<section overview>}}

**Aspose.TeX para .NET** nos permite convertir archivos LaTeX a varios formatos de imágenes rasterizadas.

## Cómo convertir LaTeX a PNG

Echemos un vistazo detallado al código en C# que proporciona la forma más sencilla de convertir LaTeX a formato PNG.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Simplest.cs" >}}

Entonces, lo primero que debemos hacer (bueno, a veces no lo primero) es crear una instancia de la clase [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). El único método estático que hace esto es [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), así que no nos dejemos desconcertar por el significado de su nombre. El método toma la [instancia de ObjectLaTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) de la clase [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), que es exactamente adecuada para convertir un [archivo LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuración le dice al motor Object TeX que cargue el formato Object LaTeX y que esté listo para aceptar el archivo LaTeX. El formato Object LaTeX es en realidad solo el formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), excepto que utiliza primitivas específicas de [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar las métricas de la página.

La primera de las opciones requeridas es [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) que define el espacio o área donde se escribirá la salida TeX. [Aquí](/tex/{{lang.url-fragment}}net/aspose-tex-output/) se encuentran los detalles sobre el concepto de directorio de salida en **Aspose.TeX para .NET**. En este ejemplo, usamos la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), que nos permite escribir la salida en el directorio o carpeta especificado.

La segunda opción es una instancia de clase [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) que controlará la transformación del [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato de destino. Dado que estamos convirtiendo LaTeX a PNG, es la instancia de clase [PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/), que nos permite especificar la resolución de las imágenes de salida.

Luego necesitamos crear una instancia de la clase [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Al querer convertir un archivo LaTeX almacenado en el sistema de archivos, utilizamos [esta](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) versión del constructor. Necesitamos especificar la ruta completa al archivo. De lo contrario, el motor lo buscará en el directorio actual (que es [CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)) y lo más probable es que no lo encuentre. Sin embargo, se puede omitir la extensión *.tex*. El motor lo agregará automáticamente. El segundo argumento del constructor es una instancia de clase [Dispositivo](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Dado que estamos convirtiendo LaTeX a PNG, es una instancia de clase [ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/) y esto es común a todos los formatos de imagen admitidos. Como último argumento, pasamos las opciones de conversión preparadas recientemente.

Todo lo que queda por hacer ahora es [ejecutar](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) el trabajo.

Independientemente de si la ejecución fue exitosa o no, el primer resultado que veremos será la salida del terminal. Si la ejecución fue exitosa, se verá así:

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

Encontraremos otros "frutos" del trabajo del motor en la carpeta que especificamos como directorio de salida. Esos serán el archivo de transcripción y, **¡aquí está!**, los archivos de imagen PNG de salida principal.

## Una forma alternativa de escribir los archivos PNG de salida principales

Hay otra forma de obtener datos de imagen como una matriz de matrices de bytes; cada matriz en la segunda dimensión representa datos de imagen para una página separada.

**Ejemplo de conversión alternativo**

El siguiente fragmento de C# muestra otra forma de obtener la salida PNG: el dispositivo conserva los datos de imagen en memoria como matrices de bytes en lugar de escribirlos en el sistema de archivos. Este enfoque es útil cuando necesita los bytes PNG generados para procesarlos posteriormente, por ejemplo, para enviarlos por una red, almacenarlos en una base de datos o realizar transformaciones adicionales antes de guardarlos.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Alternative.cs" >}}

Los archivos *"page-n.png"* se escribirán en cualquier ruta que especifiquemos. Como la opción `DeviceWritesImages` está establecida en `false`, el propio dispositivo no escribe archivos PNG en el directorio de salida.

## Acerca de las opciones de entrada

En caso de que nuestro archivo de entrada principal requiera dependencias, por ejemplo, paquetes, que no están incluidos en el sistema LaTeX básico y los paquetes compatibles, DEBEMOS configurar la opción [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) de la misma manera que configuramos [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/). opción y coloque las dependencias en ese directorio. Las dependencias pueden organizarse arbitrariamente en subdirectorios. En caso de que tengamos nuestros propios archivos para incluir durante el proceso de composición tipográfica, digamos archivos de gráficos externos, DEBEMOS también configurar [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) usando la ruta a la ubicación donde se recopilan esos archivos. También podemos colocar el archivo de entrada principal en algún lugar dentro del directorio de entrada y especificar la ruta relativa en el método `run()` (o no especificar ninguna ruta si el archivo de entrada principal está en la raíz). [Aquí](/tex/{{lang.url-fragment}}net/aspose-tex-input/) se encuentran los detalles sobre el concepto de directorio de entrada en **Aspose.TeX para .NET** y las implementaciones proporcionadas.

Otras opciones de trabajo en TeX se analizan [aquí](/tex/{{lang.url-fragment}}net/other-options/).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-png) gratuita de conversión de LaTeX a PNG creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

A continuación, analizamos la conversión de LaTeX a otros formatos de imágenes rasterizadas compatibles sin profundizar en los detalles, ya que en realidad no hay detalles. La única diferencia está en el tipo de propiedad [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) en las opciones de conversión.

## Cómo convertir LaTeX a JPG

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToJPEG.cs" >}}

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-jpg) gratuita de conversión de LaTeX a JPG creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Cómo convertir LaTeX a TIFF

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToTIFF.cs" >}}

{{% alert color="primary" %}}
El paquete `Aspose.TeX.Drawing` todavía no puede guardar archivos TIFF de varias páginas: con `TiffSaveOptions.Multipage` establecido en `true`, el archivo TIFF contiene solo la primera página. Establezca `Multipage` en `false` para obtener una imagen TIFF independiente por página. Consulte [Linux, macOS y Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/#known-limitations).
{{% /alert %}}

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-tiff) gratuita de conversión de LaTeX a TIFF creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Cómo convertir LaTeX a BMP

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToBMP.cs" >}}

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-bmp) gratuita de conversión de LaTeX a BMP creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Cómo convertir LaTeX a SVG

Y otro formato de destino admitido es [**SVG**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** es un formato de imagen vectorial basado en XML para definir gráficos bidimensionales, con soporte para interactividad y animación.

Las imágenes **SVG** se definen en un formato de gráficos vectoriales y se almacenan en archivos de texto XML. De este modo, las imágenes **SVG** se pueden escalar en tamaño sin pérdida de calidad, y los archivos **SVG** se pueden buscar, indexar, codificar y comprimir. Los archivos de texto XML se pueden crear y editar con editores de texto o editores de gráficos vectoriales y se procesan mediante los navegadores web más utilizados.

Existe la biblioteca [**Aspose.SVG**](https://products.aspose.com/svg/) que proporciona varias funciones relacionadas con **SVG**. Estos incluyen crear, cargar, editar y convertir documentos **SVG**.

La conversión de LaTeX a SVG también es tan simple como la [conversión a formatos de imagen rasterizada](/tex/{{lang.url-fragment}}net/latex-to-image/), excepto que [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) DEBE establecerse en una instancia de clase [SvgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/), y el dispositivo DEBE ser cambiado a una instancia de la clase [SvgDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToSVG-Simplest.cs" >}}

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-svg) gratuita de conversión de LaTeX a SVG creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**
