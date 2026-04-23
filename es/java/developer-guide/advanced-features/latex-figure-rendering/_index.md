---
translation: true
template: /templates/_template-java.md
title: Representación de figuras LaTeX | Aspose.TeX para Java
linktitle: Representación de figuras de LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: Este artículo describe, con ejemplos de código, la representación de fragmentos de LaTeX (figuras) con Aspose.TeX para Java.
lastmod: "2026-04-21"
---

{{<section overview>}}

Puede suceder que desee extraer algún contenido (un dibujo, un escrito, una trama, etc.) de un archivo LaTeX como una pieza renderizada por separado, o una *"figura"*, independientemente de su lugar en la página del documento de salida. . Este es el caso, por ejemplo, de una ilustración para su publicación en Internet. Nuestra API puede ayudarle con la tarea. Hay dos formatos de destino disponibles: PNG y SVG. Al igual que en la representación de fórmulas matemáticas de LaTeX. También debemos tener en cuenta que la **representación de figuras LaTeX** es una generalización de la [representación de fórmulas matemáticas LaTeX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Cómo renderizar una figura de LaTeX a PNG

Y al igual que con la representación de fórmulas, comenzaremos con un ejemplo. Aquí lo tienes:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

En primer lugar, creamos una instancia de [opciones de renderizado](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions). Lo hacemos aquí junto con la especificación de la resolución de la imagen de salida.

A continuación, especificamos el preámbulo. No hay un preámbulo predeterminado para la representación de figuras en LaTeX, por lo que si desea, por ejemplo, representar algunos gráficos trazados usando el paquete LaTeX `pict2e`, debe especificarlo en el preámbulo:

```tex
\usepackage{pict2e}
```

Luego le indicamos al renderizador que escale la salida en un 300%.

La siguiente opción define el color de fondo. A diferencia de la representación de fórmulas matemáticas, no especificamos un color de primer plano ya que asumimos que los colores están completamente bajo el control del código LaTeX. De hecho, también lo es el color de fondo, por lo que esta es solo una opción conveniente.

La siguiente línea del ejemplo no tiene mucho sentido. Simplemente demuestra que puede dirigir la salida del registro a alguna secuencia.

Y la última opción `ShowTerminal` le permite alternar la escritura de la salida del terminal en la consola.

El método que realmente realiza el renderizado es [FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-). Devuelve el tamaño de la figura en puntos.

El método acepta la secuencia donde se escribirá la imagen como segundo argumento. Creamos la secuencia a continuación.

Y finalmente, llamamos al método `FigureRenderer.render()`, pasando opciones como tercer argumento. El código LaTeX de la figura se pasa como primer argumento.

Las últimas líneas del ejemplo imprimen dos artefactos de la representación de la figura: el tamaño de la figura y el breve informe de errores (en caso de que haya errores).

Aquí está el resultado del renderizado.

![Representación de figuras LaTeX a PNG](/tex/images/java/text-and-formula.png)

Este es el caso de uso más general para la función **Representación de figuras LaTeX**.

## Cómo renderizar una figura de LaTeX a SVG

De la misma manera, podemos renderizar una figura de LaTeX al formato SVG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

Las diferencias son:

 * Usamos la clase [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions) en lugar de [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions).
 * No especificamos la resolución.
 * Usamos la clase [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer) en lugar de [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer).


Aquí está el resultado:

<a href="/tex/images/java/text-and-formula.svg">![Representación de figuras LaTeX a SVG](/tex/images/java/text-and-formula.svg)</a>