---
translation: true
template: /templates/_template-net.md
title: Interfaz de entrada de Aspose.TeX | .NET
linktitle: Interfaz de entrada de Aspose.TeX
weight: 15
url: /net/aspose-tex-input/
description: La funcionalidad de conversión de la solución API Aspose.TeX para .NET con TeX, como formato de entrada, se explica aquí con los ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}

Consulte **Aspose.TeX para .NET** [referencia de API](https://reference.aspose.com/tex/net/aspose.tex.io/) para obtener definiciones formales de implementación de E/S.

## El concepto del directorio de entrada.

Dado que las primitivas de E/S del lenguaje TeX solo pueden tratar con nombres de archivos, **Aspose.TeX para .NET** define un directorio como una asignación entre nombres y grandes cantidades de datos. Se supone que la gran cantidad de datos son archivos, secuencias, matrices o cualquier otra cosa. La API nos permite especificar los directorios de trabajo de entrada y salida por separado. Proporciona la interfaz general [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), que el usuario puede implementar para sus propios fines. También proporciona sus propias implementaciones, que se analizarán a continuación. La interfaz define el método [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/), que devuelve el flujo de datos y determina el nombre completo del archivo, mientras toma algún nombre, hipotéticamente diferente, como primer argumento, que, de hecho, es la clave de mapeo. .

### Obtener entrada de archivos del sistema de archivos del disco

Así es como lo haríamos:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.cs" >}}

Este caso de uso es bastante simple, por lo que ya no es necesario centrarse en él.

### Obtener entrada de archivo desde un archivo ZIP

También podemos poner los archivos de entrada en un archivo ZIP y considerarlo un directorio de entrada. En este caso debemos proceder de la siguiente manera:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputZipDirectory.cs" >}}

Primero, creamos la secuencia que contiene el archivo ZIP. Luego, después de crear las opciones de conversión, configuramos la opción [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) para que sea una instancia de la clase [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/). El segundo argumento del constructor es la ruta base dentro del archivo. Si queremos que todo el archivo sea un directorio de entrada, debemos pasar la cadena vacía. 

## El concepto de terminal de entrada.

Ahora toca recordar que también está la entrada del terminal. En cuanto a este, **Aspose.TeX para .NET** define la interfaz general [IInputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/) que tiene solo una propiedad que devuelve una instancia de implementación [TextReader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader). Las implementaciones proporcionadas se analizan a continuación.

### Obtener entrada de terminal desde la consola

Para hacer esto, necesitamos configurar la opción [TerminalIn](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) para que sea una instancia de la clase [InputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/).

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputConsoleTerminal.cs" >}}

Pero, a decir verdad, este es el valor predeterminado de la opción, por lo que no es necesario especificarlo. Por lo tanto, y mientras no existan otras implementaciones, esta sección tiene únicamente fines demostrativos.

En teoría, si tenemos un archivo (o secuencia de comandos) TeX interactivo con un comportamiento predecible, es posible que deseemos implementar una versión del terminal de entrada que contenga una secuencia de comandos complementaria para responder a las solicitudes del motor TeX. ¡Prueba suerte cuando tengas tiempo!