---
translation: true
template: /templates/_template-python-net.md
title: Látex a PDF | Aspose.TeX para Python
linktitle: Látex a PDF
weight: 11
url: /python-net/latex-to-pdf/
keywords: LaTeX a pdf, LaTeX pdf, convertir LaTeX a pdf
description: Aprenda cómo convertir TeX a PDF usando Aspose.TeX para Python con este artículo, que proporciona una explicación detallada y ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Convertir LaTeX a PDF

Ahora, examinemos en profundidad el código Python que ofrece el enfoque más sencillo para convertir LaTeX a formato PDF.

Establezca `ASPOSE_TEX_INPUT_FILE` en su archivo LaTeX y `ASPOSE_TEX_OUTPUT_DIR` en el directorio de salida, o edite las rutas del ejemplo. Los valores predeterminados son `hello-world.ltx` y `output`. Aplique primero una licencia. Los archivos de entrada adicionales se buscan junto al documento principal y el procesamiento no es interactivo. [Licencias](/tex/es/python-net/licensing/)

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

Para comenzar, necesitamos crear una instancia de la clase [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). El método [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)   es el único método estático que logra esto, así que no te preocupes por su nombre. Este método toma una instancia [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) de la clase [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), que es perfecta para convertir un [archivo LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuración indica al motor Object TeX que cargue el formato Object LaTeX y esté preparado para procesar el archivo LaTeX. El formato Object LaTeX es esencialmente el mismo que el formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), pero utiliza primitivas específicas de [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para definir las métricas de la página.

La primera opción que debe especificarse es [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), que determina la ubicación donde se guardará la salida TeX. Si es necesario, puede encontrar más información sobre el [concepto de directorio de salida en **Aspose.TeX**](/tex/{{lang.url-fragment}}net/aspose-tex-output/). En este caso particular, utilizamos la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/), que nos permite escribir la salida en un directorio o carpeta designado.

La segunda opción requiere una instancia de la clase [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), que determina cómo el [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) se transforma al formato deseado. En nuestro caso, mientras convertimos LaTeX a PDF, se refiere a una instancia de la clase [PdfSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Para convertir un archivo LaTeX almacenado en el sistema de archivos, necesitamos crear una instancia de la clase [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) usando el [constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)   que toma la ruta completa del archivo como parámetro. Si no especificamos la ruta completa, el motor buscará el archivo en el directorio actual (que es el directorio de trabajo del script) y es posible que no lo encuentre. Sin embargo, podemos omitir la extensión si nuestro archivo tiene la extensión `.tex`, ya que el motor la agregará automáticamente. El segundo argumento del constructor es una instancia de la clase [Dispositivo](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). En nuestro caso, dado que estamos convirtiendo LaTeX a PDF, es una instancia de la clase [PdfDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/). Finalmente, pasamos las opciones de conversión preparadas recientemente como último argumento.

Ahora, todo lo que queda es [ejecutar](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) el trabajo.

El ejemplo captura la salida del terminal en `OutputMemoryTerminal`. El directorio de salida también contiene un registro `.log`. Una conversión correcta genera un registro similar al siguiente; los datos de versión pueden variar:

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

En la carpeta que especificamos como directorio de salida, encontraremos el archivo de transcripción y, **¡aquí está!**, el archivo PDF de salida principal, entre otros resultados del trabajo del motor.

## Una forma alternativa de escribir el archivo PDF de salida principal

La clase *PdfDevice* tiene otro [constructor](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase) que nos permite obtener el archivo PDF resultante de otra manera.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

El flujo binario escribe `any-name.pdf` en el directorio de salida configurado. No se crea otro archivo PDF con el nombre predeterminado; los archivos auxiliares y el registro siguen guardándose en `output_working_directory`.

## Acerca de las opciones de entrada

Si nuestro archivo de entrada principal requiere dependencias, como paquetes que no están incluidos en el sistema LaTeX básico y paquetes compatibles, es necesario configurar la opción [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) de manera similar a como configuramos la opción *output_working_directory* y coloque las dependencias en ese directorio. Las dependencias se pueden organizar en subdirectorios según se desee. Además, si tenemos nuestros propios archivos para incluir en el proceso de composición tipográfica, como archivos de gráficos externos, también debemos configurar el [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) usando la ruta a la ubicación donde se almacenan esos archivos. También podemos colocar el archivo de entrada principal dentro del directorio de entrada y especificar la ruta relativa al constructor `TeXJob`, o no especificar ninguna ruta si el archivo de entrada principal está en la raíz. Para obtener más detalles sobre el concepto de directorio de entrada en **Aspose.TeX para Python** y las implementaciones proporcionadas, consulte [aquí](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/).

También se analizan [otras opciones de trabajo TeX](/tex/{{lang.url-fragment}}python-net/other-options/).

**También puede explorar la [aplicación web gratuita para la conversión de LaTeX a PDF](https://products.aspose.app/tex/conversion/latex-to-pdf), que se desarrolla utilizando [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**