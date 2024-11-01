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


## Cómo configurar el modo de interacción

Como mencionamos [aquí](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX para Java** nos permite configurar el modo de interacción inicial en el que se inicia el motor. Así es como lo hacemos:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-InteractionMode.java" >}}

## Cómo configurar el nombre del trabajo

Cuando pasamos el archivo de entrada principal como nombre de archivo, obtenemos archivos de salida con el mismo nombre, aunque con otras extensiones. El motor TeX llama al nombre del archivo de entrada *nombre del trabajo* y lo utiliza para los archivos de salida, excepto en los casos en que se escriben archivos auxiliares con otros nombres especificados explícitamente. Cuando pasamos el archivo de entrada principal como [flujo](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), el motor TeX usa el nombre de trabajo predeterminado, que es *texput*.
En ambos casos, podemos anular el nombre del trabajo asignando la opción de conversión adecuada.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-JobName.java" >}}

## Cómo "detener el tiempo"

LaTeX tiene una función para generar automáticamente un título a partir de algunas definiciones del preámbulo. Este título normalmente contiene la fecha actual. Es posible que deseemos congelar la fecha en algún valor deseado. Así es como se puede hacer:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-DateTime.java" >}}

## Cómo ignorar paquetes faltantes

Es posible que queramos convertir un archivo LaTeX que haga referencia a algunos paquetes que no son compatibles con la biblioteca Aspose.TeX para .NET. En este caso, el motor TeX se detendrá con un error al intentar cargar dicho paquete. Para evitar esto, podemos utilizar la siguiente opción:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.java" >}}

## Cómo evitar la construcción de ligaduras

Normalmente, el motor TeX crea ligaduras para ciertos pares de caracteres si la fuente proporciona los datos necesarios para hacerlo. Podemos indicarle al motor que omita la creación de ligaduras con el siguiente código:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-NoLigatures.java" >}}

## Cómo repetir el trabajo

Como mencionamos [arriba](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) con respecto a las etiquetas y referencias, hay casos en los que es posible que deseemos ejecutar el mismo trabajo dos veces. Así es como se puede hacer:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-Repeat.java" >}}

## Cómo convertir fórmulas matemáticas en imágenes rasterizadas

A veces es posible que necesitemos tener fórmulas matemáticas como imágenes rasterizadas en lugar de fuentes escritas. Para ello puede servir la siguiente opción:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RasterizeFormulas.java" >}}

## Cómo convertir gráficos en imágenes rasterizadas

El motor ObjectTeX nos permite incluir archivos gráficos en formatos rasterizados (PNG y JPG) así como en formatos PS(EPS) y XPS(OXPS). Los dos últimos formatos suelen contener elementos vectoriales y textos. Para tenerlas rasterizadas e incluidas como imágenes sólidas podemos utilizar la siguiente opción:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.java" >}}

## Cómo subconjuntos de fuentes

En caso de que queramos reducir el tamaño del archivo de salida, podemos recurrir al subconjunto de fuentes, lo que significa que las fuentes en el documento de salida solo contendrán datos sobre los glifos que se utilizan en el documento. Así es como podemos resolver esto:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-SubsetFonts.java" >}}