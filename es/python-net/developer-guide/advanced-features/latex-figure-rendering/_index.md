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

Establezca `ASPOSE_TEX_OUTPUT_DIR` en su directorio de salida o use la carpeta predeterminada `output`. Todo el código LaTeX está incluido en los ejemplos; no se necesitan archivos de entrada externos. Aplique primero una licencia. [Licencias](/tex/es/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

Para comenzar, creamos una instancia de la clase [opciones de renderizado de figuras LaTeX](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/), donde especificamos simultáneamente la resolución de la imagen de salida.

A continuación, debemos especificar el preámbulo. A diferencia de la representación de fórmulas matemáticas de LaTeX, no existe un preámbulo predeterminado para la representación de figuras de LaTeX. Por lo tanto, si planea renderizar gráficos creados usando el paquete LaTeX `pict2e`, por ejemplo, necesitará especificarlo en el preámbulo:

```tex
\usepackage{pict2e}
```

Se usa `scale = 3000` para una escala del 300 % y `margin = 5` para dejar espacio alrededor del fragmento. El ejemplo PNG utiliza `resolution = 150` DPI.

La siguiente opción determina el color de fondo. A diferencia de la representación de fórmulas matemáticas, no necesitamos especificar un color de primer plano, ya que asumimos que los colores están completamente controlados por el código LaTeX. De manera similar, el color de fondo también está controlado por el código LaTeX, por lo que esta opción se proporciona simplemente por conveniencia.

El ejemplo asigna un flujo de archivo binario a `log_stream` y guarda el registro como `text-and-formula.png.log` junto a `text-and-formula.png`. La instrucción `with` cierra ambos flujos automáticamente.

`show_terminal` controla la salida del terminal en la consola. Los ejemplos lo establecen en `False`; el registro sigue escribiéndose en el archivo.

El método responsable de renderizar la figura es [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions) . Devuelve el tamaño de la figura en puntos.

El segundo argumento es el flujo de salida binario abierto para la imagen. El tercero proporciona las opciones de renderizado.

Finalmente, invocamos el método `FigureRenderer.render()`, pasando las opciones como tercer argumento. El código LaTeX de la figura se proporciona como primer argumento.

Las últimas líneas muestran el informe de errores, o `No rendering errors.` si está vacío, seguido del ancho y la altura en puntos.

Aquí está el resultado del renderizado.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![Representación de figuras LaTeX a PNG](/tex/images/python-net/text-and-formula.png)</a>

Este representa el caso de uso más general para la función **Representación de figuras LaTeX**.

## Representar una figura de LaTeX a SVG

De manera similar, también podemos renderizar una figura LaTeX en formato SVG.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

Este ejemplo crea `text-and-formula.svg` y su registro `text-and-formula.svg.log` en el mismo directorio de salida.

Las diferencias son:

* En lugar de utilizar la clase [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/), utilizamos la clase [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/).
* No es necesario especificar la resolución.
* En lugar de utilizar la clase [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/), utilizamos la clase [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/).

 
Aquí está el resultado:
<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![Representación de figuras LaTeX a SVG](/tex/images/python-net/text-and-formula.svg)</a>