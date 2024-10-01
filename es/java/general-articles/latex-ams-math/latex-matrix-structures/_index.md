---
translation: true
template: /templates/_template-java.md
linktitle: Matrix y entornos similares
title: 3. Matrix y entornos similares | manual de látex
weight: 30
url: /java/latex-ams-matrix/
keywords: ams-latex, amsmath, amscd, matriz de látex, casos de látex, delarray de látex, diagramas conmutativos de látex
description: Este artículo proporciona una breve introducción a la composición tipográfica de estructuras tipo matriz LaTeX utilizando paquetes AMS-LATEX.
lastmod: "2024-10-30"
---

{{<section overview>}}

Hay varios entornos para componer estructuras tipo matriz definidas en el paquete `amsmath`. Todos son similares al entorno estándar `array` de LaTeX en sintaxis y diseño. En general, una amplia variedad de estructuras matemáticas bidimensionales y diseños tabulares pueden describirse como matrices.

Tres entornos, `cases`, `matrix` y `pmatrix`, reemplazan los comandos del LaTeX estándar. Los comandos estándar usan una notación diferente, por lo que no se pueden usar junto con los formularios de entorno que se analizan aquí. El paquete `amsmath` producirá un mensaje de error si se utiliza uno de los comandos antiguos. Por el contrario, si intenta utilizar los formularios del entorno `amsmath` sin cargar el paquete, lo más probable es que reciba el siguiente mensaje de error: `"Carácter de tabulación de alineación fuera de lugar &"`.


## 3.1. El entorno de los "casos"

El entorno "case" se utiliza para manejar construcciones, donde una sola ecuación tiene algunas variantes. Este tipo de construcciones son muy comunes en matemáticas. Produce una matriz con dos columnas, ambas alineadas a la izquierda.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
P_{r - j} = \begin{cases}
                     0 & \text{if $r - j$ is odd,} \\
r! \, (-1)^{(r - j)/2} & \text{if $r - j$ is even.}
\end{cases}
\end{equation}
```

![Entorno de casos](/tex/images/java/tutorial/latex-ams-math-3-1.png)

Observe el uso del comando `\text` y el "modo matemático integrado" en las cadenas de texto.

## 3.2. Los entornos matriciales

Los entornos matriciales, a diferencia del `array` de LaTeX, no aceptan un argumento que especifique los formatos de las columnas. En cambio, proporcionan un formato predeterminado: hasta 10 columnas centradas. El espaciado también difiere ligeramente del predeterminado en "matriz". Los siguientes ejemplos ilustran los entornos `matrix`, `pmatrix`, `bmatrix`, `Bmatrix`, `vmatrix` y `Vmatrix`.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \quad \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \\
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \quad \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} \\
\begin{vmatrix} a & b \\ c & d \end{vmatrix} \quad \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}
\end{gather*}
```

![Entornos matriciales](/tex/images/java/tutorial/latex-ams-math-3-2.png)

El contador `MaxMatrixCols` determina el número máximo de columnas en un entorno matricial. Puedes cambiarlo usando el comando de contador estándar de LaTeX. El valor del parámetro de longitud `\arraycolsep` determina la cantidad de espacio entre las columnas. Al igual que en las matrices estándar, pero no se agrega espacio a ninguno de los lados de la matriz. Más columnas harán que LaTeX trabaje más y requiera más recursos. Sin embargo, es posible establecer `MaxMatrixCols` en 20 o más sin que se vea afectado el rendimiento, ya que con las implementaciones TeX típicas de hoy en día dichos límites son menos importantes.

```tex
\usepackage{amsmath}
\setcounter{MaxMatrixCols}{20}
% -------------------------------------------------------------------------------
\[
\begin{Vmatrix}
\,a&b&c&d&e&f&g&h&i&j &\cdots\,{} \\
&a&b&c&d&e&f&g&h&i &\cdots\,{} \\
& &a&b&c&d&e&f&g&h &\cdots\,{} \\
& & &a&b&c&d&e&f&g &\cdots\,{} \\
& & & &\ddots&\ddots&\hdotsfor[2]{5}\,{}
\end{Vmatrix} \]
```

![Más columnas en entornos matriciales](/tex/images/java/tutorial/latex-ams-math-3-3.png)

En este ejemplo, el comando `\hdotsfor` se utiliza para producir una fila de puntos en una matriz, que abarca un número determinado de columnas. El parámetro opcional (aquí 2) se puede utilizar para especificar un multiplicador para el espacio predeterminado (3 unidades matemáticas) entre los puntos. El espacio delgado y el grupo de llaves `\,{}` al final de cada fila simplemente hacen que el diseño se vea mejor; juntos producen dos espacios delgados, de aproximadamente 6mu o 1/3em.

