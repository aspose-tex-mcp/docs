---
translation: true
template: /templates/_template-java.md
title: Interfaz de entrada de Aspose.TeX | Java
linktitle: Interfaz de entrada de Aspose.TeX
weight: 15
url: /java/aspose-tex-input/
description: La funcionalidad de conversión de la solución API Aspose.TeX para Java con TeX, como formato de entrada, se explica aquí con los ejemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

Consulte **Aspose.TeX para Java** [referencia de API](https://reference.aspose.com/tex/java/com.aspose.tex/) para obtener definiciones formales de implementación de E/S.

Los ejemplos de sistema de archivos y ZIP componen `hello-world.tex` en `hello-world.xps`. Establezca `inputDirectory` en una carpeta con el archivo TeX y `outputDirectory` en una carpeta de salida existente. Para la entrada ZIP, `inputZip` debe ser un `java.nio.file.Path` que apunte a un archivo con `in/hello-world.tex`. Importe las clases Aspose.TeX usadas en el ejemplo seleccionado, `com.aspose.tex.rendering.XpsDevice` y las clases necesarias de `java.io` y `java.nio.file`. El método que llama al ejemplo debe gestionar o declarar las excepciones. Aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación.

## El concepto del directorio de entrada.

Dado que las primitivas de E/S del lenguaje TeX solo pueden manejar nombres de archivos, **Aspose.TeX para Java** define un directorio como un mapeo entre nombres y grandes cantidades de datos. Se supone que la gran cantidad de datos son archivos, secuencias, matrices o cualquier otra cosa. La API nos permite especificar los directorios de trabajo de entrada y salida por separado. Proporciona la interfaz general [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), que el usuario puede implementar para sus propios fines. También proporciona sus propias implementaciones, que se analizarán a continuación. La interfaz define el método [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), que devuelve el flujo de datos y determina el nombre completo del archivo, mientras toma algún nombre, hipotéticamente diferente, como primer argumento, que, de hecho, es la clave de mapeo. .

### Obtener entrada de archivos del sistema de archivos del disco

Así es como lo haríamos:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputFileSystemDirectory.java" >}}

Este caso de uso es bastante simple, por lo que no nos detendremos en él por mucho tiempo.

### Obtener entrada de archivo desde un archivo ZIP

También podemos poner los archivos de entrada en un archivo ZIP y considerarlo un directorio de entrada. En este caso debemos proceder de la siguiente manera:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputZipDirectory.java" >}}

Primero, creamos la secuencia que contiene el archivo ZIP. Luego, después de crear las opciones de conversión, configuramos la opción [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) para que sea una instancia de la clase [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/). El segundo argumento del constructor es la ruta base dentro del archivo. Si queremos que todo el archivo sea un directorio de entrada, debemos pasar la cadena vacía. El ejemplo mantiene abiertos el flujo ZIP y el directorio de entrada hasta que termina el trabajo TeX y después los cierra. Se ejecuta sin interacción y captura la salida del terminal en memoria.

## El concepto de terminal de entrada.

Ahora recordemos que también está la entrada del terminal. En cuanto a este, **Aspose.TeX para Java** define la interfaz general [IInputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/) con dos métodos. Uno de ellos devuelve una instancia [BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html). Otro método devuelve un [InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) como flujo subyacente. Las implementaciones proporcionadas de la interfaz se analizan a continuación.

### Obtener entrada de terminal desde la consola

Para hacer esto, necesitamos configurar la opción [TerminalIn](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--) para que sea una instancia de la clase [InputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputConsoleTerminal.java" >}}

`InputConsoleTerminal` es el valor predeterminado de esta opción. Este ejemplo solo muestra la configuración del terminal y no ejecuta un trabajo. Un trabajo que solicita entrada del terminal necesita datos del usuario o una implementación personalizada del terminal. Los ejemplos de sistema de archivos y ZIP anteriores se ejecutan sin interacción con archivos de entrada completos.

En teoría, si tenemos un archivo (o secuencia de comandos) TeX interactivo con un comportamiento predecible, es posible que deseemos implementar una versión del terminal de entrada que contenga una secuencia de comandos complementaria para responder a las solicitudes del motor TeX. ¡Prueba suerte cuando tengas tiempo!