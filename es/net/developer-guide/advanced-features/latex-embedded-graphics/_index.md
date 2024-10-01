---
translation: true
template: /templates/_template-net.md
title: Gráficos integrados LaTeX | Incluir gráficos en el código LaTeX
linktitle: Gráficos integrados LaTeX
weight: 18
url: /net/latex-embedded-graphics/
keywords: includegraphics latex, gráficos base64 incrustados de látex, gráficos codificados en base64 de látex, write18, shell-escape, comando de shell de látex
description: Este artículo cubre cómo incluir imágenes codificadas en base64 en el código fuente de LaTeX, así como la característica \write18 que lo hace posible.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Otra forma de incluir imágenes.

Algunos sistemas TeX/LaTeX permiten incluir imágenes que no se almacenan externamente con respecto al archivo LaTeX en sí, sino que se incluyen directamente dentro del archivo LaTeX. Sin embargo, dado que los archivos TeX/LaTeX son archivos de texto sin formato y, por lo tanto, no pueden contener datos binarios, necesitamos una forma de representar datos binarios en forma de texto. En otras palabras, los datos binarios deben codificarse en alguna representación de texto. El problema es que un motor TeX no puede interpretar directamente dichas imágenes codificadas. De hecho, incluir una imagen se logra usando el antiguo comando `\includegraphics` del paquete `graphicx`. Sin embargo, este comando sólo puede manejar archivos de imágenes externos. Sí, se seguirá creando un archivo de imagen externo (junto con otro archivo intermediario) fuera del archivo LaTeX. El punto clave es que sólo necesita distribuir el archivo LaTeX.

Bien, digamos que de alguna manera colocamos una imagen codificada en el archivo LaTeX. Pero, ¿cómo conseguimos decodificar la imagen? Lamentablemente, no podemos decodificar el archivo leyéndolo del archivo LaTeX y escribiéndolo en el archivo de imagen externo. La cadena de texto que representa la imagen codificada debe escribirse primero en un archivo de texto externo, que luego se puede decodificar para producir un archivo de imagen.

A estas alturas, podemos delinear los siguientes pasos para obtener el resultado deseado:

1. Codifique la imagen.
2. Inyecte la cadena de texto que representa los datos de la imagen en el archivo LaTeX.
3. Envíe la cadena de texto que representa los datos de la imagen a un archivo externo.
4. Decodifica el archivo externo del Paso 3.
5. Incluya la imagen decodificada.

Los dos primeros pasos los completa el autor del archivo LaTeX. Un motor TeX se encargará de los pasos restantes, siempre que se le indique correctamente, por supuesto.

Empecemos desde el principio. ¿Cómo podemos codificar nuestra imagen para obtener una cadena de caracteres? Uno de los métodos para hacer esto (y probablemente el más popular) es **Base64**.

## Codificación de datos binarios usando Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) es un grupo de esquemas de codificación de binario a texto que transforma datos binarios en una secuencia de caracteres imprimibles, limitada a un conjunto de 64 caracteres únicos. Más específicamente, los datos binarios de origen se toman 6 bits a la vez y luego este grupo de 6 bits se asigna a uno de los 64 caracteres únicos. Al igual que con todos los esquemas de codificación de binario a texto, **Base64** está diseñado para transportar datos almacenados en formatos binarios a través de canales que solo admiten de manera confiable contenido de texto.

