---
translation: true
template: /templates/_template-java.md
linktitle: 7. Delimitadores
title: Delimitadores | Manual de látex | Aspose.TeX
weight: 70
url: /java/latex-math-delimiters/
keywords: látex, fórmulas matemáticas de látex, matemáticas de látex, delimitadores matemáticos de látex, llaves matemáticas de látex, corchetes matemáticos de látex, paréntesis matemáticos de látex
description: Este artículo analiza cómo dividir lógicamente fórmulas en subfórmulas con diferentes tipos de delimitadores.
lastmod: "2024-10-30"
---

{{<section overview>}}

Por muy grande que pueda ser una fórmula matemática, TeX conoce una manera de hacer que algunos símbolos sean lo suficientemente grandes como para tener la apariencia adecuada. Por ejemplo, el resultado de escribir

```tex
$$\sqrt{1+\sqrt{1+\sqrt{1+
            \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+x}}}}}}}$$
```

muestra una variedad de signos radicales o de raíz cuadrada disponibles:

![Radicales de diferentes tamaños](/tex/images/java/tutorial/latex-math-7-1.png)

Los tres carteles más grandes aquí son iguales, excepto por un segmento vertical que se repite tantas veces como sea necesario para alcanzar el tamaño requerido. Al mismo tiempo, los signos más pequeños son caracteres distintos tomados de las fuentes matemáticas de TeX.

Algo similar ocurre con los paréntesis y otros símbolos denominados "delimitadores". Estos símbolos son importantes en matemáticas porque dan pistas visuales sobre la estructura subyacente de expresiones complejas. En otras palabras, limitan los límites de las subfórmulas individuales. Aquí está la lista de los 22 delimitadores básicos proporcionados por LaTeX:

![Los 22 delimitadores básicos definidos en LaTeX](/tex/images/java/tutorial/latex-math-7-2.png)

Para obtener una versión un poco más grande de cualquiera de estos símbolos, simplemente escriba `\bigl` o `\bigr` para abrir o cerrar delimitadores, respectivamente. Esto hace que las fórmulas con delimitadores anidados sean más fáciles de leer:

![Los ejemplos de uso de \grandes delimitadores](/tex/images/java/tutorial/latex-math-7-3.png)

Los delimitadores `\big` son lo suficientemente grandes como para que se pueda notar la diferencia y, sin embargo, lo suficientemente pequeños como para usarse en el texto de un párrafo:

![Los delimitadores \grandes comparados con los normales](/tex/images/java/tutorial/latex-math-7-4.png)

Puede obtener símbolos un paso más grandes adecuados para pantallas, si escribe `\Bigl` y `\Bigr` en lugar de `\bigl` y `\bigr`:

![Los \Grandes delimitadores](/tex/images/java/tutorial/latex-math-7-5.png)

Son un 50% más altos que las versiones del paso anterior. Las fórmulas mostradas suelen utilizar delimitadores aún más altos (el doble del tamaño de `\big`). Puedes obtenerlos escribiendo `\biggl` y `\biggr`:

![Los \grandes delimitadores](/tex/images/java/tutorial/latex-math-7-6.png)

Finalmente, puede escribir las versiones `\Biggl` y `\Biggr`, 2,5 veces más altas que los delimitadores `\bigl` y `\bigr`:

![Los delimitadores \Bigg](/tex/images/java/tutorial/latex-math-7-7.png)

LaTeX también proporciona comandos `\bigm`, `\Bigm`, `\biggm` y `\Biggm` para producir delimitadores que se pueden usar en medio de fórmulas. Tal delimitador actúa como una relación, por lo que TeX coloca un poco de espacio a cada lado:

![Delimitadores en medio de fórmulas](/tex/images/java/tutorial/latex-math-7-8.png)

También es posible decir simplemente `\big`, `\Big`, `\bigg` o `\Bigg` para producir un delimitador que se comporte como una variable ordinaria. Estos comandos se usarían principalmente con barras diagonales y barras invertidas:

![Grandes símbolos ordinarios](/tex/images/java/tutorial/latex-math-7-9.png)

TeX implementa un algoritmo que determina qué tan alto debe ser un par de delimitadores para encerrar una subfórmula determinada. Puede usarlo, en lugar de decidir si un delimitador debe ser `\big` o `\bigg` o lo que sea. solo di

```tex
\left<delim1><subformula>\right<delim2>
```

y TeX escribirá una subfórmula, colocando los delimitadores especificados a la izquierda y a la derecha. El tamaño de los delimitadores será lo suficientemente grande como para cubrir la subfórmula:

