---
translation: true
template: /templates/_template-python-net.md
title: Interfaz de entrada de Aspose.TeX | Python 
linktitle: Interfaz de entrada de Aspose.TeX
weight: 15
url: /python-net/aspose-tex-input/
description: La funcionalidad de conversión de la solución API Aspose.TeX para Python con TeX, como formato de entrada, se explica aquí con los ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}

> Para obtener definiciones formales de la implementación de E/S en **Aspose.TeX para Python**, consulte la [referencia de API](https://reference.aspose.com/tex/python-net/aspose.tex.io/).

## La idea detrás del directorio de entrada

Dado que las primitivas de E/S del lenguaje TeX solo pueden manejar nombres de archivos, **Aspose.TeX para Python** define un directorio como un mapeo entre nombres y colecciones de datos. Estas colecciones de datos pueden ser archivos, secuencias, matrices o cualquier otro tipo. La API permite la especificación separada de directorios de trabajo de entrada y salida. Proporciona la clase general [InputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/), que los usuarios pueden implementar para sus necesidades específicas. Además, la API proporciona implementaciones integradas, que se analizarán más adelante. La interfaz incluye el método [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), que recupera el flujo de datos y determina el nombre completo del archivo en función de un nombre determinado, que sirve como clave de mapeo.

### Recuperar la entrada de archivos del sistema de archivos del disco

Este es el enfoque que adoptaríamos:

Establezca `ASPOSE_TEX_OUTPUT_DIR` en el directorio de salida (predeterminado: `output`). Aplique primero una licencia. [Licensing](/tex/es/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Establezca `ASPOSE_TEX_INPUT_DIR` en la carpeta con `hello-world.tex` (predeterminada: `input`). El ejemplo usa TeX simple con `TeXConfig.object_tex()` y genera `hello-world.xps` y `hello-world.log`. Entrada:

```tex
Hello, World!
\end
```

### Recuperar la entrada de un archivo desde un archivo ZIP

Otra opción es almacenar los archivos de entrada en un archivo ZIP y tratarlo como un directorio de entrada. En tal escenario, se deben seguir los siguientes pasos:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

`ASPOSE_TEX_INPUT_ZIP` indica un archivo con `in/hello-world.tex` (predeterminado: `zip-in.zip`). Ábralo en modo binario `rb` y mantenga el flujo abierto hasta que termine el trabajo.

Para empezar, creamos la secuencia que contiene el archivo ZIP. Posteriormente, después de crear las opciones de conversión, asignamos una instancia de la clase [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) a la propiedad [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/). El segundo parámetro del constructor representa la ruta base dentro del archivo. Si deseamos que todo el archivo funcione como directorio de entrada, debemos proporcionar una cadena vacía como argumento.

## La idea detrás del terminal de entrada

Ahora consideremos el concepto de entrada terminal. **Aspose.TeX para Python** define la interfaz general [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) específicamente para este propósito, que incluye una propiedad única que devuelve una instancia de la implementación [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/). Las implementaciones disponibles se discutirán más adelante.

### Obtener entrada de terminal desde la consola

Para lograr esto, necesitamos asignar una instancia de la clase [InputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) a la opción [terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

El ejemplo lee una línea mediante `\read` y la escribe en `texput.xps`. Introduzca, por ejemplo, `Terminal input works!` en el terminal o suministre la línea por la entrada estándar. `SCROLL_MODE` permite esta solicitud de entrada.
