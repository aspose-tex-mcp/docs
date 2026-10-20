---
translation: true
template: /templates/_template-java.md
title: Gráficos integrados LaTeX | Aspose.TeX para Java
linktitle: Gráficos integrados LaTeX
weight: 18
url: /java/latex-graphics-embedding/
keywords: includegraphics latex, gráficos base64 incrustados de LaTeX, gráficos codificados en base64 de LaTeX, write18, shell-escape, comando de shell de LaTeX
description: Explore cómo inyectar imágenes codificadas en Base64 en el código fuente LaTeX y aprenda la función \write18 que lo hace posible.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Una forma alternativa de incluir imágenes

Algunos sistemas TeX/LaTeX permiten la inclusión de imágenes que no se almacenan externamente en relación con el archivo LaTeX; en cambio, estas imágenes se incrustan directamente en el archivo LaTeX. Sin embargo, dado que los archivos TeX/LaTeX son texto sin formato y no pueden contener datos binarios, necesitamos un método para representar datos binarios en formato de texto. Esto significa que los datos binarios deben codificarse en una representación textual. El desafío es que un motor TeX no puede interpretar directamente estas imágenes codificadas. Al final, las imágenes se incluyen usando el conocido comando `\includegraphics` del paquete `graphicx`, pero este comando se limita a manejar archivos de imágenes externos. Por lo tanto, aún se debe crear un archivo de imagen externo (junto con un archivo intermediario adicional) fuera del archivo LaTeX, pero eso solo ocurrirá durante la composición tipográfica. La ventaja es que sólo necesita distribuir el archivo LaTeX en sí, en lugar de un conjunto de archivos.

Muy bien, supongamos que de alguna manera hemos incrustado una imagen codificada en el archivo LaTeX. ¿Cómo decodificamos esta imagen? Desafortunadamente, no podemos decodificarlo directamente leyéndolo del archivo LaTeX y escribiéndolo en un archivo de imagen externo. En cambio, la cadena de texto que representa la imagen codificada debe escribirse primero en un archivo de texto externo, que luego se puede decodificar para generar el archivo de imagen.

En este punto, podemos delinear los siguientes pasos para lograr el resultado deseado:

1. Codifique la imagen.
2. Inserte la cadena de texto que representa los datos de la imagen en el archivo LaTeX.
3. Escriba la cadena de texto que representa los datos de la imagen en un archivo externo.
4. Decodifica el archivo externo creado en el Paso 3.
5. Incluya la imagen decodificada.

Los dos primeros pasos los lleva a cabo el autor del archivo LaTeX. El motor TeX se encargará de los pasos restantes, siempre que reciba las instrucciones adecuadas, por supuesto.

Pasemos al **Paso 1**. ¿Cómo podemos codificar nuestra imagen para obtener una cadena de caracteres? Uno de los métodos para hacer esto (y probablemente el más popular) es **Base64**.

## Codificación de datos binarios usando Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) es un grupo de esquemas de codificación de binario a texto que transforma datos binarios en una secuencia de caracteres imprimibles, utilizando un conjunto de 64 caracteres únicos. Específicamente, los datos binarios de origen se procesan en grupos de 6 bits, y cada grupo se asigna a uno de los 64 caracteres únicos. Como todos los esquemas de codificación de binario a texto, Base64 está destinado a facilitar la transmisión de datos almacenados en formatos binarios a través de canales que admiten predominantemente contenido de texto.

