---
translation: true
template: /templates/_template-java.md
title: Representación de fórmulas matemáticas LaTeX | Aspose.TeX para Java
linktitle: Representación de fórmulas matemáticas LaTeX
weight: 10
url: /java/latex-math-formula-rendering/
description: Este artículo describe la representación de fórmulas matemáticas LaTeX dentro de la API Aspose.TeX para Java, explicada con ejemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Cómo renderizar una fórmula matemática LaTeX a PNG

De hecho, la forma más sencilla de demostrar la función de representación de **fórmula matemática LaTeX** es comenzar con el ejemplo. Aquí lo tienes:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

Vayamos a los detalles. En primer lugar, creamos una instancia de [opciones de renderizado](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions), similar a la composición tipográfica TeX/LaTeX. Lo hacemos aquí especificando simultáneamente la resolución de la imagen de salida.

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

El método que realmente realiza la renderización es [MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-). Devuelve el tamaño de la fórmula en puntos.

El método acepta la secuencia donde se escribirá la imagen como segundo argumento. Creamos la secuencia a continuación.

Y finalmente, llamamos al método `MathRenderer.render()`, pasando opciones como tercer argumento. El código LaTeX de la fórmula se pasa como primer argumento.

Las últimas líneas del ejemplo imprimen dos artefactos de la representación de fórmulas matemáticas: el tamaño de la fórmula y el breve informe de errores (en caso de que haya errores).

Aquí está el resultado del renderizado.

<a href="/tex/images/java/math-formula.png">![Representación de figuras LaTeX a PNG](/tex/images/java/math-formula.png)</a>

Este es el caso de uso más general para la representación de **fórmulas matemáticas LaTeX**.

**También puede consultar la [aplicación web](https://products.aspose.app/tex/equation-editor/png) gratuita creada en función de la función implementada dentro de la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) es la página de la versión de Java.**

## Cómo renderizar una fórmula matemática LaTeX a SVG

De la misma manera, podemos representar una fórmula matemática de LaTeX en formato SVG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

Las diferencias son:

* Usamos la clase [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) en lugar de [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions).
* No especificamos resolución.
* Usamos la clase [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) en lugar de [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer).

Aquí está el resultado:

<a href="/tex/images/java/math-formula.svg">![Representación de fórmula matemática LaTeX a SVG](/tex/images/java/math-formula.svg)</a>

**También puede consultar la [aplicación web](https://products.aspose.app/tex/equation-editor/svg) gratuita creada en función de la función implementada en [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**