---
translation: true
template: /templates/_template-java.md
title: Otras opciones de gestión de TeX | Java
linktitle: Otras opciones
weight: 17
url: /java/other-options/
description: La funcionalidad de conversión de la solución API Aspose.TeX para Java permite establecer el modo de interacción inicial en el que se inicia el motor.
lastmod: "2024-10-30"
---

{{<section overview>}}


Cada ejemplo crea `TeXOptions` para LaTeX y configura una opción. Pase estas opciones a un `TeXJob`, proporcione una entrada LaTeX adecuada y establezca un directorio de trabajo de salida antes de ejecutar el trabajo. Importe `com.aspose.tex.TeXOptions`, `TeXConfig` y las clases usadas en el ejemplo seleccionado: `Interaction`, `com.aspose.tex.rendering.XpsSaveOptions` o `PdfSaveOptions`, y `java.util.Calendar`/`GregorianCalendar` para el ejemplo de fecha. Gestione o declare las excepciones en el método que llama al ejemplo. Los ejemplos de rasterización y subconjuntos de fuentes usan `PdfSaveOptions`; renderice con un `PdfDevice` compatible. Aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/).

## Cómo configurar el modo de interacción

Como mencionamos [aquí](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX para Java** nos permite configurar el modo de interacción inicial en el que se inicia el motor. Así es como lo hacemos:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-InteractionMode.java" >}}

## Cómo configurar el nombre del trabajo

Cuando pasamos el archivo de entrada principal como nombre de archivo, obtenemos archivos de salida con el mismo nombre, aunque con otras extensiones. El motor TeX llama al nombre del archivo de entrada *nombre del trabajo* y lo utiliza para los archivos de salida, excepto en los casos en que se escriben archivos auxiliares con otros nombres especificados explícitamente. Cuando pasamos el archivo de entrada principal como [flujo](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream), el motor TeX usa el nombre de trabajo predeterminado, que es *texput*.
En ambos casos, podemos anular el nombre del trabajo asignando la opción de conversión adecuada.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-JobName.java" >}}

## Cómo "detener el tiempo"

LaTeX tiene una función para generar automáticamente un título a partir de algunas definiciones del preámbulo. Este título normalmente contiene la fecha actual. Es posible que deseemos congelar la fecha en algún valor deseado. Así es como se puede hacer:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-DateTime.java" >}}

## Cómo ignorar paquetes faltantes

Un archivo LaTeX puede hacer referencia a paquetes que no están disponibles en la biblioteca Aspose.TeX para Java. El motor normalmente se detiene con un error al intentar cargar uno de estos paquetes. Use `ignoreMissingPackages(true)` para omitir los paquetes no disponibles. Esto no proporciona los comandos que definirían esos paquetes; la entrada no debe depender de ellos.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-IgnoreMissingPackages.java" >}}

## Cómo evitar la construcción de ligaduras

Normalmente, el motor TeX crea ligaduras para ciertos pares de caracteres si la fuente proporciona los datos necesarios para hacerlo. Podemos indicarle al motor que omita la creación de ligaduras con el siguiente código:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-NoLigatures.java" >}}

## Cómo repetir el trabajo

Como mencionamos [arriba](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) con respecto a las etiquetas y referencias, hay casos en los que es posible que deseemos ejecutar el mismo trabajo dos veces. Así es como se puede hacer:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-Repeat.java" >}}

## Cómo convertir fórmulas matemáticas en imágenes rasterizadas

A veces es posible que necesitemos tener fórmulas matemáticas como imágenes rasterizadas en lugar de fuentes escritas. Para ello puede servir la siguiente opción:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeFormulas.java" >}}

## Cómo convertir gráficos en imágenes rasterizadas

El motor ObjectTeX nos permite incluir archivos gráficos en formatos rasterizados (PNG y JPG) así como en formatos PS(EPS) y XPS(OXPS). Los dos últimos formatos suelen contener elementos vectoriales y textos. Para tenerlas rasterizadas e incluidas como imágenes sólidas podemos utilizar la siguiente opción:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeIncludedGraphics.java" >}}

## Cómo subconjuntos de fuentes

Los subconjuntos de fuentes limitan las fuentes incrustadas a los glifos usados en el documento. El efecto sobre el tamaño de salida depende de la fuente y de cómo la incrusta el dispositivo de salida. Asigne las opciones de guardado antes de activar `subsetFonts(true)`, como se muestra a continuación:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-SubsetFonts.java" >}}