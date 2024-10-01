---
translation: true
template: /templates/_template-net.md
title: Interfaz de salida de Aspose.TeX | .NETO
linktitle: Interfaz de salida de Aspose.TeX
weight: 16
url: /net/aspose-tex-output/
description: La funcionalidad de conversión de la solución API Aspose.TeX para .NET con TeX, como formato de salida, se explica aquí con los ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}

Consulte **Aspose.TeX para .NET** [referencia de API](https://reference.aspose.com/tex/net/aspose.tex.io/) para obtener definiciones formales de implementación de E/S.

## El concepto del directorio de salida.

Dado que las primitivas de E/S del lenguaje TeX sólo pueden tratar con nombres de archivos, Aspose.TeX define un directorio como un mapeo entre nombres y grandes cantidades de datos. Se supone que la gran cantidad de datos son archivos, secuencias, matrices o cualquier otra cosa. La API nos permite especificar los directorios de trabajo de entrada y salida por separado. Proporciona la interfaz general [IOutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) para la salida, que el usuario puede implementar para sus propios fines. También proporciona sus propias implementaciones, que se analizarán a continuación. La interfaz extiende [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), ya que el motor puede primero crear y escribir un archivo y luego volver a leerlo. El método propio de la interfaz [GetOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) devuelve la secuencia para escribir, a diferencia de la secuencia para leer devuelta por [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/).

### Escribir la salida del archivo en el sistema de archivos del disco

Como mencionamos [arriba](/tex/{{lang.url-fragment}}net/latex-to-png/), el valor más común para [OutputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) probablemente sería una instancia de la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

Así es como lo configuraríamos:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.cs" >}}

Este caso de uso es bastante simple, por lo que ya no es necesario centrarse en él.

### Escribir la salida del archivo en un archivo ZIP

También podemos crear un archivo (o secuencia) y dejar que el motor TeX lo use como un archivo ZIP para almacenar los archivos de salida. Aquí lo tienes:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputZipDirectory.cs" >}}

Primero, creamos un flujo de salida para el archivo ZIP. Luego, después de crear las opciones de conversión, configuramos la opción [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) para que sea una instancia de la clase [OutputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/).

## El concepto de terminal de salida.

Hay otra parte importante de la salida: la salida del terminal. En cuanto a este, **Aspose.TeX para .NET** define la interfaz general [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) que tiene solo una propiedad que devuelve una instancia de implementación [TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter). Las implementaciones proporcionadas se analizan a continuación.

### Escribir la salida del terminal en la consola

Para hacer esto, necesitamos configurar la opción [TerminalOut](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) para que sea una instancia de la clase [OutputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.cs" >}}

Nuevamente, este es el valor predeterminado de la opción, por lo que no es necesario especificarlo. Debido a esto, esta sección tiene únicamente fines de demostración.

### Escribir la salida del terminal en un archivo

A diferencia del terminal de entrada, **Aspose.TeX para .NET** proporciona una implementación de [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), que nos permite escribir la salida del terminal en un archivo en algún directorio de salida.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputFileTerminal.cs" >}} 

Aquí le pedimos al motor TeX que escriba la salida del terminal en el archivo con el nombre [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, que se almacenará en el mismo directorio de salida que especificamos para el resto de la salida. Pero esto no es necesario. También podríamos pasar cualquier otra instancia de cualquier implementación de [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) al constructor.