---
translation: true
template: /templates/_template-java.md
linktitle: Subíndice y subíndice en LaTeX
title: 2. Subíndice y subíndice en LaTeX
weight: 20
url: /java/latex-math-subscripts-superscripts/
keywords: LaTeX, fórmulas matemáticas de LaTeX, matemáticas de LaTeX, subíndices matemáticos de LaTeX, superíndices matemáticos de LaTeX
description: Este artículo analiza cómo crear fórmulas matemáticas que contengan subíndices y superíndices con TeX y LaTeX.
lastmod: "2024-10-30"
---

{{<section overview>}}


## Introducción al superíndice y subíndice de LaTeX

**Superíndice** es un pequeño carácter o símbolo colocado ligeramente por encima de la línea base del texto.  Por ejemplo, en la expresión `x²`, el `2` es un superíndice.

**Subíndice** es un pequeño carácter o símbolo colocado ligeramente debajo de la línea base del texto. Por ejemplo, en la fórmula química del agua, "H₂O", el "2" es un subíndice.

## Cómo escribir subíndice/superíndice en LaTeX

Ahora intentemos construir fórmulas más complejas a partir de fórmulas simples. Primero, puede obtener superíndices y subíndices usando `^` y `_`, como se muestra en el siguiente ejemplo:

![Subíndices y superíndices de un solo carácter](/tex/images/java/tutorial/latex-math-2-1.png)

Tenga en cuenta que `^` y `_` se aplican solo al siguiente carácter. Si desea un subíndice o superíndice más complejo, simplemente enciérrelo entre llaves:

![Subíndices y superíndices de varios caracteres](/tex/images/java/tutorial/latex-math-2-2.png)

Las llaves en estos ejemplos especifican "subfórmulas": partes más simples de una fórmula más grande. TeX crea un cuadro para cada subfórmula y lo trata como si fuera un símbolo único. Los tirantes también cumplen su propósito habitual de agrupar.

Es ilegal escribir `$x^y^z$` o `$x_y_z$`. TeX se quejará de un "doble subíndice" o "doble superíndice". Debes dejar más claro lo que quieres escribiendo `$x^{y^z}$`, o `$x^{yz}$`, o `$x_{y_z}$`, o `$x_{yz} $`.

Un superíndice o subíndice que sigue a un carácter se aplica únicamente a ese carácter; pero cuando se sigue una subfórmula, se aplica a toda esa subfórmula y se aumentará o disminuirá en consecuencia.

![Subíndices y superíndices en un solo símbolo y en una subfórmula](/tex/images/java/tutorial/latex-math-2-3.png)

En la primera fórmula, `^3` y `^4` son superíndices en los paréntesis derechos que los preceden inmediatamente, pero en la segunda fórmula son superíndices en las subfórmulas que están entre llaves. Es preferible la primera versión porque es más fácil de escribir y de leer.

## Escribir subíndice o superíndice en una subfórmula vacía

A veces es posible que necesites crear un subíndice o superíndice en una subfórmula vacía para producir alguna notación bastante rara como *<sub>2</sub>F<sub>3</sub>*. La mejor manera de hacerlo es escribir `${}_2F_3$` o `${_2}F_3$` o `${_2F_3}$`.

También puede tener "subsuperíndices" simultáneos y especificarlos en cualquier orden:

![Subsuperíndices simultáneos](/tex/images/java/tutorial/latex-math-2-4.png)

Estos "subsuperíndices" simultáneos están colocados uno encima del otro. Sin embargo, para algunas letras, un subíndice se desplazará hacia la izquierda; y para algunas de esas cartas de manera bastante notable. Compare las siguientes dos fórmulas:

![Alineación simultánea de subsuperíndices](/tex/images/java/tutorial/latex-math-2-5.png)

Entonces, si desea que tanto el subíndice como el superíndice estén alineados, puede usar el truco que se muestra en la segunda versión. Nuevamente aprovecha una subfórmula vacía.

## Escribir prime en LaTeX

Lo siguiente que ocurre con frecuencia en las fórmulas matemáticas es el símbolo primo. LaTeX proporciona el comando `\prime`, que a su vez produce un símbolo primo del tamaño de una letra normal. Por lo tanto, nunca querrás usarlo excepto en un superíndice o subíndice. Pero puedes simplemente escribir `'` en lugar de `^\prime`, y `''` en lugar de `^\prime\prime`, y así sucesivamente.

![Primos](/tex/images/java/tutorial/latex-math-2-6.png)

## Doble superíndice LaTeX

En LaTeX, puede escribir superíndices dobles encerrando la expresión de superíndice completa entre llaves {}. Aquí hay un ejemplo: `x^{a^b}`

## Doble subíndice LaTeX
En LaTeX, puede escribir subíndices dobles de manera similar encerrando la expresión completa del subíndice entre llaves {}. Aquí hay un ejemplo: `X_ {i_ {j}}`