Esta breve explicación muestra que **Base64** es exactamente lo que necesitamos. Para codificar un archivo de imagen en **Base64**, puede utilizar una utilidad de línea de comandos (si está disponible en su sistema operativo), funciones estándar o de terceros de casi todos los lenguajes de programación o herramientas en línea como [Base64.guru](https://base64.guru/converter/encode/file) o similar.

## Incrustar la imagen codificada en el archivo LaTeX

La cadena de caracteres generada a partir del proceso de codificación debe colocarse en el entorno estándar `filecontents` de LaTeX dentro del preámbulo de un archivo LaTeX, de la siguiente manera:

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

¡Aquí lo tienes! **El paso 2** está completo. ¡Hemos incrustado con éxito la imagen dentro del archivo LaTeX! ¿Pero qué pasará cuando ejecutemos la composición tipográfica de este archivo con LaTeX?"

Un procesador LaTeX escribirá la cadena de caracteres del entorno en un archivo externo llamado `sample-image.64`. Debido a la opción "sobrescribir", el archivo se sobrescribirá si ya existe (por ejemplo, si se creó durante una ejecución anterior). ¡Así es como también se logra el **Paso 3**!

## Decodificando una cadena base64

**El paso 4** de nuestro plan es donde entran en juego las diferencias en las implementaciones de TeX. La decodificación de una cadena de caracteres Base64 se realiza mediante algo más común conocido como función `\write18`.

### `\write18`

En los motores TeX clásicos, `\write<número>(<lista de tokens>)` es la primitiva utilizada para escribir una *lista de tokens*. Cuando se utiliza, esta primitiva va seguida de un número entero. Si el número entero es negativo, los tokens se escriben en el archivo de transcripción (registro). Si el número entero es mayor que "15", los tokens se envían al terminal. Si el número entero está dentro del rango de `0..15`, los tokens se escriben en un archivo cuyo nombre se especifica mediante una aparición anterior de la primitiva `\openout`. La primitiva `\openout<entero de 4 bits>=<nombre de archivo>` asocia un nombre de archivo con un número.

Las implementaciones TeX más nuevas, como PDF TeX, permiten el uso de `\write18`. En este caso, interpretan la `<lista de tokens>` como una línea de comando que se ejecutará en el shell del sistema operativo. Dado que esta característica obviamente plantea un riesgo potencial de seguridad, es posible que sienta un atisbo de misterio cada vez que se hace referencia a ella en documentación relacionada con TeX o en Internet. Por esta razón, los ejecutables PDF TeX/LaTeX ofrecen opciones de comando para controlar el acceso a esta función.

Normalmente, hay tres niveles de accesibilidad: deshabilitado, habilitado con restricciones y completamente habilitado.

En **Aspose.TeX**, hay una opción de trabajo TeX llamada `ShellMode`, que puede tomar uno de dos valores posibles: `NoShellEscape` y `ShellRestricted`. El valor `NoShellEscape` indica que la función está deshabilitada. El último valor significa que cualquier comando que requiera ejecución debe ser implementado por el usuario como una extensión de la clase "Ejecutable". No entraremos aquí en los detalles de dichas implementaciones, pero es importante tener en cuenta que la emulación del comando `base64` ya está implementada en Aspose.TeX y está incluida de forma predeterminada en la propiedad de colección `Executables` de la clase `TeXOptions`. instancia. La emulación integrada de `base64` se ejecuta dentro de Aspose.TeX y no requiere una utilidad Base64 del sistema operativo.

### Decodificación de datos codificados en Base64

Para decodificar el contenido de un archivo que se espera que contenga datos codificados en Base64, normalmente usaríamos la siguiente línea de comando:


```
base64 -d  FILE1 > FILE2
```

donde ARCHIVO1 es el archivo "codificado" y `> ARCHIVO2` redirige la salida al archivo `FILE2`.

Por tanto, deberíamos incluir la siguiente línea en el cuerpo de nuestro archivo LaTeX:

```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> El prefijo `\immediate` es necesario para garantizar que la operación `\write` se ejecute inmediatamente cuando el escáner TeX encuentre este primitivo. De lo contrario, se procesará durante el envío de la página.

Si ejecutamos la composición tipográfica del archivo ahora, encontraremos que se ha creado el archivo de imagen `sample-image.png`. ¡Continúe y ábralo en un visor para comprobarlo!

## Incluyendo la imagen decodificada.

Como señalamos al principio del artículo, para incluir la imagen decodificada utilizamos el conocido comando LaTeX `\includegraphics`:

```tex
\includegraphics[options]{sample-image.png}
```

El siguiente ejemplo muestra la estructura del documento. Sustituya la línea Base64 abreviada por los datos completos de la imagen; los puntos son un marcador y no se pueden decodificar:

```tex
\documentclass{article}
\usepackage{graphicx}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \immediate\write18{base64 -d sample-image.64 > sample-image.png}
  \includegraphics[width=\textwidth]{sample-image.png}
\end{document}
```

El ejemplo Java convierte el documento completo `embedded-base64-image.tex` a PDF. Asigne a `inputFile` la ruta completa de entrada y a `outputDirectory` una carpeta de salida existente. Importe las clases utilizadas de `com.aspose.tex`, `com.aspose.tex.rendering.PdfDevice` y `com.aspose.tex.rendering.PdfSaveOptions`. Gestione o declare las excepciones y aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/). El ejemplo activa `ShellRestricted` para el comando Base64 integrado, procesa sin interacción y captura la salida del terminal en memoria. El dispositivo PDF y el directorio de salida se liberan o cierran al terminar el trabajo. La carpeta contiene `sample-image.64`, la imagen decodificada `sample-image.png`, el PDF y el registro TeX:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-EmbeddedBase64Image.java" >}}

Y ahora el **Paso 5** está completo. Para ver ejemplos verdaderamente completos, explore nuestro [Proyecto de ejemplo](https://github.com/aspose-tex/Aspose.TeX-for-Java).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex/) de conversión gratuita creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**