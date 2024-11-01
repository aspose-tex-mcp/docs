---
translation: true
template: /templates/_template-java.md
linktitle: Símbolos en LaTeX.
title: 9. Símbolos en fórmulas matemáticas | Manual de látex
weight: 90
url: /java/latex-math-symbols/
keywords: ams-latex, amsmath, amsfonts, amssymb, clases de símbolos matemáticos de látex, paquete stmaryrd, fuente st mary road, simbolos en latex
description: Clasificación de símbolos matematicos LaTeX y acceso a símbolos de varios tipos utilizando comandos estándar de TeX (LaTeX) y el paquete amssymb.
lastmod: "2024-10-30"
---

{{<section overview>}}

Las tablas de este artículo enumeran la amplia gama de símbolos matemáticos proporcionados por los paquetes AMS-LATEX, incluidos comandos para acceder a cada símbolo. También incluyen los símbolos complementarios de la fuente **St Mary Road** diseñada por Allan Jeffrey y Jeremy Gibbons. Este paquete amplía las colecciones de fuentes de símbolos **Computer Modern** y AMS y normalmente debe cargarse además de `amssymb`, pero siempre después de él. Proporciona símbolos adicionales para campos como programación funcional, álgebra de procesos, teoría de dominios, lógica lineal y muchos más.

Las tablas indican qué paquetes adicionales deben cargarse para usar cada comando de símbolo. Los símbolos con nombres de comandos en negro están disponibles en LaTeX estándar. Los símbolos con nombres de comandos en azul requieren cargar `amsmath`, `amssymb` o `stmaryrd`. Si es necesario, se proporciona una clasificación adicional mediante marcas: <sup>(*StM*)</sup> significa un símbolo de `stmaryrd` cuando la tabla también contiene símbolos de otros paquetes; <sup>(*kernel*)</sup> marca símbolos que están disponibles en LaTeX estándar pero solo combinando dos o más glifos, mientras que existe un solo glifo en el paquete indicado; y <sup>(*var*)</sup> marca "Símbolos alfabéticos" (de tipo `\mathalpha`) que cambian de apariencia cuando se usan dentro del alcance de un [identificador del alfabeto matemático](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers).

## 9.1. clases de símbolos matemáticos

La clasificación principal de los símbolos matemáticos está relacionada con su significado en el uso técnico. En tipografía matemática, esta clasificación define el diseño de la fórmula. En particular, el formateador matemático de TeX ajusta el espacio horizontal a cada lado de cada símbolo según su clase matemática. Esta clasificación también hace algunas distinciones más finas, por ejemplo, entre acentos y símbolos simples y al dividir la enorme lista de símbolos de *Relación* en varias tablas.

La configuración para matemáticas coloca cada símbolo en una de estas clases: *Ordinario* (Ord), *Operador* (Op), *Binario* (Bin), *Relación* (Rel), *Apertura* (Abrir), *Cierre* (Cerrar), o *Puntuación* (Punct). La clase del símbolo se puede cambiar explícitamente usando los comandos `\mathord`, `\mathop`, `\mathbin`, `\mathrel`, `\mathopen`, `\mathopen` y `\mathpunct`. En el siguiente ejemplo, `\#` y `\top` (ambos Ord por defecto) se cambian a Rel y Op.

```tex
\usepackage[fleqn]{amsmath}
\[ a \# \top _x^\alpha x^\alpha_b \]
\[ a \mathrel{\#} \mathop{\top}_x^\alpha x^\alpha_b \]
```

![Cambiar explícitamente la clase de símbolo](/tex/images/java/tutorial/latex-ams-math-9-1.png)

Además de las clases anteriores, ciertas subfórmulas (principalmente fracciones y aquellas producidas por `\left` y `\right`) forman una clase llamada *Inner*, que está disponible explícitamente a través del comando `\mathinner`.

![Clases de símbolos y espaciado](/tex/images/java/tutorial/latex-ams-math-9-2.png)

