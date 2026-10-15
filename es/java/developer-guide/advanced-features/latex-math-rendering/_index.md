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

Establezca `outputFile` en un `java.nio.file.Path` dentro de una carpeta existente, por ejemplo `Paths.get(outputDirectory, "math-formula.png")` para PNG o `Paths.get(outputDirectory, "math-formula.svg")` para SVG. Importe las clases de renderizador, opciones y `Size2D` de Aspose.TeX utilizadas, además de `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. El método que realiza la llamada debe capturar o declarar las excepciones. Aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/) para evitar las restricciones de evaluación.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

Vayamos a los detalles. En primer lugar, creamos una instancia de [opciones de renderizado](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/), similar a la composición tipográfica TeX/LaTeX. Lo hacemos aquí especificando simultáneamente la resolución de la imagen de salida.

A continuación, especificamos el preámbulo. El preámbulo predeterminado es:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que proporciona un soporte de fórmulas matemáticas ligeramente más avanzado que el LaTeX básico. Puede, por ejemplo, agregar el paquete `color` si desea utilizar su propio resaltado en la fórmula, como mostramos en el ejemplo de código.

Luego le indicamos al renderizador que escale la salida en un 300%.

Las dos opciones definen los colores de primer plano y fondo. Las partes de la fórmula sin resaltado personalizado utilizan el color establecido por `setTextColor()`.

El ejemplo dirige los registros de renderización a un `ByteArrayOutputStream` mediante `setLogStream()`. Los flujos del registro y de la imagen se cierran automáticamente después de renderizar.

`showTerminal()` controla la salida del terminal en la consola. Los ejemplos utilizan `false`; establezca `true` para mostrarla.

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) se llama en una instancia de `PngMathRenderer` o `SvgMathRenderer` y devuelve las dimensiones de la fórmula en puntos como un `Size2D`.

El método acepta el flujo de salida de la imagen como segundo argumento. El ejemplo lo abre en un bloque try-with-resources, que lo cierra después de renderizar.

Finalmente, llamamos a `render()` en la instancia del renderizador: la fórmula LaTeX es el primer argumento, el flujo de la imagen el segundo y las opciones de renderización el tercero.

Las últimas líneas del ejemplo imprimen dos artefactos de la representación de fórmulas matemáticas: el tamaño de la fórmula y el breve informe de errores (en caso de que haya errores).

Aquí está el resultado del renderizado.

<a href="/tex/images/java/math-formula.png">![Representación de figuras LaTeX a PNG](/tex/images/java/math-formula.png)</a>

Este es el caso de uso más general para la representación de **fórmulas matemáticas LaTeX**.

**También puede consultar la [aplicación web](https://products.aspose.app/tex/equation-editor/png) gratuita creada en función de la función implementada dentro de la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/java/) es la página de la versión de Java.**

## Cómo renderizar una fórmula matemática LaTeX a SVG

De la misma manera, podemos representar una fórmula matemática de LaTeX en formato SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

Las diferencias son:

* Usamos la clase [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) en lugar de [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/).
* No especificamos resolución.
* Usamos la clase [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) en lugar de [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/).

Aquí está el resultado:

<a href="/tex/images/java/math-formula.svg">![Representación de fórmula matemática LaTeX a SVG](/tex/images/java/math-formula.svg)</a>

**También puede consultar la [aplicación web](https://products.aspose.app/tex/equation-editor/svg) gratuita creada en función de la función implementada en [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**