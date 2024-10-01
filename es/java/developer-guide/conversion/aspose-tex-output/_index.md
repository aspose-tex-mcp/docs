---
translation: true
template: /templates/_template-java.md
title: Interfaz de salida de Aspose.TeX | Java
linktitle: Interfaz de salida de Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: La funcionalidad de conversión de la solución API Aspose.TeX para Java con TeX, como formato de salida, se explica aquí con los ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}

Consulte **Aspose.TeX para Java** [referencia de API](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame) para obtener definiciones formales de implementación de E/S.

## El concepto del directorio de salida.

Dado que las primitivas de E/S del lenguaje TeX sólo pueden tratar con nombres de archivos, Aspose.TeX define un directorio como un mapeo entre nombres y grandes cantidades de datos. Se supone que la gran cantidad de datos son archivos, secuencias, matrices o cualquier otra cosa. La API nos permite especificar los directorios de trabajo de entrada y salida por separado. Proporciona la interfaz general [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory) para la salida, que el usuario puede implementar para sus propios fines. También proporciona sus propias implementaciones, que se analizarán a continuación. La interfaz extiende [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory), ya que el motor puede primero crear y escribir un archivo y luego volver a leerlo. El método propio de la interfaz [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory#getOutputFile-java.lang.String-java.lang.String:A-) devuelve la secuencia para escribir, a diferencia de la secuencia para leer devuelta por [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Escribir la salida del archivo en el sistema de archivos del disco

Como mencionamos [arriba](/tex/{{lang.url-fragment}}java/latex-to-png/), el valor más común para [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) probablemente sería una instancia de la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

Así es como lo configuraríamos:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

Este caso de uso es bastante simple, por lo que no nos detendremos en él por mucho tiempo.

### Escribir la salida del archivo en un archivo ZIP

También podemos crear un archivo (o secuencia) y dejar que el motor TeX lo use como un archivo ZIP para almacenar los archivos de salida. Aquí lo tienes:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

Primero, creamos un flujo de salida para el archivo ZIP. Luego, después de crear las opciones de conversión, configuramos la opción [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) para que sea una instancia de la clase [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputZipDirectory).

## El concepto de terminal de salida.

Hay otra parte importante de la salida: la salida del terminal. En cuanto a este, **Aspose.TeX para Java** define la interfaz general [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) con dos métodos. Uno de ellos devuelve una instancia [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Otro devuelve una instancia [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) como flujo subyacente. Las implementaciones proporcionadas de la interfaz se analizan a continuación.

### Escribir la salida del terminal en la consola

Para hacer esto, necesitamos configurar la opción [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalOut--) para que sea una instancia de la clase [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/OutputConsoleTerminal).

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

Nuevamente, este es el valor predeterminado de la opción, por lo que no es necesario especificarlo. Debido a esto, esta sección tiene únicamente fines de demostración.

### Escribir la salida del terminal en un archivo

A diferencia del terminal de entrada, **Aspose.TeX para Java** proporciona una implementación de [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal), que nos permite escribir la salida del terminal en un archivo en algún directorio de salida.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}} 

Aquí le pedimos al motor TeX que escriba la salida del terminal en el archivo con el nombre [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, que se almacenará en el mismo directorio de salida que especificamos para el resto de la salida. Pero esto no es necesario. También podríamos pasar cualquier otra instancia de cualquier implementación de [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) al constructor.