---
translation: true
template: /templates/_template-python-net.md
title: LaTeX a la imagen | Aspose.TeX para Python
linktitle: LaTeX a imagen
weight: 10
url: /python-net/latex-to-image/
keywords: LaTeX a png, LaTeX png, LaTeX a imagen, imagen de LaTeX, LaTeX a jpg, LaTeX jpg, LaTeX a jpeg, LaTeX jpeg, LaTeX a tiff, LaTeX tiff, LaTeX a bmp, LaTeX bmp
description: Para convertir TeX a formatos de imagen usando la solución Aspose.TeX para Python, lea este artículo para ver cómo se hace esto y los ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}

**Aspose.TeX para Python** nos proporciona la capacidad de convertir archivos LaTeX en varios formatos de imágenes rasterizadas.

## Conversión de LaTeX a PNG

Ahora, examinemos en profundidad el código Python que ofrece el enfoque más sencillo para convertir LaTeX a formato PNG.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

Para empezar, necesitamos crear una instancia de la clase [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) usando el método [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig). No te preocupes por el nombre, es sólo el método estático que crea la instancia. Este método toma la instancia [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) de la clase [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), que es perfecta para convertir un [archivo LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuración configura el motor Object TeX para cargar el formato Object LaTeX y estar listo para procesar el archivo LaTeX. El formato Object LaTeX es esencialmente el mismo que el [formato LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), pero utiliza primitivas específicas de [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para definir las métricas de la página.

La primera de las opciones necesarias es [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), que especifica la ubicación donde se guardará la salida TeX. Si está interesado, puede obtener más información sobre el concepto de [directorio de salida en **Aspose.TeX para Python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/). En este ejemplo particular, utilizamos la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) para escribir la salida en un directorio o carpeta específica.

La segunda opción es una instancia de la clase [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), que se encarga de gestionar la conversión del [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato deseado. En este caso, dado que estamos convirtiendo LaTeX a PNG, usamos la instancia de clase [PngSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/), que nos permite especificar la resolución de las imágenes de salida.

A continuación, creamos una instancia de la clase [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/). En este caso, como queremos convertir un archivo LaTeX almacenado en el sistema de archivos, usamos [esta versión del constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions). Necesitamos proporcionar la ruta completa al archivo; de lo contrario, el motor lo buscará en el directorio actual (que es el directorio de trabajo del script) y es posible que no lo encuentre. Sin embargo, la extensión `.tex` se puede omitir ya que el motor la agregará automáticamente. El segundo argumento del constructor es una instancia de la clase [Dispositivo](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Dado que estamos convirtiendo LaTeX a PNG, es una instancia de clase [ImageDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/), que es común a todos los formatos de imagen admitidos. Finalmente, pasamos las opciones de conversión preparadas como último argumento.

Ahora, todo lo que queda es [ejecutar](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) el trabajo.

Una vez ejecutado el trabajo, independientemente de su éxito o fracaso, la primera salida que encontraremos es la salida del terminal. En el caso de una ejecución exitosa, el resultado será similar al siguiente:

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

Los resultados del trabajo del motor se pueden encontrar en el directorio de salida que especificamos. Esto incluirá el archivo de transcripción y, lo más importante, los archivos de imagen PNG de salida principales.

## Una forma alternativa de escribir los archivos PNG de salida principales

Existe un método alternativo para obtener datos de imagen como una matriz de matrices de bytes, donde cada matriz en la segunda dimensión representa los datos de imagen para una página separada.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

Los archivos "page-n.png" se pueden escribir en cualquier ruta especificada. A diferencia de [salida PDF](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file), estos archivos PNG duplicarán los archivos PNG de salida que se escriben en el directorio de salida.

## En cuanto a las opciones de entrada

Si nuestro archivo de entrada principal requiere dependencias, como paquetes que no están incluidos en el sistema LaTeX básico o paquetes compatibles, debemos configurar la opción [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) de manera similar a como configuramos la opción *output_working_directory* y coloque las dependencias en ese directorio. Las dependencias se pueden organizar en subdirectorios según sea necesario. Si tenemos nuestros archivos para incluir en el proceso de composición tipográfica, como archivos de gráficos externos, también debemos configurar el [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) en la ubicación donde se almacenan esos archivos. También podemos colocar el archivo de entrada principal dentro del directorio de entrada y especificar la ruta relativa en el método `run()`, o no especificar ninguna ruta si el archivo de entrada principal está en el directorio raíz. También hay más detalles sobre el [concepto de directorio de entrada](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) en **Aspose.TeX** y las implementaciones proporcionadas descritas.

Conozca también [otras opciones de trabajo TeX aquí](/tex/{{lang.url-fragment}}python-net/other-options/).

**También puede explorar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-png) gratuita para la conversión de LaTeX a PNG, que se desarrolla utilizando [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

A continuación, explicaremos brevemente la conversión de LaTeX a otros formatos de imágenes rasterizadas compatibles, sin entrar en demasiados detalles ya que no existen diferencias significativas. La única variación radica en el tipo de propiedad [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) en las opciones de conversión.

## Conversión de LaTeX a JPG

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

**También puede explorar la [aplicación web gratuita para la conversión de LaTeX a JPG](https://products.aspose.app/tex/conversion/latex-to-jpg), que se desarrolla utilizando [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Conversión de LaTeX a TIFF

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**También puede explorar la [aplicación web gratuita para la conversión de LaTeX a TIFF](https://products.aspose.app/tex/conversion/latex-to-tiff), que se desarrolla utilizando [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Conversión de LaTeX a BMP

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**También puede explorar la [aplicación web gratuita para la conversión de LaTeX a BMP](https://products.aspose.app/tex/conversion/latex-to-bmp), que se desarrolla utilizando [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**


## Conversión de LaTeX a SVG

Otro formato de destino admitido es [**SVG**](https://en.wikipedia.org/wiki/SVG). **Gráficos vectoriales escalables (SVG)** es un formato de imagen vectorial basado en XML que se utiliza para definir gráficos bidimensionales. Soporta interactividad y animación.

Las imágenes **SVG** se almacenan en archivos de texto XML y se definen en un formato de gráficos vectoriales. Esto significa que las imágenes **SVG** se pueden escalar en tamaño sin perder calidad, y los propios archivos **SVG** se pueden buscar, indexar, codificar y comprimir. Los archivos de texto XML se pueden crear y editar utilizando editores de texto o editores de gráficos vectoriales, y se pueden representar mediante los navegadores web más utilizados.

La API [**Aspose.SVG**](https://products.aspose.com/svg/) ofrece una variedad de funciones para trabajar con **SVG**, como crear, cargar, editar y convertir documentos **SVG**.

Convertir LaTeX a SVG es tan sencillo como [convertir a formatos de imagen rasterizada](/tex/{{lang.url-fragment}}python-net/latex-to-image/), con la única diferencia de que [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) debe configurarse en una instancia de la clase [SvgSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/) y el El dispositivo debe cambiarse a una instancia de la clase [SvgDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**También puede explorar la [aplicación web gratuita para la conversión de LaTeX a SVG](https://products.aspose.app/tex/conversion/latex-to-svg), que se desarrolla utilizando [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**