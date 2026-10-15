---
translation: true
template: /templates/_template-java.md
title: Otros formatos de salida de conversión TeX | Java
linktitle: Otros formatos TeX
weight: 18
url: /java/other-tex-formats/
description: La funcionalidad de conversión de la solución API Aspose.TeX para Java permite convertir archivos LaTeX y sus propios archivos TeX personalizados.
lastmod: "2026-04-21"
---

{{<section overview>}}

Es muy poco probable que actualmente quieras convertir un archivo TeX escrito en cualquier otro formato que no sea LaTeX. Pero esto es posible si estás estudiando el lenguaje TeX y/o sus aspectos internos por algún motivo. De todos modos, **Aspose.TeX para Java** te permite convertir archivos escritos en formato Plain TeX. También le permite crear formatos personalizados y componer documentos diseñados en estos formatos.

Comenzaremos creando un formato personalizado.

## Creando un formato personalizado

Recordemos que el archivo de formato es un volcado binario del estado interno del motor TeX.

Establezca `inputDirectory` en una carpeta que contenga `customtex.tex` y sus dependencias, y `outputDirectory` en una carpeta de salida existente. El archivo fuente del formato debe terminar con `\dump`; este ejemplo crea allí `customtex.fmt`. Importe las clases de Aspose.TeX utilizadas en los ejemplos y, para la composición, `com.aspose.tex.rendering.XpsDevice`, `java.io.ByteArrayInputStream` y `java.nio.charset.StandardCharsets`. El método que llama al ejemplo debe gestionar o declarar las excepciones. Aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación.

{{< gist "aspose-com-gists" "d21a098d3848236e0c258661f5bbc0ae" "Example-CreateCustomTeXFormat.java" >}}

Como puede ver, el código es similar al código para convertir un archivo TeX. Pero hay algunas diferencias.

Primero, aquí usamos la configuración del trabajo [TeXConfig.objectIniTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectIniTeX--) . Se trata de una configuración especial que deja el estado del motor "virgen", es decir, los parámetros internos tienen sus valores por defecto y el conjunto de secuencias de control coincide con el conjunto de primitivas. En nuestro ejemplo, el conjunto de primitivas se amplía en el sentido mencionado [aquí](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

A continuación, configuramos los directorios de trabajo de entrada y salida como de costumbre. El directorio de trabajo de entrada debe contener el archivo fuente del formato principal y todas sus dependencias.

Y la segunda diferencia clave es la forma en que ejecutamos el trabajo. En esta ocasión usamos el método estático [createFormat()](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#createFormat-java.lang.String-com.aspose.tex.TeXOptions-) , que junto con las opciones toma el nombre del archivo fuente principal, que debe ser el mismo que el nombre del formato.

## Componer un archivo TeX en su formato personalizado

Ahora que tenemos nuestro propio formato TeX, queremos componer un archivo TeX escrito en este formato. Aquí está el código:

Establezca `formatDirectory` en la carpeta que contiene el archivo `customtex.fmt` creado anteriormente, y `outputDirectory` en una carpeta de salida existente. El ejemplo compone un flujo de texto autónomo en `typeset-with-custom-format.xps`, por lo que no necesita un directorio de trabajo de entrada. Establezca uno cuando la entrada principal tenga dependencias, como imágenes.

{{< gist "aspose-com-gists" "d21a098d3848236e0c258661f5bbc0ae" "Example-TypesetWithCustomTeXFormat.java" >}}

Obviamente, tenemos que especificar el formato de alguna manera. En primer lugar, necesitamos crear una instancia de la clase [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/formatprovider/) . Luego, en el constructor de opciones, usamos la configuración [TeXConfig.objectTeX(FormatProvider)](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectTeX-com.aspose.tex.FormatProvider-), que toma nuestro proveedor de formato como argumento y carga el formato encima del estado "virgen" del motor.

Ambos ejemplos se ejecutan sin interacción y capturan la salida del terminal en memoria. Tras el trabajo, el ejemplo de composición cierra el flujo de entrada, libera el dispositivo XPS y cierra el directorio de trabajo y el proveedor de formato. Estas funciones se explican anteriormente en esta [guía](/tex/{{lang.url-fragment}}java/conversion/).

## Composición tipográfica de un archivo TeX en formato Plain TeX

Si utilizamos `TeXConfig.objectTeX()` sin un proveedor de formato, el motor cargará el formato predeterminado, que es [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) en su cuarto sentido. Por lo tanto, si tiene un archivo TeX escrito en formato Plain TeX, de esta manera puede convertirlo a cualquier formato de destino compatible.