> En la tabla, "0" significa "sin espacio", "1" significa `\thinmuspace`, "2" significa `\medmuskip`, "3" significa `\thickmuskip`, "*" significa "imposible". Las entradas en negrita significan que no se agrega el espaciado correspondiente en los estilos de escritura matemática.

TeX maneja el espaciado dentro de las fórmulas simplemente identificando la clase de cada objeto en una fórmula y luego agregando espacio entre cada par de objetos adyacentes como se define en la tabla anterior. Esta tabla está codificada en las rutinas de composición tipográfica matemática de TeX y, por lo tanto, los paquetes de macros no pueden modificarla.

Un símbolo *Binario* se convierte en un símbolo *Ordinario* siempre que no esté precedido ni seguido por símbolos de naturaleza compatible con una operación binaria. Por eso algunas entradas de la tabla están marcadas como imposibles. Por ejemplo, `$+x$` da +*x* (un más unario) y no + *x*. Este último puede ser producido por `${}+x$`.

Considere la siguiente fórmula (los valores predeterminados se cambian para mostrar los espacios agregados con mayor claridad):

```tex
thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[
a - b = -\max \{ x , y \}
\]
```

![\thinmuskip, \medmuskip y \thickmuskip](/tex/images/java/tutorial/latex-ams-math-9-3.png)

TeX identifica los objetos como Ord, Bin, Ord, etc., y luego inserta espacios de la siguiente manera:

```
 A      -      b      =      -    \max   \{   x    ,       y   \}
Ord \: Bin \: Ord \; Rel \; Ord \, Op   Open Ord Punct \, Ord Close
```

El signo menos delante de `\max` se convierte en *Ordinario* porque un *Binario* no puede seguir una *Relación*.

En una construcción "`\left...\right`", toda la subfórmula delimitada por la construcción se convierte en un único objeto de clase *Inner*. Por el contrario, comandos como `\Bigl` y `\Bigr` producen símbolos individuales de las clases *Apertura* y *Cierre*, respectivamente. La diferencia entre ellos se revela en la tabla de espaciado anterior. Aunque pueden dar como resultado delimitadores de igual tamaño vertical, pueden surgir diferencias de espaciado dependiendo de los objetos adyacentes en la fórmula. Por ejemplo, *Ordinario* seguido de *Apertura* no tiene espacio, mientras que *Ordinario* seguido de *Interior* está separado por un espacio fino. Los espacios dentro de la subfórmula dentro de una construcción "`\left...\right`" se crean como se esperaba, comenzando con un símbolo de *Apertura* y terminando con un símbolo de *Cierre*.

```tex
\thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[ a \Bigl( \sum x \Bigr) \neq a \left( \sum x \right) \]
```

![\izquierda...\derecha y \Bigl...\Bigr](/tex/images/java/tutorial/latex-ams-math-9-4.png)

En resumen, es mejor comprobar que un símbolo pertenece a la clase deseada, en lugar de simplemente buscarlo en las tablas siguientes.

## 9.2. Letras, números y otros símbolos *ordinarios*

Las letras latinas ASCII sin acentos y los dígitos de los números arábigos se denominan "símbolos alfabéticos". La fuente en la que están escritos puede variar. En las fórmulas matemáticas, la fuente predeterminada para las letras latinas es cursiva, mientras que para los dígitos árabes es vertical/romana. Los símbolos alfabéticos son todos de la clase *Ordinario*.

![Símbolos de clase \mathord (griego)](/tex/images/java/tutorial/latex-ams-math-9-5.png)

A diferencia de las letras latinas, las letras matemáticas griegas ya no están estrechamente relacionadas con los glifos utilizados para componer texto griego normal. Debido a una curiosa casualidad del siglo XVIII, en la principal tradición europea de tipografía matemática, la fuente predeterminada para las letras griegas minúsculas en las fórmulas matemáticas es cursiva, mientras que para las letras griegas mayúsculas es vertical/romana. (En física y química, por ejemplo, las tradiciones tipográficas son ligeramente diferentes).

