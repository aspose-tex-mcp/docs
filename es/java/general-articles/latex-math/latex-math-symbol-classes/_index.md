---
translation: true
template: /templates/_template-java.md
linktitle: Diferentes caracteres en fórmulas matemáticas.
title: 4. Diferentes caracteres en fórmulas matemáticas.
weight: 40
url: /java/latex-math-symbol-classes/
keywords: LaTeX, fórmulas matemáticas de LaTeX, matemáticas de LaTeX, símbolos matemáticos de LaTeX, variables matemáticas de LaTeX, operaciones binarias matemáticas de LaTeX, relaciones matemáticas de LaTeX, acentos matemáticos de LaTeX
description: Este artículo analiza la división de los símbolos matemáticos TeX en clases y el significado de estas clases en matemáticas.
lastmod: "2024-10-30"
---

{{<section overview>}}

Las 52 letras (`A` a `Z` y `a` a `z`) denotan símbolos en cursiva, que un matemático llamaría "variables". TeX los llama simplemente "símbolos ordinarios", porque constituyen la mayor parte de las fórmulas matemáticas. LaTeX también trata los siguientes 18 caracteres.

``0 1 2 3 4 5 6 7 8 9 ! ? . | `@ "``

como símbolos ordinarios, lo que significa que no inserta ningún espacio adicional cuando estos símbolos aparecen uno al lado del otro o al lado de letras. A diferencia de las letras, estos 18 caracteres permanecen en tipo romano en las fórmulas.

Los tres caracteres `+`, `-` y `*` se denominan "operaciones binarias" porque operan en dos partes de la fórmula. El asterisco (*) es poco común, pero también se comporta como una operación binaria. A continuación se muestran algunos ejemplos de composición tipográfica de operaciones binarias cuando aparecen junto a símbolos ordinarios:

![Operaciones binarias](/tex/images/java/tutorial/latex-math-4-1.png)

TeX no trata `/` como una operación binaria porque daría lugar a un espaciado incorrecto en fórmulas como `$1/2$`. Por lo tanto, TeX trata `/` como un símbolo ordinario.

Aquí hay algunos ejemplos más de operaciones binarias:

![Operaciones binarias más complejas](/tex/images/java/tutorial/latex-math-4-2.png)

Por cierto, las operaciones binarias se tratan como símbolos ordinarios si no ocurren entre dos cantidades sobre las que puedan operar. Por lo tanto, no se inserta ningún espacio adicional junto a +, - y * en casos como los siguientes:

![Operación binaria como símbolos ordinarios](/tex/images/java/tutorial/latex-math-4-3.png)

Los siguientes ejemplos muestran que las operaciones binarias se pueden utilizar como símbolos ordinarios en superíndices y subíndices:

![Operación binaria como símbolos ordinarios en superíndices y subíndices](/tex/images/java/tutorial/latex-math-4-4.png)

LaTeX trata los cuatro caracteres `=`, `<`, `>` y `:` como "relaciones" porque expresan una relación entre dos cantidades. Estas relaciones tienen un significado bastante diferente al de las operaciones binarias, y los símbolos están escritos de forma algo distinta:

![Relaciones](/tex/images/java/tutorial/latex-math-4-5.png)

Los dos caracteres ',' (coma) y ';' (punto y coma) se tratan como signos de puntuación en las fórmulas, lo que significa que TeX pone un poco de espacio adicional después de ellos, pero no antes.

![Signos de puntuación](/tex/images/java/tutorial/latex-math-4-6.png)

No es habitual poner espacio extra después de un '.' (punto) en fórmulas, por lo que TeX trata un punto como un símbolo ordinario. Si desea que el carácter ':' sea un signo de puntuación en lugar de una relación, simplemente llámelo `\dos puntos`. Y si desea que una coma se trate como un símbolo normal, simplemente colóquela entre llaves. TeX trata todo lo que esté entre llaves como un símbolo ordinario.

![Dos puntos como puntuación y coma como símbolo ordinario](/tex/images/java/tutorial/latex-math-4-7.png)

Los caracteres `(` y `[` se denominan "aperturas", mientras que `)` y `]` se denominan "cierres". Actúan de forma muy parecida a los símbolos ordinarios, pero ayudan a TeX a decidir cuándo una operación binaria no se está utilizando realmente de forma binaria.

Finalmente, LaTeX reserva los otros 10 caracteres:

`\ $ % # & ~ { } _ ^`

No puedes usarlos en modo matemático. Aunque '{' y '}' especifican agrupación, los comandos `\{` y `\}` se pueden usar para obtener '{' como apertura y '}' como cierre.

Los caracteres especiales `^` y `_` no deben usarse excepto en fórmulas. Por el contrario, los nombres de símbolos matemáticos como `\alpha` y `\approx`, y los comandos para operaciones matemáticas como `\overline`, no deben aparecer dentro del texto normal. Además, no se permite una línea en blanco o `\par` en el modo matemático.

A los matemáticos también les gusta usar acentos sobre las letras como una forma eficaz de indicar relaciones entre objetos matemáticos. También amplía enormemente la cantidad de símbolos disponibles sin aumentar la cantidad de fuentes necesarias. Los acentos matemáticos son algo diferentes de los acentos utilizados en el texto normal. El espaciado no es lo mismo; TeX sigue reglas especiales para los acentos en las fórmulas, de modo que los dos tipos de acentos no se confundan entre sí. LaTeX proporciona los siguientes acentos matemáticos:

![Acentos](/tex/images/java/tutorial/latex-math-4-8.png)

Los primeros nueve de ellos se denominan `\^`, `\v`, `\~`, `\'`, ``\` ``, `\.`, `\"`, `\u` y `\=`, respectivamente, cuando aparecen en el texto; `\vec` es un acento que aparece solo en fórmulas. TeX emitirá un mensaje de error si intenta utilizar `\^` o `\v`, etc. en fórmulas, o si intenta utilizar `\hat` o `\check`, etc., en texto normal.

Generalmente es mejor definir macros para letras acentuadas que necesita con frecuencia. puedes poner

```tex
\def\Ahat{{\hat A}}
\def\chat{{\hat c}}
\def\scheck{{\check s}}
```

al principio de un archivo LaTeX. Esto le ahorra muchas pulsaciones de teclas y hace que el archivo sea más fácil de leer.

Cuando las letras *i* y *j* están acentuadas en fórmulas matemáticas, debes usar bases de símbolos sin puntos que se denominan `\imath` y `\jmath`. Entonces, un artículo que use hat'ed i y j podría comenzar con las siguientes definiciones:

```tex
\def\ihat{{\hat\imath}}
\def\jhat{{\hat\jmath}}
```

Es posible poner acentos matemáticos en cualquier subfórmula. Pero normalmente no tiene mucho sentido hacerlo, porque TeX simplemente centra el acento en toda la subfórmula. En particular, un acento `\bar` siempre permanece del mismo tamaño; no es como `\overline`, que crece con la fórmula debajo. Algunas personas prefieren la línea más larga de `\overline` incluso cuando se aplica a una sola letra. Sin embargo, LaTeX proporciona dos acentos que crecen; se llaman `\widehat` y `\widetilde`. Ahora veamos los ejemplos de casos discutidos en el presente párrafo.

![Acentos amplios](/tex/images/java/tutorial/latex-math-4-9.png)

El último ejemplo muestra el tamaño máximo disponible.