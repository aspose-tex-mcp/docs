---
translation: true
template: /templates/_template-java.md
linktitle: Ecuaciones mostradas
title: 9. Ecuaciones mostradas
weight: 90
url: /java/latex-math-displayed-equations/
keywords: LaTeX, fórmulas matemáticas de LaTeX, matemáticas de LaTeX, fórmula mostrada de matemáticas de LaTeX, ecuación mostrada de matemáticas de LaTeX, matriz de ecuaciones matemáticas de LaTeX, alineación mostrada de matemáticas de LaTeX
description: Conozca la forma de mostrar fórmulas matemáticas de gran tamaño o una gran cantidad de fórmulas utilizando comandos proporcionados por LaTeX.
lastmod: "2026-04-21"
---

{{<section overview>}}

Hasta ahora hemos discutido cómo abordar las fórmulas individuales; pero las exhibiciones a menudo involucran un montón de fórmulas diferentes, o diferentes partes de una fórmula enorme, y puede ser un desafío diseñarlas para que se alineen adecuadamente entre sí. Afortunadamente, las pantallas grandes generalmente siguen algunos patrones simples.

### 9.1. Pantallas de una línea

Las ecuaciones mostradas suelen contener texto normal. Ya hemos [discutido](/tex/{{lang.url-fragment}}java/latex-math-fine-points/#82-non-italic-letters) cómo introducir texto romano en fórmulas sin salir del modo matemático, pero la mejor manera de mostrar texto en una pantalla es ponerlo en un `\hbox`. En realidad, ni siquiera es necesario que haya ninguna matemática. Para escribir conjunto

![Texto mostrado sin ningún cálculo matemático](/tex/images/java/tutorial/latex-math-9-1.png)

puedes decir `$$\hbox{Texto mostrado}$$`. Pero aquí hay un ejemplo más interesante:

![Texto en una pantalla matemática](/tex/images/java/tutorial/latex-math-9-2.png)

En este caso, las fórmulas y el texto se combinaron de la siguiente manera:

```tex
$$\X_n=X_k \qquad\hbox{if and only if}\qquad
     Y_n=Y_k \quad\hbox{and}\quad Z_n=Z_k.$$
```

Como puede ver, `\qquad` aparece alrededor de "si y sólo si", pero un único `\quad` rodea "y"; esto pone énfasis en el hecho de que las partes *Y* y *Z* de la pantalla están más estrechamente relacionadas entre sí que con la parte *X*. 

Veamos la siguiente pantalla:

![Texto en una pantalla matemática](/tex/images/java/tutorial/latex-math-9-3.png)

Una forma de especificarlo es

```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all }n\ge0.$$
```

Pero la mejor manera sería (ver la segunda línea)

```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all $n\ge0$.}$$
```

Sí, ese es el modo matemático dentro del modo horizontal dentro del modo matemático de visualización, pero esta solución parece más natural que la primera.

Ahora pasemos a los números de ecuación, esas pequeñas etiquetas que aparecen a los lados de las pantallas. si escribes

```tex
$$<formula>\eqno<formula>$$
```

TeX mostrará la primera fórmula y también pondrá un número de ecuación (la segunda fórmula) en el margen derecho. Por ejemplo,

```tex
$$x^2-y^2 = (x+y)(x-y).\eqno(15)$$
```

producirá

![Números de ecuación a la derecha](/tex/images/java/tutorial/latex-math-9-4.png)

También puedes obtener los números de ecuación en el margen izquierdo usando `\leqno`. Por ejemplo,

```tex
$$x^2-y^2 = (x+y)(x-y).\leqno(15)$$
```

producirá

![Números de ecuación a la izquierda](/tex/images/java/tutorial/latex-math-9-5.png)

Observe que siempre coloca el número de la ecuación en segundo lugar, incluso cuando aparecerá a la izquierda.

Las ecuaciones mostradas están centradas independientemente de la presencia de los números de ecuación. Pero cuando una fórmula es grande, TeX se asegura de que no interfiera con su número; el número de la ecuación puede incluso colocarse solo en una línea.

LaTeX también proporciona el entorno de ecuaciones para numerar automáticamente sus ecuaciones. Por ejemplo, escribiendo

```tex
\begin{equation}
  f(x)=(x+a)(x+b)
\end{equation}
```

resultados en

![El uso del entorno de ecuaciones](/tex/images/java/tutorial/latex-math-9-6.png)

También es posible etiquetar y hacer referencia a ecuaciones usando `\label` y `\ref`. Por ejemplo,

```tex
\begin{equation} \label{eq:someequation}
  f(x)=(x+a)(x+b)
\end{equation}
esto hace referencia a la ecuación \ref{eq:someequation}.
```

resultados en

![El uso del entorno de ecuación con una etiqueta y una referencia](/tex/images/java/tutorial/latex-math-9-7.png)

### 9.2. Pantallas multilínea

A veces, es posible que una pantalla no se ajuste al patrón simple de una fórmula de una línea con o sin un número de ecuación. LaTeX proporciona comandos especiales para la mayoría de los casos restantes.

Las pantallas de líneas múltiples generalmente incluyen varias ecuaciones que deben estar alineadas por sus signos '=", como en

![Una ecuación de varias líneas compuesta con el entorno de matriz](/tex/images/java/tutorial/latex-math-9-8.png)

El método recomendado para dicha visualización es utilizar el entorno `array` proporcionado por LaTeX:

```tex
$$\begin{array}{rl}
  X_1+\cdots+\X_p&=m,\\
  Y_1+\cdots+\Y_q&=n.}
\end{array}$$
```

Este entorno le ayuda a representar sus ecuaciones como una matriz rectangular de varias columnas (dos columnas en este caso). Las filas contienen ecuaciones individuales separadas por el comando `\\` (que es una nueva línea). Los lados izquierdo y derecho de cada ecuación están separados por el símbolo "&". No es necesario que la última línea termine en `\\`. El entorno también tiene un argumento que especifica la alineación en cada columna. En el ejemplo, el valor apropiado es "rl", lo que significa que los lados izquierdos de las ecuaciones quedarán alineados a la derecha, mientras que los lados derechos quedarán alineados a la izquierda.

LaTeX también proporciona el entorno `eqnarray*` que funciona de manera similar, pero para tener ambos lados de las ecuaciones correctamente alineados se necesitan dos puntos de alineación y, desafortunadamente, el espaciado se sale un poco de las convenciones de escritura matemática. El siguiente código

```tex
\begin{eqnarray*}
  X_1+\cdots+X_p&=&m,\\
  Y_1+\cdots+Y_q&=&n.
\end{eqnarray*}
```

produce el siguiente resultado:

![Una ecuación de varias líneas compuesta con el entorno eqnarray*](/tex/images/java/tutorial/latex-math-9-9.png)

El entorno `eqnarray` de LaTeX produce el mismo resultado excepto que numera automáticamente las ecuaciones.

Puede haber cualquier número de ecuaciones en un entorno de "matriz"; el patrón general es

```tex
\begin{array}{rl}
  <left-hand side_1>&<right-hand side_1>\\
  <left-hand side_2>&<right-hand side_2>\\
  ...
  <left-hand side_n>&<right-hand side_n>
\end{array}
```

donde cada `<lado derecho>` comienza con el símbolo en el que desea que se produzca la alineación.

El resultado del entorno "matriz" es un cuadro centrado verticalmente. Esto hace que sea fácil obtener una fórmula como

![Dos grupos de ecuaciones en una pantalla](/tex/images/java/tutorial/latex-math-9-10.png)

Simplemente usa el entorno `array` dos veces en la línea:

```tex
$$\left\{
  \begin{array}{rl}
    \alpha&=f(z)\\ \beta&=f(z^2)\\ \gamma&=f(z^3)
  \end{array}
\right\}\qquad\left\{
  \begin{array}{rl}
    x&=\alpha^2-\beta\\ y&=2\gamma
  \end{array}
\right\}.$$
```

El siguiente nivel de complejidad ocurre cuando tienes varias ecuaciones alineadas con varios números de ecuación. O algunas de las líneas pueden estar numeradas y otras no:

![Matriz de ecuaciones numeradas arbitrariamente con etiquetas a la derecha](/tex/images/java/tutorial/latex-math-9-11.png)

Desafortunadamente, incluso con el entorno `eqnarray*` (con su espaciado inadecuado) no hay forma de especificar manualmente los números de ecuación en una pantalla de varias líneas. Sólo el paquete `amsmath` puede 
ayuda. Entonces, la forma recomendada de obtener el resultado anterior es escribir:

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```

Si omite tanto `\tag` como `\notag` en una línea del entorno `align`, el número de ecuación se generará automáticamente utilizando el valor actual almacenado en el contador interno correspondiente.

Si carga el paquete `amsmath` con la opción `leqno`, los números de las ecuaciones aparecerán en el margen izquierdo. De este modo

```tex
%% Preamble
\usepackage[leqno]{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```
produce

![Matriz de ecuaciones numeradas arbitrariamente con etiquetas a la izquierda](/tex/images/java/tutorial/latex-math-9-12.png)

Para obtener más información sobre la composición tipográfica de fórmulas matemáticas utilizando las funciones del paquete `amsmath`, consulte estos [artículos](/tex/{{lang.url-fragment}}java/what-is-ams-latex/).

### 9.3. Fórmulas largas

Ahora analicemos qué se debe hacer cuando una fórmula es tan larga que no cabe en una sola línea. Por ejemplo, supongamos que encuentras la ecuación

![Fórmula larga reducida que hace que la línea esté demasiado llena](/tex/images/java/tutorial/latex-math-9-13.png)

Tendrás que dividirlo de alguna manera; TeX ha hecho todo lo posible para comprimir todo reduciendo los espacios junto a los signos '+' y '-' a cero, pero aun así la línea ha salido demasiado llena.

Intentemos romper esa ecuación justo antes del '+7'. El entorno `array` deja demasiado espacio a la derecha del '=" si lo usas de la misma manera que para las ecuaciones multilínea:

```tex
$$\begin{array}{rl}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1)
\end{array}$$
```

Por lo tanto, es mejor recurrir nuevamente al paquete `amsmath`. Pero esta vez deberías usar la matriz `align*` ya que los números de la ecuación no son necesarios:

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).
\end{align*}$$
```

Esto produce

![Fórmula larga dividida usando el entorno align*](/tex/images/java/tutorial/latex-math-9-14.png)

La idea es tratar una fórmula larga de una línea como una fórmula de dos líneas, usando `\qquad` en la segunda línea para que la segunda parte de la fórmula aparezca bien a la derecha del signo '=" en la primera línea. .
En realidad, no es una tarea fácil decidir cómo dividir en líneas las fórmulas que se muestran durante mucho tiempo; TeX nunca intenta hacer esto, porque ningún conjunto de reglas es realmente adecuado. El autor de un manuscrito matemático es generalmente el mejor juez sobre qué hacer, ya que las posiciones de ruptura dependen de factores sutiles de las exposiciones matemáticas. Por ejemplo, a menudo es deseable enfatizar algo de la simetría u otra estructura que subyace a la fórmula, y tales cosas requieren una comprensión sólida de lo que sucede exactamente en esa fórmula.

Sin embargo, es posible establecer algunas reglas generales sobre cómo manejar fórmulas largas en pantallas, ya que existen algunos principios que el mejor tipógrafo matemático tiende a seguir:

1. Aunque las fórmulas dentro de un párrafo siempre se rompen *después* de las operaciones y relaciones binarias, las fórmulas mostradas siempre se rompen *antes* de las operaciones y relaciones binarias. Es por eso que no terminamos la primera línea de nuestro ejemplo anterior con `(2^{34}-1)+`; lo terminamos con `(2^{34}-1` y comenzamos la segunda línea con `+`.

2. Cuando una ecuación se divide antes de una operación binaria, la segunda línea debe comenzar al menos dos cuadretes a la derecha de donde comienza la subfórmula más interna que contiene esa operación binaria en la primera línea. Por ejemplo, si desea romper

```tex
$$\sum_{0<k<n}\left(<formula_1>+<formula_2>\right)$$
```

en el signo más entre `<fórmula_1>` y `<fórmula_2>`, es casi obligatorio que el signo más en la segunda línea aparezca algo a la derecha del paréntesis izquierdo grande que corresponde a `\left(`.

En el ejemplo que acabamos de considerar, se necesita especial cuidado al dividir la fórmula en dos líneas, porque los delimitadores `\left` y `\right` no se pueden usar de forma aislada: no se puede tener solo `\left` en una línea de un fórmula y solo `\right` en el segundo. Además, querrá que los dos delimitadores sean del mismo tamaño, aunque aparezcan en líneas diferentes. La mejor solución suele ser elegir usted mismo el tamaño del delimitador; por ejemplo, podrías escribir

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sum_{0<k<n}\biggl(&<formula_1>\\
    &\qquad+<formula_2>\biggr)
\end{align*}
```

si los delimitadores `\ bigg` son los mejores. Observe que los marcadores `&` no aparecen en los signos `=` en este ejemplo, solo marcan un punto de alineación.

Hay otra forma de dividir fórmulas largas, a veces llamada forma de *dos líneas*. La idea es poner la primera parte de la fórmula casi al ras a la izquierda y la segunda parte casi al ras a la derecha, donde "casi al ras" significa "a un cuadrante de distancia". Por lo tanto, la forma de dos líneas de una ecuación sigma larga considerada anteriormente es

![Forma de dos líneas de una ecuación](/tex/images/java/tutorial/latex-math-9-15.png)

Para obtener este efecto de dos líneas, simplemente escriba:

```tex
$$\displaylines{\quad\sigma(2^{34}-1,2^{35},1)
  =-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1)\hfill{}\cr
\hfill{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).\quad\cr}$$
```

Se escribió un `{}` adicional en la segunda línea aquí para que TeX supiera que `+` es una operación binaria. La forma de dos líneas se recomienda especialmente para ecuaciones que tienen un lado izquierdo largo; en ese caso, la pausa suele aparecer justo antes del signo =.