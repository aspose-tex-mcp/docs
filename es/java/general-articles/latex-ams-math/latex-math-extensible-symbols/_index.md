---
translation: true
template: /templates/_template-java.md
linktitle: Símbolos extensibles y ajustables.
title: 5. Símbolos extensibles y ajustables
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: ams-latex, amsmath, amsxtra, operadores matemáticos de LaTeX, delimitadores matemáticos de LaTeX, corchetes matemáticos de LaTeX, llaves matemáticas de LaTeX, acentos matemáticos de LaTeX
description: Este artículo analiza las características de LaTeX relacionadas con el trabajo con símbolos matemáticos extensibles y ajustables.
lastmod: "2024-10-30"
---

{{<section overview>}}

En LaTeX, existen ciertas características que permiten producir estructuras que pueden crecer hasta cualquier tamaño requerido. La composición tipográfica matemática necesita urgentemente dicha variabilidad. Discutiremos algunos aspectos del mismo en este artículo. Todos los comandos cubiertos en esta sección (a menos que se indique lo contrario) se proporcionan en LaTeX estándar.

## 5.1. Elipsis...

El paquete `amsmath` reemplaza (en casi todos los casos) todos esos `\ldots`, `cdots`, etc. del LaTeX estándar con el único comando `\dots`. Tanto la posición vertical de los puntos suspensivos como el espacio a su alrededor se seleccionan automáticamente dependiendo del tipo de símbolo que sigue a `\puntos`. Si el siguiente símbolo es, digamos, un signo más, los puntos aparecerán centrados; si es una coma, caerán en la línea de base. Siempre son tres puntos pero el espaciado es variable.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![Elipsis con espaciado determinado automáticamente](/tex/images/java/tutorial/latex-ams-math-5-1.png)

