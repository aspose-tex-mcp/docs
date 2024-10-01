---
translation: true
template: /templates/_template-python-net.md
title: Otras opciones de gestión de TeX | Pitón
linktitle: Otras opciones
weight: 17
url: /python-net/other-options/
description: La solución API Aspose.TeX para Python incluye una funcionalidad de conversión que le permite configurar el modo de interacción inicial en el que se inicia el motor.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Configurar el modo de interacción

Como se menciona [en el párrafo de interacción TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX para Python** proporciona la capacidad de establecer el modo de interacción inicial en el que se inicia el motor. A continuación se muestra un ejemplo de cómo se puede hacer:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InteractionMode.py" >}}

## Configurar el nombre del trabajo

Cuando el archivo de entrada principal se proporciona como un nombre de archivo, los archivos de salida resultantes tendrán el mismo nombre pero con diferentes extensiones. El motor TeX se refiere al nombre del archivo de entrada como *nombre del trabajo* y lo utiliza para los archivos de salida. La excepción son los archivos auxiliares con nombres de archivo especificados explícitamente. Sin embargo, cuando el archivo de entrada principal se pasa como [flujo](/tex/{{lang.url-fragment}}python-net/other-ways-of-main-input/#supplying-the-main-input-file-as-a-stream), el motor TeX utiliza el nombre de trabajo predeterminado, que es *texput*. En ambos escenarios, es posible anular el nombre del trabajo asignando la opción de conversión adecuada.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-JobName.py" >}}

## "Deteniendo el tiempo"

Para generar automáticamente un título a partir de ciertas definiciones en el preámbulo, LaTeX ofrece una función que normalmente incluye la fecha actual. Sin embargo, puede haber casos en los que queramos fijar la fecha en un valor específico. Aquí hay un método para lograrlo:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-DateTime.py" >}}

## Ignorar paquetes faltantes

Si tenemos un archivo LaTeX que incluye referencias a paquetes que no son compatibles con la biblioteca **Aspose.TeX para Python**, el motor TeX encontrará un error y se detendrá al intentar cargar estos paquetes. Para evitar esto, podemos utilizar la siguiente opción:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.py" >}}

## Cómo evitar la construcción de ligaduras

De forma predeterminada, el motor TeX construye ligaduras para pares de caracteres específicos si la fuente contiene los datos necesarios. Sin embargo, podemos indicarle al motor que omita la construcción de ligaduras usando el siguiente código:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-NoLigatures.py" >}}

## repitiendo el trabajo

Como se menciona [en el párrafo 3 del archivo de entrada de LaTeX], etiquetas y referencias, hay situaciones en las que es posible que necesitemos ejecutar el mismo trabajo dos veces. Aquí hay un método para lograrlo:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-Repeat.py" >}}

## Convertir fórmulas matemáticas en imágenes rasterizadas

Si es necesario convertir fórmulas matemáticas en imágenes rasterizadas en lugar de representarlas con fuentes, se puede utilizar la siguiente opción para este propósito:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RasterizeFormulas.py" >}}

## Convertir gráficos en imágenes rasterizadas

El motor ObjectTeX proporciona la capacidad de incluir archivos gráficos en formatos rasterizados como PNG y JPG, así como formatos PS (EPS) y XPS (OXPS). Los dos últimos formatos suelen contener elementos vectoriales y texto. Si queremos rasterizarlas e incluirlas como imágenes sólidas, podemos utilizar la siguiente opción:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.py" >}}

## Subconjunto de fuentes

Si deseamos reducir el tamaño del archivo de salida, podemos emplear subconjuntos de fuentes, lo que implica que las fuentes en el documento resultante no incluirán datos para aquellos glifos que no están presentes en el documento. Aquí hay una solución para lograr esto:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-SubsetFonts.py" >}}