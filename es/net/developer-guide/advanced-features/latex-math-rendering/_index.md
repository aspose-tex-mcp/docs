---
translation: true
template: /templates/_template-net.md
title: Representación de fórmulas matemáticas LaTeX | .NET
linktitle: Representación de fórmulas matemáticas LaTeX
weight: 10
url: /net/latex-math-formula-rendering/
description: Este artículo describe con ejemplos de código cómo representar fórmulas matemáticas en LaTeX con Aspose.TeX para .NET.
lastmod: "2024-10-30"
---

{{<section overview>}}


## Cómo renderizar una fórmula matemática LaTeX a PNG

La sección de referencia de API relacionada con este tema está [aquí](https://reference.aspose.com/tex/net/aspose.tex.features/). De hecho, la forma más sencilla de demostrar la función **Representación de fórmulas matemáticas de LaTeX** es comenzar con el ejemplo. Aquí lo tienes:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-PngLaTeXMathRendering.cs" >}}

Vayamos a los detalles. En primer lugar, creamos una instancia de [opciones de renderizado](https://reference.aspose.com/tex/net/aspose.tex.features/mathrendereroptions/), similar a la composición tipográfica TeX/LaTeX. Lo hacemos aquí especificando simultáneamente la resolución de la imagen de salida.

A continuación, especificamos el preámbulo. El preámbulo predeterminado es:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que proporciona un soporte de fórmulas matemáticas ligeramente más avanzado que el LaTeX básico. Puede, por ejemplo, agregar el paquete `color` si desea utilizar su propio resaltado en la fórmula, como mostramos en el ejemplo de código.

Luego le indicamos al renderizador que escale la salida en un 300%.

Las siguientes dos opciones definen los colores de primer plano y de fondo. Aquellas partes de la fórmula que no estén cubiertas ("coloreadas") por el resaltado personalizado se mostrarán en el color "TextColor".

La siguiente línea del ejemplo no tiene mucho sentido. Simplemente demuestra que puede dirigir la salida del registro a alguna secuencia.

Y la última opción `ShowTerminal` le permite alternar la escritura de la salida del terminal en la consola.

El método que realmente realiza la renderización es [MathRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/mathrenderer/render/). Devuelve el tamaño de la fórmula en puntos.

El método acepta la secuencia donde se escribirá la imagen como segundo argumento. Creamos la secuencia a continuación.

Y finalmente, llamamos al método `MathRenderer.Render()`, pasando opciones como tercer argumento. El código LaTeX de la fórmula se pasa como primer argumento.

Las últimas líneas del ejemplo imprimen dos artefactos de la representación de fórmulas matemáticas: el tamaño de la fórmula y el breve informe de errores (en caso de que haya errores).

Aquí está el resultado del renderizado.

<a href="/tex/net/latex-math-formula-rendering/math-formula.png">![Representación de fórmula matemática LaTeX a PNG](/tex/images/net/math-formula.png)</a>

Este es el caso de uso más general para la función **Representación de fórmulas matemáticas LaTeX**.

**También puede consultar la [aplicación web](https://products.aspose.app/tex/equation-editor/png) gratuita creada en función de la función implementada en [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Cómo renderizar una fórmula matemática LaTeX a SVG

De la misma manera, podemos representar una fórmula matemática de LaTeX en formato SVG.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.cs" >}}

Las diferencias son:

* Usamos la clase [SvgMathRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrendereroptions/) en lugar de [PngMathRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrendereroptions/).
* No especificamos resolución.
* Usamos la clase [SvgMathRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrenderer/) en lugar de [PngMathRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrenderer/).
 
Aquí está el resultado:

<a href="/tex/net/latex-math-formula-rendering/math-formula.svg">![Representación de fórmula matemática LaTeX a SVG](/tex/images/net/math-formula.svg)</a>

**También puede consultar la [aplicación web](https://products.aspose.app/tex/equation-editor/svg) gratuita creada en función de la función implementada en [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**