Podemos ver en esta breve explicación que **Base64** es lo que necesitamos. Para codificar un archivo de imagen en **Base64**, puede utilizar una utilidad de línea de comandos (si está disponible en su sistema operativo), funciones estándar o de terceros de casi todos los lenguajes de programación o herramientas en línea como [Base64.guru](https://base64.guru/converter/encode/file) o similar.

## Colocar la imagen codificada en el archivo LaTeX

La cadena de caracteres que obtiene como resultado de la codificación debe colocarse en el entorno estándar `filecontents*` de LaTeX en el preámbulo de un archivo LaTeX de la siguiente manera:

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Aquí lo tienes. El paso 2 está cumplido. ¡Tenemos la imagen dentro del archivo LaTeX! Pero ¿qué pasará cuando ejecutemos la composición tipográfica de este archivo con LaTeX?

Un procesador LaTeX escribirá la cadena de caracteres del entorno en un archivo externo llamado `sample-image.64`. Debido al uso de la opción "sobrescribir", el archivo se sobrescribirá si ya existe (por ejemplo, si fue producido por una ejecución anterior). ¡Y eso es lo que también logra el Paso 3!

## Decodificando una cadena base64

El paso 4 de nuestro plan es donde entran en juego las diferencias en las implementaciones de TeX. La decodificación de una cadena de caracteres Base64 se realiza mediante algo más común conocido como función `\write18`.

### `\escribir18`

En los motores TeX clásicos, `\write<número>(<lista de tokens>)` es la primitiva que escribe una *lista de tokens*. Cuando se utiliza, esta primitiva va seguida de un número entero. Si este número es negativo, los tokens se escriben en el archivo de transcripción (registro). Si el número es mayor que "15", los tokens se escriben en el terminal. Si el número está en el rango `0..15`, los tokens se escriben en un archivo cuyo nombre se especifica mediante una aparición anterior de la primitiva `\openout`. La primitiva `\openout<entero de 4 bits>=<nombre de archivo>` asigna un nombre de archivo a un número.

Las implementaciones TeX más nuevas (como PDF TeX) permiten el uso de `\write18`. En este caso, interpretan la `<lista de tokens>` como una línea de comando que se ejecutará en el shell del sistema operativo. Dado que esta característica es obviamente una puerta trasera potencial, es posible que sienta un toque de misterio cada vez que se menciona en la documentación relacionada con TeX o en Internet. Por este motivo, los ejecutables PDF TeX/LaTeX tienen opciones de comando para gestionar la accesibilidad de esta función.

Generalmente, existen tres niveles de accesibilidad: deshabilitado, habilitado con restricciones y completamente habilitado.

En **Aspose.TeX**, hay una opción de trabajo TeX llamada `ShellMode`, pero solo hay dos valores adecuados: `NoShellEscape` y `ShellRestricted`. El valor `NoShellEscape` significa que la función está deshabilitada. El segundo valor indica que cualquier comando que deba ejecutarse debe ser implementado por el usuario como una extensión de la clase "Ejecutable". Aquí no profundizaremos en los detalles de dichas implementaciones, pero mencionaremos que la emulación del comando `base64` ya está implementada en Aspose.TeX. De forma predeterminada, puede encontrar su instancia prototipo en la propiedad de colección `Executables` de la instancia de clase `TeXOptions`.

### Decodificación de datos codificados en Base64

Para decodificar el contenido de un archivo que se supone que son datos codificados en Base64, normalmente usaríamos la siguiente línea de comando:

```
base64 -d  FILE1 > FILE2
```

donde ARCHIVO1 es el archivo "codificado" y `> ARCHIVO2` significa que la salida debe redirigirse al archivo `FILE2`.

Así, en el cuerpo de nuestro archivo LaTeX, deberíamos añadir la siguiente línea:

```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> El prefijo `\immediate` es necesario para garantizar que la operación `\write` se realice tan pronto como el escáner TeX encuentre el comando primitivo. De lo contrario, se procesará en el momento del envío de la página.

Si ejecutamos la composición tipográfica del archivo ahora, veremos que se crea el archivo de imagen `sample-image.png`. ¡Vamos, ábrelo en un visor para comprobarlo!

## Incluyendo la imagen decodificada.

Como mencionamos al principio del artículo, para incluir la imagen decodificada utilizamos el conocido comando LaTeX `\includegraphics`:

```tex
\includegraphics[options]{sample-image.png}
```

Por lo tanto, el archivo LaTeX completo (casi) podría tener el siguiente aspecto:

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \write18{base64 -d  sample-image.64 > sample-image.png}
  \includegraphics[options]{sample-image.png}
\end{document}
```

Y el código C# que utiliza la API **Aspose.TeX** es similar al de otros artículos, excepto por especificar la opción `ShellMode`:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.cs" >}}

Y ahora hemos terminado con el **Paso 5**. Para ver ejemplos verdaderamente completos, explore nuestro [Proyecto de ejemplo](https://github.com/aspose-tex/Aspose.TeX-for-.NET).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex/) de conversión gratuita creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**