Las letras mayúsculas griegas en las primeras filas de la siguiente tabla también son símbolos alfabéticos cuya fuente varía, siendo la predeterminada vertical/romana. Hay letras griegas mayúsculas, cada una de las cuales tiene la misma apariencia que alguna letra latina (por ejemplo, *A* y *Alpha*, *B* y *Beta*, *K* y *Kappa*, *O* y *Omicron *). Estas letras no están presentes en la tabla. Por la misma razón, no hay ómicrón en minúsculas. En la práctica, las letras griegas que parecen letras latinas no se utilizan en fórmulas matemáticas.

![letras griegas](/tex/images/java/tutorial/latex-ams-math-9-6.png)

> Los símbolos en azul requieren el paquete `amssymb`. <sup>(*var*)</sup> indica un símbolo alfabético variable.

La siguiente tabla enumera otros símbolos en forma de letras de la clase *Ordinario*. Las primeras cuatro son letras hebreas.

![Símbolos de clase \mathord (en forma de letra)](/tex/images/java/tutorial/latex-ams-math-9-7.png)

> Los símbolos en azul requieren el paquete `amssymb`.

La siguiente tabla enumera los símbolos restantes de la clase *Ordinario*, incluyendo algunos signos de puntuación comunes. Se comportan como letras y dígitos, por lo que nunca tienen espacio adicional a su alrededor.

![Símbolos de clase \mathord (varios)](/tex/images/java/tutorial/latex-ams-math-9-8.png)

> Los símbolos en azul requieren el paquete `amssymb` o, si están marcados con <sup>(*StM*)</sup>, el paquete `stmaryrd`.

> Tenga en cuenta que el signo de exclamación, el punto y el signo de interrogación no se tratan como signos de puntuación en las fórmulas.

> Sinónimos: negación lógica - `\lnot`, `\neg`; `|` - `\vert`, `|`; `||` - `\Vert`, `\|`.

Un error común es utilizar estos símbolos directamente como operadores *binarios* o símbolos *de relación*, sin utilizar un comando de símbolo matemático correctamente definido para ese tipo. Por lo tanto, si usa comandos como `\#`, `\square` o `\&`, verifique cuidadosamente que obtenga los espacios entre símbolos correctos o, mejor aún, defina su propio comando de símbolo.

```tex
\usepackage[fleqn]{amsmath} \usepackage{amssymb}
\DeclareMathSymbol\bneg {\mathbin}{symbols}{"3A}
\DeclareMathSymbol\rsquare{\mathrel}{AMSa}{"03}
% -------------------------------------------------------------------------------
\[ a \neg b \qquad x \square y + z \]
\[ a \mathbin{\neg} b \qquad x \mathrel{\square} y + z \]
\[ a \bneg b \qquad x \rsquare y + z \]
```

![Declaración de símbolos matemáticos](/tex/images/java/tutorial/latex-ams-math-9-9.png)

El comando `\DeclareMathSymbol` se utiliza para declarar su propio nombre de símbolo.

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

El primer argumento es el nombre del comando elegido. El segundo argumento es uno de los comandos correspondientes a la clase de símbolo. El tercer argumento identifica la fuente del símbolo de la que se debe obtener el símbolo. El cuarto argumento proporciona la posición del símbolo en la codificación de fuente, ya sea un valor decimal, octal o hexadecimal. Los valores correctos para los argumentos se pueden encontrar más fácilmente mirando las definiciones en el archivo `amssymb.sty` o `fontmath.ltx` (para los símbolos principales). Por ejemplo, buscamos `\neq` y `\square`, reemplazamos `\mathord` en cada caso y finalmente le dimos un nuevo nombre al símbolo resultante.

## 9.3. Acentos matemáticos

