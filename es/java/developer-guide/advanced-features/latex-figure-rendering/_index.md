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

Establezca `outputFile` en un `java.nio.file.Path` dentro de una carpeta existente, por ejemplo `Paths.get(outputDirectory, "text-and-formula.png")` para PNG o `Paths.get(outputDirectory, "text-and-formula.svg")` para SVG. Importe las clases de renderizador, opciones y `Size2D` de Aspose.TeX utilizadas, además de `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. El método que realiza la llamada debe capturar o declarar las excepciones. Aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToPNG.java" >}}

En primer lugar, creamos una instancia de [opciones de renderizado](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/). Lo hacemos aquí junto con la especificación de la resolución de la imagen de salida.

A continuación, especificamos el preámbulo. No hay un preámbulo predeterminado para la representación de figuras en LaTeX, por lo que si desea, por ejemplo, representar algunos gráficos trazados usando el paquete LaTeX `pict2e`, debe especificarlo en el preámbulo:

```tex
\usepackage{pict2e}
```

Luego le indicamos al renderizador que escale la salida en un 300%. Los ejemplos también establecen un margen de 5 puntos con `setMargin(5)` alrededor de la figura. El ejemplo PNG utiliza 150 DPI.

La siguiente opción define el color de fondo. A diferencia de la representación de fórmulas matemáticas, no especificamos un color de primer plano ya que asumimos que los colores están completamente bajo el control del código LaTeX. De hecho, también lo es el color de fondo, por lo que esta es solo una opción conveniente.

El ejemplo dirige los registros de renderización a un `ByteArrayOutputStream` mediante `setLogStream()`. Los flujos del registro y de la imagen se cierran automáticamente después de renderizar.

`showTerminal()` controla la salida del terminal en la consola. Los ejemplos utilizan `false`; establezca `true` para mostrarla.

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) se llama en una instancia de `PngFigureRenderer` o `SvgFigureRenderer` y devuelve las dimensiones de la figura en puntos como un `Size2D`.

El método acepta el flujo de salida de la imagen como segundo argumento. El ejemplo lo abre en un bloque try-with-resources, que lo cierra después de renderizar.

Finalmente, llamamos a `render()` en la instancia del renderizador: la figura LaTeX es el primer argumento, el flujo de la imagen el segundo y las opciones de renderización el tercero.

Las últimas líneas del ejemplo imprimen dos artefactos de la representación de la figura: el tamaño de la figura y el breve informe de errores (en caso de que haya errores).

Aquí está el resultado del renderizado.

![Representación de figuras LaTeX a PNG](/tex/images/java/text-and-formula.png)

Este es el caso de uso más general para la función **Representación de figuras LaTeX**.

## Cómo renderizar una figura de LaTeX a SVG

De la misma manera, podemos renderizar una figura de LaTeX al formato SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToSVG.java" >}}

Las diferencias son:

 * Usamos la clase [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) en lugar de [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/).
 * No especificamos la resolución.
 * Usamos la clase [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) en lugar de [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/).


Aquí está el resultado:

<a href="/tex/images/java/text-and-formula.svg">![Representación de figuras LaTeX a SVG](/tex/images/java/text-and-formula.svg)</a>