![Delimitadores establecidos por los comandos \left y \right](/tex/images/java/tutorial/latex-math-7-10.png)

Cuando usas `\left` y `\right`, deben estar emparejados, al igual que las llaves lo hacen con los grupos. No puede tener `\left` en una subfórmula y `\right` en otra. Además, no puede escribir cosas como `\left(...{...\right...}` o `\left(...\begingroup...\right)...\endgroup`. Esto se debe a que TeX necesita componer la subfórmula que aparece entre `\left` y `\right` antes de poder decidir qué tan grandes deben ser los delimitadores. Cuando no estás usando `\left` y `\right`, no lo haces. No tiene que coincidir con los paréntesis y los corchetes, por lo que puede escribir algo como `$[0,1)$` o `$)($` o incluso `$)$`. E incluso cuando use `\left` y `\right`, no es necesario que coincidan con los símbolos particulares, de modo que `\left)` o `\right(` no causarán un error.

Pero ¿por qué molestarse en aprender sobre `\bigl` y `\bigr` y otros de su tipo, cuando TeX puede calcular automáticamente los tamaños de `\left` y `\right`? Hay al menos tres casos en los que querrás decidir por ti mismo cómo seleccionar el tamaño de delimitador adecuado:

(1) Simplemente compare las dos fórmulas siguientes:

![\left y \right vs. \bigl y \bigr con barras verticales](/tex/images/java/tutorial/latex-math-7-11.png)

De hecho, usar `\left` y `\right` no fue una buena elección, ya que no pudieron determinar el tamaño del delimitador apropiado para una mejor legibilidad.

(2) Por otro lado, a veces `\left` y `\right` eligen un delimitador mayor del deseado. Esto sucede principalmente cuando encierran a un operador grande en una pantalla:

![\left y \right vs. \bigl y \bigr con una sumatoria](/tex/images/java/tutorial/latex-math-7-12.png)

El algoritmo de TeX hace que `\left` y `\right` incluyan la `\sum` junto con sus límites, pero en casos especiales como este parece mejor dejar que los límites cuelguen un poco. Entonces los delimitadores `\ bigg` son mejores aquí.

(3) Cuando necesite componer una fórmula enorme que se muestra, debe dividirla en dos o más líneas. Y desea asegurarse de que sus delimitadores de apertura y cierre tengan el mismo tamaño; pero no puedes usar `\left` en la primera línea y `\right` en la última, ya que `\left` y `\right` deben aparecer en pares. La única solución es usar `\Biggl` (por ejemplo) en la primera línea y `\Biggr` en la última.

> Aunque `\left` y `\right` suelen ser delimitadores de cualquier tamaño, las barras y los corchetes angulares tienen un tamaño máximo. Si pides versiones realmente grandes de esos símbolos, obtendrás las más grandes disponibles.

También puedes utilizar un truco que produce el llamado delimitador nulo (en blanco). Necesitará dicho delimitador cuando necesite componer una fórmula que visualmente contenga solo un delimitador grande. Por ejemplo,

![Un delimitador nulo en casos](/tex/images/java/tutorial/latex-math-7-13.png)

tiene '{' pero no '}'. Puede producirse mediante una construcción de la forma

```tex
$$|x|=\left\{ ... \right.$$ 
```

donde `\right.` genera el delimitador nulo derecho.

LaTeX también proporciona algunos delimitadores más, que no figuran en el conjunto básico de 22 porque son algo especiales. Los comandos `\arrowvert`, `\Arrowvert` y `\bracevert` producen delimitadores hechos a partir de las partes repetibles de las flechas verticales, las flechas verticales dobles y las llaves grandes, respectivamente, sin puntas de flecha ni las partes rizadas de las llaves. Producen resultados similares a `\vert` y `\Vert`, pero están rodeados por más espacios en blanco y tienen un peso diferente. También hay `\lgroup` y `\rgroup`, que se construyen a partir de tirantes sin las partes intermedias; y `\lmoustache` y `\rmoustache`, que producen las mitades superior e inferior de aparatos ortopédicos grandes. Aquí se muestran las versiones `\Big` y `\bigg` de `\vert`, `\Vert` y estos siete delimitadores especiales:

![Delimitadores adicionales proporcionados por LaTeX](/tex/images/java/tutorial/latex-math-7-14.png)

Puede encontrar que `\lgroup` y `\rgroup` son como paréntesis en negrita, con curvas más pronunciadas en las esquinas; esto los hace atractivos para ciertas pantallas grandes. Tenga en cuenta que no puede usarlos exactamente como paréntesis, porque solo están disponibles en tamaños `\Big` y más.