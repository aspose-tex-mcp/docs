---
translation: true
template: /templates/_template-java.md
linktitle: Comandos LaTeX
title: 3. Comandos LaTeX
weight: 30
url: /java/latex-math-commands/
keywords: LaTeX, fórmulas matemáticas de LaTeX, matemáticas de LaTeX, comandos matemáticos de LaTeX, raíz cuadrada de LaTeX, subrayado matemático de LaTeX, sobrerayado matemático de LaTeX
description: Este artículo analiza otra forma de componer fórmulas matemáticas que involucra comandos macro proporcionados por LaTeX.
lastmod: "2024-10-30"
---

{{<section overview>}}

Otra forma de crear fórmulas complejas a partir de fórmulas simples es utilizar los comandos `\sqrt`, `\underline` o `\overline`. También se aplican al carácter o subfórmula que les sigue:

![Aplicación más sencilla de comandos LaTeX](/tex/images/java/tutorial/latex-math-3-1.png)

También puedes obtener raíces cúbicas y cosas similares:

![Raíces de grado arbitrario](/tex/images/java/tutorial/latex-math-3-2.png)

Estos tres comandos colocan líneas encima y debajo de subfórmulas de cualquier tamaño y forma; las líneas de barra cambian su tamaño y posición, de modo que sean lo suficientemente largas para cubrir la subfórmula y lo suficientemente altas o bajas para no superponerse con ella. En particular, los signos de raíz cuadrada aparecen en una variedad de posiciones dependiendo de la altura y profundidad de lo que se está escribiendo `\sqrt`': ![Raíces de grado arbitrario](/tex/images/java/tutorial/latex-math-3-3.png) En tal caso, es posible que desee componer todos los signos cuadrados raíces uniformemente, así: ![Raíces de grado arbitrario](/tex/images/java/tutorial/latex-math-3-4.png) La manera fácil de hacer esto es usar el comando `\mathstrut`:

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

Un `\mathstrut` es un cuadro invisible de ancho cero. Su altura y profundidad son la altura y profundidad de un paréntesis '('. De ello se deduce que las subfórmulas que contienen `\mathstrut` siempre tendrán la misma altura y profundidad, a menos que impliquen construcciones más complicadas como subíndices y superíndices.