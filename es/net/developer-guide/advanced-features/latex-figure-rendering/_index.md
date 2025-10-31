---
translation: true
template: /templates/_template-net.md
title: Representación de figuras LaTeX | .NET
linktitle: LaTeX incluye figura
weight: 20
url: /net/latex-figure-rendering/
description: Este artículo describe la representación de fragmentos de LaTeX (figuras) con Aspose.TeX para .NET. Consulte los ejemplos de código para esta función.
keywords: figura de LaTeX, tamaño de figura de LaTeX, imagen de LaTeX, imagen de LaTeX, figura incluida de LaTeX, imagen de LaTeX, opciones de figura de LaTeX
lastmod: "2024-10-30"
---

{{<section overview>}}


A veces es posible que desees extraer algún contenido de un archivo LaTeX como una pieza renderizada por separado, o una *"figura"*, sin ninguna conexión con el diseño de la página. Puede ser una ilustración para tu publicación en Internet, por ejemplo. Puedes hacerlo con nuestra API. En cuanto a los formatos de destino, hay dos opciones: PNG y SVG. Como es el caso de la función de representación de fórmulas matemáticas de LaTeX. También vale la pena señalar que **representación de figuras LaTeX** es una generalización de [representación de fórmulas matemáticas LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).

## Cómo renderizar una figura de LaTeX a PNG

La sección de referencia de API relacionada con este tema está [aquí](https://reference.aspose.com/tex/net/aspose.tex.features/). Y al igual que con la representación de fórmulas, comenzaremos con un ejemplo. Aquí lo tienes:

{{< gist "aspose-com-gists" "79be6a0d7a31aa5deb213ba4ca81cb1b" "Example-RenderFigureToPNG.cs" >}}

En primer lugar, creamos una instancia de [opciones de figura LaTeX](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/). Lo hacemos aquí especificando simultáneamente la resolución de la imagen de salida.

A continuación, especificamos el preámbulo. No hay un preámbulo predeterminado para la representación de figuras en LaTeX, por lo que si, por ejemplo, va a representar algunos gráficos trazados usando el paquete LaTeX `pict2e`, debe especificarlo en el preámbulo:

```tex
\usepackage{pict2e}
```

Luego le indicamos al renderizador que escale la salida en un 300%.

La siguiente opción define el color de fondo. A diferencia de la representación de fórmulas matemáticas, no especificamos un color de primer plano ya que asumimos que los colores están completamente bajo el control del código LaTeX. De hecho, también lo es el color de fondo, por lo que esta es solo una opción conveniente.

La siguiente línea del ejemplo no tiene mucho sentido. Simplemente demuestra que puede dirigir la salida del registro a alguna secuencia.

Y la última opción `ShowTerminal` le permite alternar la escritura de la salida del terminal en la consola.

El método que realmente realiza el renderizado es [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). Devuelve el tamaño de la figura en puntos.

El método acepta la secuencia donde se escribirá la imagen como segundo argumento. Creamos la secuencia a continuación.

Y finalmente, llamamos al método `FigureRenderer.Render()`, pasando opciones como tercer argumento. El código LaTeX de la figura se pasa como primer argumento.

Las últimas líneas del ejemplo imprimen dos artefactos de la representación de la figura: el tamaño de la figura y el breve informe de errores (en caso de que haya errores).

Aquí está el resultado del renderizado.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![Representación de figuras LaTeX a PNG](/tex/images/net/text-and-formula.png)</a>

Este es el caso de uso más general para la función **Representación de figuras LaTeX**.

## Cómo renderizar una figura de LaTeX a SVG

De la misma manera, podemos representar una figura de LaTeX en formato SVG.

{{< gist "aspose-com-gists" "79be6a0d7a31aa5deb213ba4ca81cb1b" "Example-RenderFigureToSVG.cs" >}}

Las diferencias son:

* Usamos la clase [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) en lugar de [PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* No especificamos la resolución.
* Usamos la clase [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) en lugar de [PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).


Aquí está el resultado:

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![Representación de figuras LaTeX a SVG](/tex/images/net/text-and-formula.svg)</a>
