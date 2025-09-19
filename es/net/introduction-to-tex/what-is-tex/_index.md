---
translation: true
template: /templates/_template-net.md
title: ¿Qué es TeX?
linktitle: ¿Qué es TeX?
weight: 10
url: /net/what-is-tex/
keywords: que es tex
description: Esta página responde brevemente a la pregunta "¿Qué es TeX?" ¿Es uno de los lenguajes de programación o se considera un formato de documento?
lastmod: "2024-10-30"
---

{{<section overview>}}

## Lo que NO es TeX

TeX definitivamente no es un formato en absoluto.

## ¿Qué es Texas?

Entonces, ¿qué es TeX? Bueno, esa es la cuestión, como dijo Hamlet[^1]. Intentemos responderla de la forma más sencilla posible.

Imaginemos que tenemos un lenguaje de programación que consta de dos comandos elementales (llamados *secuencias de control*), o *primitivos*, `\a` y `\b`. Y en este lenguaje podemos escribir programas para componer documentos (libros, artículos, etc.). Llamemos a este lenguaje **(L1)**. Para que estos programas se ejecuten de una determinada forma, contamos con un determinado motor que interpreta los comandos de este lenguaje.

Ahora supongamos que al escribir un programa de composición tipográfica para algún documento, encontramos que la subsecuencia `\a \b \a` ocurre con bastante frecuencia. Y supongamos también que en nuestro lenguaje existe otra primitiva `\def`, que nos permite definir subrutinas, o macros. Llamemos a este lenguaje **(L2)**. En estas circunstancias, podemos definir la macro `\def\c{\a \b \a}` al comienzo del programa y reemplazar cada aparición de la subsecuencia con `\c` tanto para una mejor legibilidad como para una mejor reducción.

Ahora bien, si queremos componer otro documento, en cuyo programa también se produce con frecuencia esta subsecuencia de comandos, tendremos que volver a definir esta macro. Pero supongamos que nuestro motor es capaz de cargar la macro `\c` en su estado interno y luego guardar ese estado como un archivo binario (un *volcado*), que luego se cargará automáticamente ("encima" del **(L2)** conjunto de comandos de lenguaje) antes de procesar los programas de composición tipográfica de cada documento en el que se requiere la macro `\c`. Llamaremos *formato* al conjunto de primitivas extendidas por la macro `\c`. Por lo tanto, nuestro formato es una *extensión de macro* del lenguaje primitivo de bajo nivel **(L2)**.

El motor también contiene una serie de registros internos, o *parámetros internos*, a los que se puede acceder mediante secuencias de control. Además de las definiciones de macros, un formato puede contener expresiones de inicialización para estos parámetros.

Sucedió que <a href="https://en.wikipedia.org/wiki/Donald_Knuth" target=_blank rel="nofollow">Donald E. Knuth</a>, definió un lenguaje similar a **(L2) **, pero con un conjunto mucho más amplio de primitivas, al que llamó TeX. También creó un motor que entendía (y todavía entiende) el lenguaje TeX. También lo llamó TeX.

Afortunadamente, estas no fueron las únicas cosas que hizo. También propuso la extensión macro, o formato, que llamó *Plain* TeX, que hizo que escribir programas fuera más conveniente. El conjunto inicial de primitivas de TeX a veces se llama VirTeX ("Vir" para "virgen") y, formalmente, también es un formato, cuando se considera junto con los valores predeterminados de los parámetros internos.

** Entonces, por un lado, TeX ES un lenguaje de programación. Y por otro lado, ES un motor intérprete que entiende este idioma. Y, por otro lado, TeX es un concepto más general que significa un sistema tipográfico en su totalidad.**

Lo único que queda por señalar aquí es que, de hecho, los caracteres del texto que se está escribiendo también son comandos que obligan al motor TeX a escribir los caracteres correspondientes (teniendo en cuenta la codificación de entrada actual) utilizando la configuración de fuente actual (que, a su vez son controlables mediante secuencias de control). Por tanto, al definir macros, también podemos utilizar caracteres.

Esperamos que a partir de ahora la pregunta “¿Qué es TeX?” ya no existe en tu mente.
[^1]: 1 