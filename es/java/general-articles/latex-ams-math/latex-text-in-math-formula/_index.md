---
translation: true
template: /templates/_template-java.md
linktitle: Texto en fórmulas matemáticas.
title: 6. Texto en fórmulas matemáticas | manual de látex
weight: 60
url: /java/latex-text-in-math-formula/
keywords: ams-latex, amsmath, operadores matemáticos de látex, funciones matemáticas de látex, texto matemático de látex
description: Este artículo analiza la inserción de texto en fórmulas matemáticas de LaTeX. También describe funciones y operadores matemáticos, así como el método para definirlos.
lastmod: "2024-10-30"
---

{{<section overview>}}

## 6.1. El comando `\texto`

Para poner texto normal dentro de matemáticas, es mejor usar el comando `\text` en lugar de comandos como `\mathrm`. El comando `\text` garantiza que el texto esté configurado con el tamaño de fuente correcto. La fuente será la fuente del texto que se utilice fuera del material matemático actual.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![Texto dentro de matemáticas](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. Nombres de operadores

Generalmente se prefiere distinguir los nombres de funciones matemáticas comunes (p. ej., *sin* y *log*) y operadores (p. ej., *min* y *sup*) de los nombres de variables que están en cursiva. Por lo tanto, tradicionalmente se establecen como texto en tipo romano. Hay comandos predefinidos en LaTeX estándar para las funciones y operadores más comunes. El paquete `amsmath` amplía suficientemente el conjunto de dichos comandos. La siguiente tabla enumera tanto los comandos "estándar" como los comandos proporcionados por "amsmath". Estos últimos están resaltados en negrita. Aquellos en cursiva pueden tener un subíndice/superíndice en la posición límite cuando se usan en fórmulas mostradas.

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Arccos"](/tex/images/java/tutorial/latex-ams-math-foper-6-1.png) | `\arccos` | !["Arcsin"](/tex/images/java/tutorial/latex-ams-math-foper-6-14.png) | `\arcsin` | !["Arctan"](/tex/images/java/tutorial/latex-ams-math-foper-6-27.png) | `\arctan` |
| !["Arg"](/tex/images/java/tutorial/latex-ams-math-foper-6-2.png) | `\arg` | !["Cos"](/tex/images/java/tutorial/latex-ams-math-foper-6-15.png) | `\cos` | !["Cosh"](/tex/images/java/tutorial/latex-ams-math-foper-6-28.png) | `\cosh` |
| !["Cot"](/tex/images/java/tutorial/latex-ams-math-foper-6-3.png) | `\cot` | !["Coth"](/tex/images/java/tutorial/latex-ams-math-foper-6-16.png) | `\coth` | !["Csc"](/tex/images/java/tutorial/latex-ams-math-foper-6-29.png) | `\csc` |
| !["Deg"](/tex/images/java/tutorial/latex-ams-math-foper-6-4.png) | `\deg` | !["Det"](/tex/images/java/tutorial/latex-ams-math-foper-6-17.png) | *`\det`* | !["Dim"](/tex/images/java/tutorial/latex-ams-math-foper-6-30.png) | `\dim` |
| !["Exp"](/tex/images/java/tutorial/latex-ams-math-foper-6-5.png) | `\exp` | !["Gcd"](/tex/images/java/tutorial/latex-ams-math-foper-6-18.png) | *`\gcd`* | !["Hom"](/tex/images/java/tutorial/latex-ams-math-foper-6-31.png) | `\hom` |
| !["Inf"](/tex/images/java/tutorial/latex-ams-math-foper-6-6.png) | *`\inf`* | !["Injlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-19.png) | ***`\injlim`*** | !["Ker"](/tex/images/java/tutorial/latex-ams-math-foper-6-32.png) | `\ker` |
| !["Lg"](/tex/images/java/tutorial/latex-ams-math-foper-6-7.png) | `\lg` | !["Lim"](/tex/images/java/tutorial/latex-ams-math-foper-6-20.png) | *`\lim`* | !["Liminf"](/tex/images/java/tutorial/latex-ams-math-foper-6-33.png) | *`\liminf`* |
| !["Limsup"](/tex/images/java/tutorial/latex-ams-math-foper-6-8.png) | *`\limsup`* | !["Ln"](/tex/images/java/tutorial/latex-ams-math-foper-6-21.png) | `\ln` | !["Log"](/tex/images/java/tutorial/latex-ams-math-foper-6-34.png) | `\log` |
| !["Max"](/tex/images/java/tutorial/latex-ams-math-foper-6-9.png) | *`\max`* | !["Min"](/tex/images/java/tutorial/latex-ams-math-foper-6-22.png) | *`\min`* | !["Pr"](latex-ams-math-foper-6-35.png) | *`\Pr`* |
| !["Projlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-10.png) | ***`\projlim`*** | !["Sec"](/tex/images/java/tutorial/latex-ams-math-foper-6-23.png) | `\sec` | !["Sin"](/tex/images/java/tutorial/latex-ams-math-foper-6-36.png) | `\sin` |
| !["Sinh"](/tex/images/java/tutorial/latex-ams-math-foper-6-11.png) | `\sinh` | !["Sup"](/tex/images/java/tutorial/latex-ams-math-foper-6-24.png) | *`\sup`* | !["Tan"](/tex/images/java/tutorial/latex-ams-math-foper-6-37.png) | `\tan` |
| !["Tanh"](/tex/images/java/tutorial/latex-ams-math-foper-6-12.png) | `\tanh` | !["Varinjlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-25.png) | ***`\varinjlim`*** | !["Varliminf"](/tex/images/java/tutorial/latex-ams-math-foper-6-38.png) | ***`\varliminf`*** |
| !["Varlimsup"](latex-ams-math-foper-6-13.png) | ***`\varlimsup`*** | !["Varprojlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-26.png) | ***`\varprojlim`*** |  |  |

```tex
\usepackage[fleqn]{amsmath}
\newcommand\abs[1]{\lvert#1\rvert}
\setlength\mathindent{0pt}
% -------------------------------------------------------------------------------
\begin{gather*}
\lim_{x \rightarrow 0} \frac{ \sin^2(x) }{ x^2 } = 1 \\
\varliminf_{n \rightarrow \infty}
\abs{a_{n+1}} / \abs{a_n} = 0 \\
\varinjlim (m_i^\lambda \cdot M)^* \le
\varprojlim_{A/p \rightarrow \lambda(A)}A_p \le 0
\end{gather*}
```

![Funciones y operadores](/tex/images/java/tutorial/latex-ams-math-6-2.png)

A menudo resulta que esta lista no es suficiente. El paquete `amsmath` define un método general para definir nuevos "nombres de operadores".

```tex
\DeclareMathOperator*{cmd}{text}
```

El comando `\DeclareMathOperator` define `cmd` para producir `texto` en la fuente apropiada para los "operadores textuales". Si se espera que el nuevo operador tenga subíndices/superíndices en la posición límite (cuando se usa en pantallas), entonces se debe usar la forma con asterisco `\DeclareMathOperator*`. Además de utilizar la fuente adecuada, `\DeclareMathOperator` establece un buen espacio a cada lado del nombre del operador. El argumento de texto se procesa utilizando un "modo de pseudotexto" en el que
 - El guión se imprime como un guión de texto (no como un signo menos) (consulte `\supminus` en el siguiente ejemplo).
 - El carácter de asterisco `*` se imprime como un asterisco de texto elevado (no centrado).
 - De lo contrario, el texto se procesa en modo matemático para que se ignoren los espacios y se puedan utilizar subíndices, superíndices y otros elementos.


El siguiente ejemplo muestra cómo proporcionar el comando `\meas` para el nuevo nombre de función "meas" (medida) y las funciones del operador `\esssup` y `\supminus` (ambas pueden tener subíndices/superíndices en la posición límite).

```tex
\usepackage[fleqn]{amsmath}
\DeclareMathOperator \meas {meas}
\DeclareMathOperator*\esssup {ess \, sup}
\DeclareMathOperator*\supminus{sup - minus*}
\newcommand\abs [1]{\lvert#1\rvert}
\newcommand\norm[1]{\lVert#1\rVert}
% -------------------------------------------------------------------------------
\begin{gather*}
  \norm{f}_\infty = \esssup_{x \in R^n} \abs{f(x)} \\
  \meas_1 \{ u \in R_+^1 \colon f^*(u)>\alpha \} \\
  \quad \esssup_{x \in R^i} \; \meas_i
  \{ u \in R^n \colon \abs{f(u)} \geq \alpha \} \\
  \quad (\forall \alpha \in \supminus_{f^*} R_{*+})
\end{gather*}
```

![Nuevos nombres de funciones y nombres de operadores](/tex/images/java/tutorial/latex-ams-math-6-3.png)

Estas declaraciones deben aparecer en el preámbulo y es imposible cambiarlas temporalmente. Estrictamente hablando, `\DeclareMathOperator` solo se puede usar para nombres de comandos que no se hayan usado previamente. Para reemplazar un comando existente, primero debe eliminar la definición anterior antes de volver a declararlo.

```tex
\usepackage{amsmath}
%% Low-level TeX needed here to cancel the old the definition of \csc:
\let \csc \relax
\DeclareMathOperator\csc{cosec}
\newcommand\calQ{\mathcal{Q}}
% -------------------------------------------------------------------------------
\[
\varlimsup_{n\to\infty} \calQ (u_n, u_n - u^{\#})
  \ge \csc (\calQ' (u^{\#}))
\]
```

![Redefiniendo el nombre de una función](/tex/images/java/tutorial/latex-ams-math-6-4.png)