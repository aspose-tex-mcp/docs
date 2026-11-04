---
translation: true
template: /templates/_template-net.md
title: Otras opciones de gestión de TeX | .NET
linktitle: Otras opciones
weight: 17
url: /net/other-options/
description: La funcionalidad de conversión de la solución API Aspose.TeX para .NET permite establecer el modo de interacción inicial en el que se inicia el motor.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Cómo configurar el modo de interacción

Como mencionamos [aquí](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX para .NET** nos permite configurar el modo de interacción inicial en el que se inicia el motor. Así es como lo hacemos:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-InteractionMode.cs" >}}

## Cómo configurar el nombre del trabajo {#how-to-set-the-job-name}

Cuando pasamos el archivo de entrada principal como nombre de archivo, obtenemos archivos de salida con el mismo nombre, aunque con otras extensiones. El motor TeX llama al nombre del archivo de entrada *nombre del trabajo* y lo utiliza para los archivos de salida, excepto en los casos en que se escriben archivos auxiliares con otros nombres especificados explícitamente. Cuando pasamos el archivo de entrada principal como [flujo](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream), el motor TeX usa el nombre de trabajo predeterminado, que es *texput*.
En ambos casos, podemos anular el nombre del trabajo asignando la opción de conversión adecuada.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-JobName.cs" >}}

## Cómo "detener el tiempo"

LaTeX tiene una función para generar automáticamente un título a partir de algunas definiciones del preámbulo. Este título normalmente contiene la fecha actual. Es posible que deseemos congelar la fecha en algún valor deseado. Así es como se puede hacer:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-DateTime.cs" >}}

## Cómo ignorar paquetes faltantes

Es posible que queramos convertir un archivo LaTeX que haga referencia a algunos paquetes que no son compatibles con la biblioteca Aspose.TeX para .NET. En este caso, el motor TeX se detendrá con un error al intentar cargar dicho paquete. Para evitar esto, podemos utilizar la siguiente opción:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-IgnoreMissingPackages.cs" >}}

## Cómo evitar la construcción de ligaduras

Normalmente, el motor TeX crea ligaduras para ciertos pares de caracteres si la fuente proporciona los datos necesarios para hacerlo. Podemos indicarle al motor que omita la creación de ligaduras con el siguiente código:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-NoLigatures.cs" >}}

## Cómo repetir el trabajo {#how-to-repeat-the-job}

Como mencionamos [arriba](/tex/{{lang.url-fragment}}net/latex-io/#latex-output-file) con respecto a las etiquetas y referencias, hay casos en los que nos gustaría ejecutar el mismo trabajo dos veces. Así es como se puede hacer:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-Repeat.cs" >}}

## Cómo convertir fórmulas matemáticas en imágenes rasterizadas

A veces es posible que necesitemos tener fórmulas matemáticas como imágenes rasterizadas en lugar de fuentes escritas. Para ello puede servir la siguiente opción:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RasterizeFormulas.cs" >}}

## Cómo convertir gráficos en imágenes rasterizadas

El motor ObjectTeX nos permite incluir archivos gráficos en formatos rasterizados (PNG y JPG) así como en formatos PS(EPS) y XPS(OXPS). Los dos últimos formatos suelen contener elementos vectoriales y textos. Para tenerlas rasterizadas e incluidas como imágenes sólidas podemos utilizar la siguiente opción:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RasterizeIncludedGraphics.cs" >}}

## Cómo subconjuntos de fuentes

En caso de que queramos reducir el tamaño del archivo de salida, podemos recurrir al subconjunto de fuentes, lo que significa que las fuentes en el documento de salida solo contendrán datos sobre los glifos que se utilizan en el documento. Así es como podemos resolver esto:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-SubsetFonts.cs" >}}
