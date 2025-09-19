---
translation: true
template: /templates/_template-java.md
linktitle: Grandes operadores
title: 6. Grandes operadores
weight: 60
url: /java/latex-math-large-operators/
keywords: LaTeX, fórmulas matemáticas de LaTeX, matemáticas de LaTeX, operadores grandes de matemáticas de LaTeX, suma de LaTeX, integral de LaTeX
description: Este artículo analiza cómo crear fórmulas matemáticas que contengan operadores grandes, como suma e integración con TeX y LaTeX.
lastmod: "2024-10-30"
---

{{<section overview>}}

En matemáticas, hay símbolos que denotan, por ejemplo, operaciones de "suma" o "integración". Se denominan "operadores grandes" y se escriben del mismo modo que se escriben símbolos y letras normales. La diferencia es que TeX elegirá un símbolo más grande para el operador grande en el estilo de visualización que en el estilo de texto.

![Suma e integración sin superíndices/subíndices](/tex/images/java/tutorial/latex-math-6-1.png)

Una `\sum` mostrada generalmente ocurre con "límites", es decir, con subfórmulas que deben aparecer encima y debajo de ella. Los límites deben escribirse como si fueran subíndices y superíndices;
`$$\sum_{n=1}^m$$` o `$$\sum^m_{n=1}$$` ambos producen

![Suma con límites](/tex/images/java/tutorial/latex-math-6-2.png)

Las convenciones normales de composición tipográfica matemática suponen que la fórmula anterior debe cambiarse a

![Suma sin límites](/tex/images/java/tutorial/latex-math-6-3.png)

(es decir, sin límites) si ocurre en texto en lugar de en una visualización. Y TeX sigue estas convenciones.

Los superíndices y subíndices en el signo de integración no están establecidos como límites ni siquiera en el estilo de visualización:

![Integración en texto y en display](/tex/images/java/tutorial/latex-math-6-4.png)

Establecer subíndices y superíndices como límites proporciona una mejor apariencia si las subfórmulas son complejas, aunque ocupa más espacio en la página. Puede forzar a TeX a procesar la fórmula de esta manera escribiendo `\limits` inmediatamente después de `\int`, o `\sum`, u otro operador, sin importar qué estilo se usará en la subfórmula. Por otro lado, a veces no son deseables límites en los signos de suma mostrados. Puedes cambiar la convención de TeX escribiendo `\nolimits` inmediatamente después del operador grande.

![Forzando límites y no límites para la suma e integración](/tex/images/java/tutorial/latex-math-6-5.png)

Si dice `\nolimits\limits` (por ejemplo, algunas macros como `\int` especifican `\nolimits`), el último comando tiene prioridad. El comando `\displaylimits` se puede utilizar para cambiar a las convenciones normales de TeX; es decir, los límites se mostrarán sólo en los estilos *D* y *D'*.

Si necesita poner más de una fila de límites bajo un operador grande, puede hacerlo con `\atop`. La forma correcta de escribir la siguiente fórmula es 

```tex
$$\sum_{\scriptstyle0\le i\le m\atop\scriptstyle0<j<n}P(i,j)$$.
```

![Límites de varias filas bajo el signo de suma](/tex/images/java/tutorial/latex-math-6-6.png)

El comando `\scriptstyle` es necesario aquí; de lo contrario, ambas filas del límite habrían estado en tamaño scriptscript, que es demasiado pequeño. Este es otro caso raro en el que es necesario anular las reglas de estilo de TeX.