---
translation: true
template: /templates/_template-java.md
title: Interfaz de salida de Aspose.TeX | Java
linktitle: Interfaz de salida de Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: La funcionalidad de conversión de la solución API Aspose.TeX para Java con TeX, como formato de salida, se explica aquí con los ejemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

Consulte **Aspose.TeX para Java** [referencia de API](https://reference.aspose.com/tex/java/com.aspose.tex/) para obtener definiciones formales de implementación de E/S.

Los ejemplos de sistema de archivos, ZIP y terminal componen `hello-world.tex` en XPS. Establezca `inputDirectory` en una carpeta con el archivo TeX y `outputDirectory` en una carpeta de salida existente. Para la salida ZIP, `outputZip` debe ser un `java.nio.file.Path` en una carpeta existente. Importe las clases Aspose.TeX usadas en el ejemplo seleccionado, `com.aspose.tex.rendering.XpsDevice` y las clases necesarias de `java.io` y `java.nio.file`. El método que llama al ejemplo debe gestionar o declarar las excepciones. Aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación.

## El concepto del directorio de salida.

Dado que las primitivas de E/S del lenguaje TeX sólo pueden tratar con nombres de archivos, Aspose.TeX define un directorio como un mapeo entre nombres y grandes cantidades de datos. Se supone que la gran cantidad de datos son archivos, secuencias, matrices o cualquier otra cosa. La API nos permite especificar los directorios de trabajo de entrada y salida por separado. Proporciona la interfaz general [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) para la salida, que el usuario puede implementar para sus propios fines. También proporciona sus propias implementaciones, que se analizarán a continuación. La interfaz extiende [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), ya que el motor puede primero crear y escribir un archivo y luego volver a leerlo. El método propio de la interfaz [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) devuelve la secuencia para escribir, a diferencia de la secuencia para leer devuelta por [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Escribir la salida del archivo en el sistema de archivos del disco

Como mencionamos [arriba](/tex/{{lang.url-fragment}}/java/conversion/), el valor más común para [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) probablemente sería una instancia de la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

Así es como lo configuraríamos:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

Este caso de uso es bastante simple, por lo que no nos detendremos en él por mucho tiempo.

### Escribir la salida del archivo en un archivo ZIP

También podemos crear un archivo (o secuencia) y dejar que el motor TeX lo use como un archivo ZIP para almacenar los archivos de salida. Aquí lo tienes:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

Primero, creamos un flujo de salida para el archivo ZIP. Luego, después de crear las opciones de conversión, configuramos la opción [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) para que sea una instancia de la clase [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/). El ejemplo almacena `hello-world.xps` y `hello-world.log` en el archivo. Después del trabajo, llame a `finish()` en el directorio de salida antes de cerrar el flujo subyacente. Los ejemplos mantienen abiertos sus flujos y directorios de trabajo hasta que termina el trabajo y después los cierran.

## El concepto de terminal de salida.

Hay otra parte importante de la salida: la salida del terminal. En cuanto a este, **Aspose.TeX para Java** define la interfaz general [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) con dos métodos. Uno de ellos devuelve una instancia [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Otro devuelve una instancia [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) como flujo subyacente. Las implementaciones proporcionadas de la interfaz se analizan a continuación.

### Escribir la salida del terminal en la consola

Para hacer esto, necesitamos configurar la opción [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) para que sea una instancia de la clase [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` es el valor predeterminado de esta opción. El ejemplo lo selecciona explícitamente y escribe la salida del terminal en la consola durante la conversión. Los cuatro ejemplos se ejecutan sin interacción; los ejemplos de sistema de archivos y ZIP capturan la salida del terminal en memoria.

### Escribir la salida del terminal en un archivo

A diferencia del terminal de entrada, **Aspose.TeX para Java** proporciona una implementación de [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), que nos permite escribir la salida del terminal en un archivo en algún directorio de salida.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

Establezca el directorio de trabajo de salida antes de crear `OutputFileTerminal`. Escribe la salida del terminal en [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, aquí `hello-world.trm`, en ese directorio. Este archivo del terminal es independiente de la transcripción TeX `hello-world.log`. Para escribir la salida del terminal en otro lugar, pase al constructor otra implementación de [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/).