Sin embargo, cuando los puntos aparecen al final de una fórmula, el siguiente objeto será algo como `\end` o `\)` o `$`, y no le da a LaTeX ninguna pista sobre la posición de los puntos. En tal caso, debe ayudar usando `\dotsc` para puntos seguidos de comas, `\dotsb` para puntos seguidos de *operador binario* o *símbolo de relación*, `\dotsm` para puntos seguidos de puntos de multiplicación, ` \dotsi` para puntos seguidos de integrales, o `\dotso` en cualquier otro caso.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![Elipsis al final de una fórmula](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2. Símbolos que son extensibles horizontalmente.

Básicamente, LaTeX permite configurar cualquier comando de acento matemático para producir el glifo apropiado a partir de un rango de anchos siempre que las fuentes disponibles lo proporcionen. Sin embargo, en LaTeX estándar sólo existen dos de estos comandos: `\widehat` y `\widetilde`.

En el siguiente ejemplo, demostramos el uso de algunos comandos que producen construcciones similares a los acentos extensibles antes mencionados. Todos producen símbolos compuestos de la clase de matemáticas *Ordinaria*.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
\widehat {\psi_\delta(t) E_t h}
&= \widetilde {\psi_\delta(t) E_t h} \\
\overline {\psi_\delta(t) E_t h}
&= \underline {\psi_\delta(t) E_t h} \\
\overbrace {\psi_\delta(t) E_t h}
&= \underbrace {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\
\overrightarrow {\psi_\delta(t) E_t h} 
&= \overleftarrow {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\[-3pt]
& & & \text{without \textsf{amsmath}} \\
\underrightarrow {\psi_\delta(t) E_t h}
&= \underleftarrow {\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}} \\
\overleftrightarrow {\psi_\delta(t) E_t h}
&=\underleftrightarrow{\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}}
\end{align*}
```

![Acentos extensibles](/tex/images/java/tutorial/latex-ams-math-5-3.png)

Aquí, "cambiar estilo" significa que el símbolo empleado se ve afectado por el estilo matemático en uso para que se vea bien cuando se use, por ejemplo, en fracciones o subíndice/superíndice. Aquellos que no cambien de estilo aparecerán correctamente sólo en el nivel superior de las fórmulas mostradas.

## 5.3. Símbolos que son extensibles verticalmente.

La extensibilidad vertical es mucho más amplia. La siguiente tabla enumera todos los símbolos que son extensibles verticalmente.

*Símbolos verticalmente extensibles*

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Paréntesis"](/tex/images/java/tutorial/latex-ams-math-delim-5-1.png) | `(` `)` | !["Llaves abiertas"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\{` `\}` | !["Barras verticales dobles"](/tex/images/java/tutorial/latex-ams-math-delim-5-18.png) | *`\lVert` `\rVert`* |
| !["Corchetes angulares"](/tex/images/java/tutorial/latex-ams-math-delim-5-2.png) | `\langle` `\rangle` | !["Las llaves se cierran"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\lbrace` `\rbrace` | !["Barras verticales simples"](/tex/images/java/tutorial/latex-ams-math-delim-5-19.png) | *`\lvert` `\rvert`* |
| !["Grupo L y grupo R"](/tex/images/java/tutorial/latex-ams-math-delim-5-3.png) | `\lgroup` `\rgroup` | !["Los corchetes se abren"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `[` `]` | !["Barra vertical"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `|` |
| !["Bigotes"](/tex/images/java/tutorial/latex-ams-math-delim-5-4.png) | `\lmoustache` `\rmoustache` | !["Corchetes para cerrar"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `\lbrack` `\rbrack` | !["Barra vertical"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\vert` |
| !["Flecha hacia abajo"](/tex/images/java/tutorial/latex-ams-math-delim-5-5.png) | `\Downarrow` | !["Soportes de techo abiertos"](/tex/images/java/tutorial/latex-ams-math-delim-5-13.png) | `\lceil` `\rceil` | !["Barra vertical de flecha"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\arrowvert` |
| !["Flecha hacia arriba"](/tex/images/java/tutorial/latex-ams-math-delim-5-6.png) | `\Uparrow` | !["Soportes de piso cerrados"](/tex/images/java/tutorial/latex-ams-math-delim-5-14.png) | `\lfloor` `\rfloor` | !["Barra vertical de refuerzo"](/tex/images/java/tutorial/latex-ams-math-delim-5-21.png) | `\bracevert` |
| !["Flecha hacia arriba y hacia abajo"](/tex/images/java/tutorial/latex-ams-math-delim-5-7.png) | `\Updownarrow` | !["Corchetes dobles abiertos"](/tex/images/java/tutorial/latex-ams-math-delim-5-15.png) | ***`\llbracket` `\rrbracket`*** | !["Barra vertical de flecha doble"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Arrowvert` |
| !["Flecha simple hacia abajo"](/tex/images/java/tutorial/latex-ams-math-delim-5-8.png) | `\downarrow` | !["Barra diagonal"](/tex/images/java/tutorial/latex-ams-math-delim-5-16.png) | `/` | !["Línea vertical doble"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\|` |
| !["Flecha hacia arriba simple"](/tex/images/java/tutorial/latex-ams-math-delim-5-9.png) | `\uparrow` | !["Barra diagonal inversa"](/tex/images/java/tutorial/latex-ams-math-delim-5-17.png) | `\backslash` | !["Línea vertical doble"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Vert` |
| !["Flecha simple hacia arriba y hacia abajo"](/tex/images/java/tutorial/latex-ams-math-delim-5-10.png) | `\updownarrow` | | `.` | !["Signo de raíz cuadrada"](/tex/images/java/tutorial/latex-ams-math-delim-5-23.png) | `\sqrtsign` |


> *Los símbolos en cursiva requieren el paquete `amsmath` o, si se escriben además en negrita, el paquete `stmaryrd`. Un punto (.) no es en sí mismo un símbolo extensible, pero se puede utilizar para producir un delimitador "invisible". El símbolo `\sqrtsign` no se puede utilizar con `\left`, `\right` o `\middle`.*

> *Sinónimos: [ - `\lbrack`, `[`;	] - `\rbrack`, `]`;	{ - `\lbrace`, `\{`;	} - `\rbrace`, `\}`; | - `\vert`, `|`;	|| - `\Vert`, `\|`.*

Estos símbolos se vuelven extensibles sólo en ciertos usos. Deberán basarse en la siguiente construcción:

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```
> Si LaTeX utiliza el programa eTeX, también puede utilizar estos símbolos extensibles con `\middle`.

Aquí `<ext-Open>` y `<ext-Close>` pueden ser cualquiera de los símbolos (excepto `\sqrtsign`) enumerados en la tabla anterior. Deben ser símbolos que se hayan configurado para ser extensibles como se describe en [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf). Por lo tanto, debe estar disponible un símbolo que represente la ausencia de un glifo real. Sucedió que este símbolo, también conocido como *delimitador nulo*, es el punto (.). Los tamaños de los glifos reales para componer un símbolo extensible se eligen para que se ajusten a la altura y profundidad de la subfórmula que se encuentra entre ellos.

El símbolo radical `\sqrtsign` crece tanto vertical como horizontalmente para adaptarse al tamaño de su argumento. En LaTeX, preferirías usar el comando `\sqrt` para obtener este símbolo.

```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![Radicales extendidos](/tex/images/java/tutorial/latex-ams-math-5-24.png)