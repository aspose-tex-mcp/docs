---
translation: true
template: /templates/_template-python-net.md
title: Interfaz de entrada de Aspose.TeX | Pitón
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

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Este caso de uso particular es bastante sencillo, por lo que podemos continuar con él ahora.

### Recuperar la entrada de un archivo desde un archivo ZIP

Otra opción es almacenar los archivos de entrada en un archivo ZIP y tratarlo como un directorio de entrada. En tal escenario, se deben seguir los siguientes pasos:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

Para empezar, creamos la secuencia que contiene el archivo ZIP. Posteriormente, después de crear las opciones de conversión, asignamos una instancia de la clase [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) a la propiedad [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/). El segundo parámetro del constructor representa la ruta base dentro del archivo. Si deseamos que todo el archivo funcione como directorio de entrada, debemos proporcionar una cadena vacía como argumento.

## La idea detrás del terminal de entrada

Ahora consideremos el concepto de entrada terminal. **Aspose.TeX para Python** define la interfaz general [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) específicamente para este propósito, que incluye una propiedad única que devuelve una instancia de la implementación [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/). Las implementaciones disponibles se discutirán más adelante.

### Obtener entrada de terminal desde la consola

Para lograr esto, necesitamos asignar una instancia de la clase [InputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) a la opción [terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

Sin embargo, para ser honesto, este es el valor predeterminado para la opción, por lo que no hay necesidad real de especificarlo explícitamente. Dada la ausencia de otras implementaciones, esta sección tiene fines puramente demostrativos.

En teoría, si tenemos un archivo (o script) TeX interactivo con un comportamiento predecible, podría ser deseable implementar una versión del terminal de entrada que incluya un script correspondiente para responder a las solicitudes del motor TeX. ¡No dudes en probarlo cuando tengas la oportunidad!