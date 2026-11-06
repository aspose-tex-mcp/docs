---
translation: true
template: /templates/_template-python-net.md
title: Interfaz de salida de Aspose.TeX | Python 
linktitle: Interfaz de salida de Aspose.TeX
weight: 16
url: /python-net/aspose-tex-output/
description: Aquí hay una explicación de la funcionalidad de conversión de la solución Aspose.TeX para Python, con TeX como formato de salida, con ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}

> Para obtener definiciones formales de la implementación de E/S, consulte la [referencia de API](https://reference.aspose.com/tex/python-net/aspose.tex.io/) de **Aspose.TeX para Python**.

## La idea detrás del directorio de salida

Aspose.TeX define un directorio como un mapeo entre nombres y grandes cantidades de datos, donde las grandes cantidades de datos pueden ser archivos, secuencias, matrices u otros tipos de datos. La API permite la especificación de directorios de trabajo de entrada y salida separados. Para la salida, la API proporciona la interfaz general [IOutputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/), que el usuario puede implementar para sus necesidades específicas. Además, la API proporciona implementaciones listas para usar, que se analizarán a continuación. La interfaz *IOutputWorkingDirectory* extiende [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/), ya que el motor puede primero crear y escribir un archivo y luego volver a leerlo. La interfaz incluye el método [get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str), que devuelve la secuencia para escribir, en contraste con el método [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), que devuelve la secuencia para leer.

### Guardar la salida como un archivo en el sistema de archivos del disco

Como se mencionó [arriba](/tex/{{lang.url-fragment}}net/latex-to-image/), el [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/) comúnmente se configura como una instancia de la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/).

Así es como lo configuraríamos:

Establezca `ASPOSE_TEX_OUTPUT_DIR` en el directorio de salida (predeterminado: `output`). Aplique primero una licencia. [Licensing](/tex/es/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

El flujo TeX simple incluido genera `texput.xps` y `texput.log` en el directorio de salida.

### Guardar el resultado como un archivo ZIP.

Otra opción es crear un archivo o secuencia y usarlo como archivo ZIP para almacenar los archivos de salida. Aquí hay un ejemplo:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

`zip-xps-out.zip` se abre en modo binario `wb`. Llame a `finish()` en `OutputZipDirectory` antes de cerrar el flujo. El archivo contiene `texput.xps` y `texput.log`.

Para comenzar, creamos un flujo de salida para el archivo ZIP. Luego, después de crear las opciones de conversión, configuramos la opción *output_working_directory* para que sea una instancia de la clase [OutputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/).

## La idea detrás del terminal de salida.

La salida del terminal es otro aspecto importante de la salida. Para esto, **Aspose.TeX para Python** define la interfaz general [IOutputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/), que tiene una única propiedad que devuelve una instancia de la implementación [TerminalWriter](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/). Las implementaciones disponibles se analizarán a continuación.

### Escribir la salida del terminal en la consola

Para lograr esto, necesitamos configurar la opción [terminal_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/) como una instancia de la clase [OutputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

Una vez más, este es el valor predeterminado de la opción, por lo que no es necesario especificarlo. Por lo tanto, esta sección se proporciona únicamente con fines de demostración.

### Escribir la salida del terminal en un archivo

A diferencia del terminal de entrada, **Aspose.TeX para Python** incluye una implementación de la interfaz *IOutputTerminal* que nos permite escribir la salida del terminal en un archivo dentro de un directorio de salida específico.

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}}

El constructor de `OutputFileTerminal` recibe el directorio de trabajo de salida y escribe allí `texput.trm`, junto a `texput.xps` y `texput.log`.