La siguiente tabla enumera los comandos de acento disponibles en las fórmulas. La mayoría de ellos están definidos en TeX estándar. Consulte [aquí](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible) para obtener información sobre acentos extensibles. Cuando agrega un acento matemático a un símbolo, el resultado es un símbolo de clase *Ordinario*.

![Acentos matemáticos, dando subfórmulas de clase \mathord](/tex/images/java/tutorial/latex-ams-math-9-10.png)

> Los acentos en azul requieren el paquete `amsmath`.

> Los dos últimos acentos están disponibles en una variedad de anchos, y se utiliza automáticamente el más grande que sea adecuado.

```tex
\usepackage{amstext}
% -------------------------------------------------------------------------------
\[ a = b \text{ but } a \tilde{=} b
\text{ which is not } a \mathrel{\tilde{=}} b \]
```

![Hacer un símbolo de relación a partir de un símbolo acentuado](/tex/images/java/tutorial/latex-ams-math-9-11.png)

Otras formas de colocar símbolos sobre símbolos de *Relación* se muestran [aquí](/tex/{{lang.url-fragment}}java/latex-math-decorations/#47-other-decorations). Al agregar un acento a *i* o *j* en fórmulas matemáticas, es mejor usar las variantes sin puntos `\imath` y `\jmath`.

## 9.4. Símbolos del operador *binario*

Hay más de 100 símbolos de clase *Binario* entre los que elegir. La mayoría de ellos se enumeran en la siguiente tabla. Algunos de ellos también están disponibles como símbolos de *Relación*, aunque con nombres diferentes.

![Símbolos de clase \mathbin (varios)](/tex/images/java/tutorial/latex-ams-math-9-12.png)

> Los símbolos en azul requieren el paquete `amssymb` o, si están marcados con <sup>(*StM*)</sup>, el paquete `stmaryrd`.

> Los triángulos izquierdo y derecho también están disponibles como símbolos de *Relación*.

> El paquete `stmaryrd` cambia de manera confusa los símbolos *Binarios* `\bigtriangleup` y `\bigtriangledown` en *Operadores*, dejando solo los sinónimos `\varbigtriangleup` y `\varbigtriangledown` para las formas de operador *Binario*.

El paquete `amssymb` ofrece algunos símbolos de cuadro para usar como operadores *binarios*; `stmaryrd` agrega muchos más. Vea la siguiente tabla.

![Símbolos de clase \mathbin (cuadros)](/tex/images/java/tutorial/latex-ams-math-9-13.png)

> Todos los símbolos requieren el paquete `amssymb` o, si está marcado con <sup>(*StM*)</sup>, el paquete `stmaryrd`.

Puede cargar el paquete `stmaryrd` con la opción `heavycircles`. Como resultado, cada comando de símbolo de círculo de la siguiente tabla que comienza con `\var` intercambia su definición con el comando correspondiente sin "var"; por ejemplo, el símbolo `\varodot` se convierte en `\odot` y viceversa.

![Símbolos de clase \mathbin (círculos)](/tex/images/java/tutorial/latex-ams-math-9-14.png)

> Los símbolos en azul requieren el paquete `amssymb` o, si están marcados con <sup>(*StM*)</sup>, el paquete `stmaryrd`.

> La opción `heavycircles` del paquete `stmaryrd` afecta a todos los comandos que comienzan con `\var` y sus variantes normales.

## 9.5. Símbolos de relación

La clase de símbolos binarios *Relación* es incluso mayor que la de los operadores *Binarios*. La siguiente tabla enumera los símbolos de igualdad y orden. Se puede colocar una barra diagonal en cualquier símbolo de *Relación* precediéndolo con el comando `\not`. El símbolo negado representa el complemento (o negación) de las relaciones.

![Símbolos de clase \mathrel (igualdad y orden)](/tex/images/java/tutorial/latex-ams-math-9-15.png)

> Los símbolos en azul requieren el paquete `amssymb` o, si está marcado <sup>(*StM*)</sup>, el paquete `stmaryrd`.

```tex
$ u \not< v$ or $a \not\in \mathbf{A} $
```

![Negar una relación](/tex/images/java/tutorial/latex-ams-math-9-16.png)

Este método genérico de negar un símbolo de *Relación* no siempre da buenos resultados, especialmente con símbolos más grandes, porque la barra siempre tendrá el mismo tamaño, posición e inclinación. Debido a este hecho, también están disponibles algunos "símbolos negados" especialmente diseñados. Vea la lista en la siguiente tabla.

![Símbolos de clase \mathrel (igualdad y orden�negados)](/tex/images/java/tutorial/latex-ams-math-9-17.png)

> Los símbolos en azul requieren el paquete `amssymb`.

Si hay una opción disponible, normalmente es preferible utilizar los glifos especialmente diseñados. Para ver por qué, compare los símbolos en el siguiente ejemplo.

```tex
\usepackage{amssymb}
% -------------------------------------------------------------------------------
$ \not\leq \ \not\succeq \ \not\sim $ \par
$ \nleq \ \nsucceq \ \nsim $
```

![Símbolos de relación negada compuestos y especialmente diseñados](/tex/images/java/tutorial/latex-ams-math-9-18.png)

La siguiente tabla enumera los símbolos de *Relación* para conjuntos e inclusiones.

![Símbolos de clase \mathrel (conjuntos e inclusión)](/tex/images/java/tutorial/latex-ams-math-9-19.png)

> Los símbolos en azul requieren el paquete `amssymb` o, si están marcados con <sup>(*StM*)</sup>, el paquete `stmaryrd`.

Y ahora negaciones de los símbolos de *Relación* para conjuntos e inclusión.

![Símbolos de clase \mathrel (conjuntos e inclusión negada)](/tex/images/java/tutorial/latex-ams-math-9-20.png)

> Los símbolos en azul requieren el paquete `amssymb`.

La siguiente tabla enumera los símbolos de *Relación* en forma de flecha. Algunas construcciones de flechas extensibles que producen símbolos compuestos de *Relación* se describen [aquí](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible).

![Símbolos de clase \mathrel (flechas)](/tex/images/java/tutorial/latex-ams-math-9-21.png)

> Los símbolos en azul requieren el paquete `amssymb` o, si están marcados con <sup>(*StM*)</sup>, el paquete `stmaryrd`.

Y aquí están los símbolos de *Relación* negados en forma de flecha.

![Símbolos de clase \mathrel (flechas negadas)](/tex/images/java/tutorial/latex-ams-math-9-22.png)

> Los símbolos en azul requieren el paquete `amssymb`.

Hay otros elementos (además de `\not` usado para negar símbolos generales de *Relación*) que fueron especialmente diseñados para negar o extender símbolos tipo flecha. Vea la siguiente tabla.

![Símbolos de clase \mathrel (negación y extensiones de flecha))](/tex/images/java/tutorial/latex-ams-math-9-23.png)

> Los símbolos en azul requieren el paquete `stmaryrd`.

> Estos símbolos se utilizan para combinar, principalmente con flechas; por ejemplo, `\longarrownot\longleftarrow`.

> Utilice `\joinrel` para "pegar" símbolos relacionales, por ejemplo, `\lhook\joinrel\longrightarrow`.

> Las dimensiones de estos símbolos los hacen inadecuados para otros usos.

```tex
\usepackage{stmaryrd}
% -------------------------------------------------------------------------------
$\Longarrownot\longleftrightarrow \qquad \arrownot \hookleftarrow$
```

![Negaciones de flecha](/tex/images/java/tutorial/latex-ams-math-9-24.png)

Finalmente, a continuación se muestran otros símbolos diversos de *Relación*.

![Símbolos de clase \mathrel (varios)))](/tex/images/java/tutorial/latex-ams-math-9-25.png)

> Los símbolos de *Relación* en azul requieren el paquete `amssymb`.

> `\therefore` es un símbolo de *Relación*, por lo que su espaciado puede no ser el esperado en usos comunes.
