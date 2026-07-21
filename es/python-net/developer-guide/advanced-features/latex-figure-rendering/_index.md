---
translation: true
template: /templates/_template-python-net.md
title: Representación de figuras LaTeX | Aspose.TeX para Python
linktitle: LaTeX incluye figura
weight: 20
url: /python-net/latex-figure-rendering/
description: El artículo ofrece una descripción general de la solución API Aspose.TeX para Python y su funcionalidad para representar fragmentos de LaTeX (figuras).
keywords: figura de LaTeX, tamaño de figura de LaTeX, imagen de LaTeX, imagen de LaTeX, figura incluida de LaTeX, imagen de LaTeX, opciones de figura de LaTeX
lastmod: "2026-04-03"
---

{{<section overview>}}

En determinadas situaciones, es posible que necesites extraer contenido específico de un archivo LaTeX como una pieza renderizada independiente, comúnmente denominada *figura*, sin ninguna conexión con el diseño de la página. Esto podría resultar útil, por ejemplo, al crear ilustraciones para una publicación en línea. Nuestra API le permite lograr esto. Los formatos de destino para representar figuras son PNG y SVG, al igual que con la función de representación de fórmulas matemáticas de LaTeX. Vale la pena señalar que la **representación de figuras LaTeX** es una característica más general en comparación con la [representación de fórmulas matemáticas LaTeX](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/).

## Renderizar una figura de LaTeX a PNG

Si es necesario, primero eche un vistazo a la [sección de referencia de API para este tema](https://reference.aspose.com/tex/python-net/aspose.tex.features/). De manera similar a la representación de fórmulas, comenzaremos con un ejemplo. Aquí lo tienes:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

Para comenzar, creamos una instancia de la clase [opciones de renderizado de figuras LaTeX](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/), donde especificamos simultáneamente la resolución de la imagen de salida.

A continuación, debemos especificar el preámbulo. A diferencia de la representación de fórmulas matemáticas de LaTeX, no existe un preámbulo predeterminado para la representación de figuras de LaTeX. Por lo tanto, si planea renderizar gráficos creados usando el paquete LaTeX `pict2e`, por ejemplo, necesitará especificarlo en el preámbulo:

```tex
\usepackage{pict2e}
```

Luego le indicamos al renderizador que escale la salida en un 300%.

La siguiente opción determina el color de fondo. A diferencia de la representación de fórmulas matemáticas, no necesitamos especificar un color de primer plano, ya que asumimos que los colores están completamente controlados por el código LaTeX. De manera similar, el color de fondo también está controlado por el código LaTeX, por lo que esta opción se proporciona simplemente por conveniencia.

Es posible que la siguiente línea del ejemplo no sea particularmente significativa. Simplemente pretende demostrar que tiene la opción de dirigir la salida del registro a una secuencia específica.

La última opción, `ShowTerminal`, le permite controlar si la salida del terminal debe mostrarse en la consola.

El método responsable de renderizar la figura es [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions) . Devuelve el tamaño de la figura en puntos.

El método acepta una secuencia como segundo argumento, que es la secuencia donde se escribirá la imagen. Creamos la secuencia en la siguiente línea.

Finalmente, invocamos el método `FigureRenderer.render()`, pasando las opciones como tercer argumento. El código LaTeX de la figura se proporciona como primer argumento.

Las últimas líneas del ejemplo muestran dos datos relacionados con la representación de la figura: el tamaño de la figura y un breve informe de errores (si hay algún error).

Aquí está el resultado del renderizado.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![Representación de figuras LaTeX a PNG](/tex/images/python-net/text-and-formula.png)</a>

Este representa el caso de uso más general para la función **Representación de figuras LaTeX**.

## Representar una figura de LaTeX a SVG

De manera similar, también podemos renderizar una figura LaTeX en formato SVG.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

Las diferencias son:

* En lugar de utilizar la clase [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/), utilizamos la clase [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/).
* No es necesario especificar la resolución.
* En lugar de utilizar la clase [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/), utilizamos la clase [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/).

 
Aquí está el resultado:
<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![Representación de figuras LaTeX a SVG](/tex/images/python-net/text-and-formula.svg)</a>