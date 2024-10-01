---
translation: true
template: /templates/_template-java.md
linktitle: 1. Fórmulas simples
title: Fórmulas simples | manual de látex
weight: 10
url: /java/latex-math-simple-formulas/
keywords: látex, fórmulas matemáticas de látex, matemáticas de látex, letras matemáticas de látex, letras griegas de látex, números de látex
description: Este artículo analiza cómo crear expresiones matemáticas atómicas simples para fórmulas más complejas con TeX y LaTeX.
lastmod: "2024-10-30"
---

{{<section overview>}}

La fórmula más simple es una sola letra '*x*' o un solo dígito '4'. Para insertar una fórmula de este tipo en un texto LaTeX, escriba `$x$` o `$4$`, respectivamente. Todas las fórmulas matemáticas están encerradas entre corchetes matemáticos especiales ("$`).

Cuando escribe `$x$`, '*x*' aparece en cursiva, pero `$2$` produce '2' en tipo romano. En general, todos los caracteres de su teclado tienen una interpretación especial en las fórmulas matemáticas, de acuerdo con las convenciones normales de impresión matemática. Las letras indican letras en cursiva, mientras que los dígitos y las puntuaciones indican dígitos romanos y puntuación. Un guión (-) indica un signo menos. El `$` izquierdo pone TeX en "modo matemático" y el derecho lo elimina. Entonces, si olvida un `$` o escribe un `$` adicional, probablemente recibirá un mensaje de error porque TeX se confundirá.

TeX crea la mayor parte de su propio espaciado en fórmulas matemáticas. Al mismo tiempo, ignora los espacios que coloques entre `$`. Puede escribir `$(x + y)/(x - y)$` o `$(x+y) / (x-y)$`, ¡pero ambos darán como resultado una fórmula! [Subíndices y superíndices de un solo carácter](/tex/images/java/tutorial/latex-math-1-1.png) en el que hay un poco de espacio adicional alrededor de los signos '+' y '-' pero ninguno alrededor del signo '/'. Por lo tanto, no es necesario que recuerdes la complicada regla del espaciado matemático y eres libre de utilizar los espacios como quieras. Cuando es necesario marcar el final de secuencias de control (comandos), los espacios se siguen utilizando de forma normal. En la mayoría de los casos, el espaciado de TeX cumplirá con las expectativas de un matemático; pero si desea anular las reglas de espaciado de TeX, puede hacerlo con secuencias de control, que discutiremos más adelante.

Una de las cosas comunes que puedes encontrar en las fórmulas matemáticas es el uso de letras griegas. En LaTeX puedes escribir `$\alpha, \beta, \gamma, \delta$` para obtener las primeras cuatro letras griegas. Y `$\Gamma$`, por ejemplo, produce una letra gamma mayúscula. No confunda las letras griegas `\kappa` y `\nu` con las letras en cursiva *v* y *x*; el griego `\phi` es diferente del cero cortado llamado `\emptyset`. Una `\epsilon` minúscula es diferente del símbolo que denota pertenencia a un conjunto. Algunas letras griegas minúsculas tienen formas variantes en fuentes LaTeX en cursiva: `$\phi, \theta, \epsilon, \rho$` produce ![Subíndices y superíndices de un solo carácter](/tex/images/java/tutorial/latex-math-1-2.png) mientras que `$\varphi, \vartheta, \varepsilon, \varrho$` produce ![Subíndices y superíndices de un solo carácter](/tex/images/java/tutorial/latex-math-1-3.png)

Además de las letras griegas, hay muchos símbolos matemáticos como "aproximadamente igual" (`$\approx$`) y "se asigna a" (`$\mapsto$`). Puede encontrar una lista completa de estas secuencias de control y sus símbolos correspondientes [aquí](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/).