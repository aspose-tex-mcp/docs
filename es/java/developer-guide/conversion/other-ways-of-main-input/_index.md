---
translation: true
template: /templates/_template-java.md
title: Proporcionar el archivo de entrada TeX principal | Java
linktitle: Otras formas de proporcionar el archivo de entrada TeX principal
weight: 14
url: /java/other-ways-of-main-input/
description: La funcionalidad de conversión de la solución API Aspose.TeX para Java tiene un constructor que acepta una secuencia como primer argumento.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Proporcionar el archivo de entrada principal al motor TeX como una secuencia

Hasta este punto, sólo sabíamos cómo pasar el [archivo de entrada principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) al motor TeX como un nombre de archivo, ya sea completamente especificado o en formato corto, con o sin extensión. Pero hay otro [constructor](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) de la clase `TeXJob`, que acepta una secuencia como primer argumento. Esto es conveniente si por alguna razón tenemos el archivo de entrada principal en un formato que no sea un archivo en el sistema de archivos del disco. Así es como podemos afrontarlo:

Establezca `outputDirectory` en una carpeta de salida existente. Importe las clases Aspose.TeX usadas en los ejemplos, `com.aspose.tex.rendering.XpsDevice`, `com.aspose.tex.rendering.XpsSaveOptions` y, para la entrada mediante flujo, `java.io.ByteArrayInputStream` y `java.nio.charset.StandardCharsets`. El método que llama al ejemplo debe gestionar o declarar las excepciones. Aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación. El ejemplo de flujo contiene un documento LaTeX completo, por lo que no necesita un directorio de trabajo de entrada. Los flujos y dispositivos permanecen abiertos hasta que termina el trabajo y después se cierran o liberan.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-StreamInput-LaTeX.java" >}}

Cuando la entrada mediante flujo no tiene un nombre de trabajo asignado explícitamente, el motor usa el nombre predeterminado *texput*. Este ejemplo crea `texput.xps` y `texput.log`. Use `options.setJobName(...)` para elegir otro nombre de trabajo. Consulte [aquí](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) y [aquí](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name) para obtener detalles sobre los nombres de trabajo.

## Ingresando el archivo de entrada TeX principal desde la terminal

Hay otro [constructor](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)  de la clase `TeXJob`, que no nos permite especificar la entrada en absoluto. Entonces, ¿qué va a procesar un trabajo TeX de este tipo?, te preguntarás. Esta vez necesitaremos un terminal de entrada. El motor TeX nos pedirá que introduzcamos el nombre del archivo desde la terminal.

Establezca `inputDirectory` en una carpeta con un documento LaTeX completo llamado `hello-world.ltx`, y `outputDirectory` en una carpeta de salida existente. Ejecute el ejemplo en una consola, introduzca `hello-world.ltx` en el indicador `**` y pulse Enter. Crea `hello-world.xps` y escribe la salida del terminal en la consola. Ambos ejemplos usan `NonstopMode` para el procesamiento, pero el constructor del terminal sigue necesitando el nombre de archivo inicial. Para la ejecución desatendida, proporcione una implementación de `IInputTerminal` o use entrada mediante archivo o flujo.

Aquí está el código:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-MainInputTerminal.java" >}}

Nada más ejecutarlo el motor se queda esperando a que introduzcamos el nombre del archivo (con o sin ruta, con o sin extensión):


![Ventana de terminal](/tex/images/java/Conversion-MainInputTerminal.png)

Y así quedaría en el terminal de salida que es la consola:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```