Para producir una pequeña matriz en línea para usar en texto, puede utilizar el entorno `smallmatrix`.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
To show the effect of the matrix on surrounding lines inside a paragraph, we put it here:
$ \left( \begin{smallmatrix}
1 & 0 \\ 0 & -1
\end{smallmatrix} \right) $
and follow it with enough text to ensure that there is at least one full line below the matrix.
```

![El entorno de Smallmatrix](/tex/images/java/tutorial/latex-ams-math-3-4.png)

Tenga en cuenta que las líneas de texto no están separadas aunque la línea anterior a la matriz pequeña contenga letras con descendentes.

## 3.3. Apilamiento en subíndices y superíndices

A veces es posible que necesites escribir varias líneas dentro de un subíndice o superíndice. Para hacer esto, puede usar el comando `\substack` con `\\` delimitando filas.

El entorno `subarray` es una estructura un poco más general que le permite alinear líneas a la izquierda o a la derecha, en lugar de centrarlas.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\sum_{\substack{0 \le i \le m \\ 0 < j < n}} P(i, j) \\
\sum_{\begin{subarray}{l}
i \in \Lambda \\
0 \le i \le m \\
0 < j < n
\end{subarray}} P(i, j)
\end{gather}
```

![Apilamiento en subíndices y superíndices](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> Tenga en cuenta que ambos entornos deben estar entre llaves cuando aparecen como subíndice o superíndice.

## 3.4. Diagramas conmutativos
El paquete `amscd` define algunos comandos para producir diagramas conmutativos simples basados ​​en matrices. Existen algunas formas abreviadas útiles para especificar flechas decoradas y otros conectores. Sin embargo, tiene limitaciones: por ejemplo, estos conectores sólo pueden ser horizontales o verticales.

En el entorno `CD`, las notaciones `@>>>`, `@<<<`, `@VVV` y `@AAA` producen flechas derecha, izquierda, abajo y arriba, respectivamente. El siguiente ejemplo también muestra el uso del comando `\DeclareMathOperator`.

```tex
\usepackage{amsmath,amscd}
\DeclareMathOperator\add{add}
\DeclareMathOperator\cf {cf}
\DeclareMathOperator\cov{cov}
\DeclareMathOperator\non{non}
% -------------------------------------------------------------------------------
\[ \begin{CD}
\cov (L) @>>> \non (K) @>>> \cf (K) \\
@VVV @AAA @AAA \\
\add (L) @>>> \add (K) @>>> \cov (K) \\
\end{CD} \]
```

![Diagrama conmutativo simple](/tex/images/java/tutorial/latex-ams-math-3-6.png)

Veamos cómo se especifican las decoraciones. Para las flechas horizontales, el material entre el primer y el segundo símbolo `>` o `<` se compondrá como superíndice, y el material entre el segundo y el tercero se compondrá como subíndice. De manera similar, el material entre la primera y la segunda, o la segunda y la tercera, "A" o "V" de flechas verticales se compondrá como "guión lateral" izquierdo o derecho. Veremos el uso de este formato en el siguiente ejemplo.

Las notaciones `@=` y `@|` dan líneas dobles horizontales y verticales.

En lugar de una flecha visible, puede usar una "flecha nula" (`@.`) para completar una matriz donde sea necesario.

```tex
\usepackage{amsmath, amscd}
\DeclareMathOperator{\End}{End}
% -------------------------------------------------------------------------------
\[ \begin{CD}
S^{W_\Lambda}\otimes T @>j>> T \\
@VVV @VV{\End P}V \\
(S \otimes T)/I @= (Z\otimes T)/J
\end{CD} \]

```

![Diagrama conmutativo con guiones](/tex/images/java/tutorial/latex-ams-math-3-7.png)

Se puede producir un diseño similar en LaTeX estándar. Pero no parece tan bueno.

```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![Diagrama conmutativo en LaTeX estándar](/tex/images/java/tutorial/latex-ams-math-3-8.png)

Este ejemplo muestra claramente cuánto mejores resultados produce el paquete `amscd`: la notación es más sencilla, las flechas horizontales son más largas y el espacio entre elementos ha mejorado mucho. Los paquetes más especializados te ayudarán a lograr resultados aún más bellos.

## 3.5. Delimitadores que rodean una matriz: el paquete `delarray`

En esta sección, discutiremos una extensión general útil del paquete `array`. Con esta extensión, el usuario puede especificar delimitadores extensibles de apertura y cierre para rodear un entorno de "matriz" matemática. Veamos el ejemplo:

```tex
\usepackage{delarray}
% -------------------------------------------------------------------------------
\[ \mathcal{Q} =
\begin{array}[t] ( {cc} ) X & Y \end{array}
\begin{array}[t] [ {cc} ] A & B \\ C & D \end{array}
\begin{array}[b] \lgroup{cc}\rgroup L \\ M \end{array}
\]
```

![El uso del paquete delarray](/tex/images/java/tutorial/latex-ams-math-3-9.png)

> Tenga en cuenta que el paquete `delarray` es independiente de `amsmath`, pero carga automáticamente el paquete `array` si es necesario.

Los delimitadores se colocan a ambos lados de `{cc}`.

Este ejemplo también ilustra la característica más útil del paquete `delarray`: el uso de los argumentos opcionales `[t]` y `[b]`, que no están permitidos con los entornos matriciales de `amsmath`. Estos muestran que el uso de la sintaxis `delarray` no es equivalente a rodear el entorno `array` con `\left` y `\right`, ya que los delimitadores se elevan al igual que el propio array.