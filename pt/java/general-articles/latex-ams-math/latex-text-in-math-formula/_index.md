---
translation: true
template: /templates/_template-java.md
linktitle: Texto em fórmulas de matemática
title: 6. Texto em fórmulas de matemática | Manual de LaTeX
weight: 60
url: /java/latex-text-in-math-formula/
keywords: AMS-LATEX, AMSMATH, Operadores de matemática de LaTeX, funções matemáticas de LaTeX, texto matemático de LaTeX
description: Este artigo discute a inserção de texto em fórmulas de matemática de LaTeX. Ele também descreve funções e operadores matemáticos, bem como o método para defini -los.
lastmod: "2025-06-16"
---

{{<section overview>}}

## 6.1. O comando `\text`

Para colocar o texto normal dentro da matemática, é melhor usar o comando `\text`, em vez de comandos como`\mathrm`. O comando `\text` garante que o texto seja definido usando o tamanho da fonte correto. A fonte será a fonte de texto em uso fora do material de matemática atual.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![Texto dentro da matemática](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. Nomes do operador

Os nomes das funções matemáticas comuns (por exemplo, *sin* e *log*) e operadores (por exemplo, *min* e *sup*) são normalmente preferidos para serem distinguidos de nomes de variáveis ​​definidos em itálico. Então, eles são tradicionalmente definidos como texto no tipo romano. Existem comandos predefinidos no LaTeX padrão para as funções e operadores mais comuns. O pacote `amsmath` estende suficientemente o conjunto desses comandos. A tabela a seguir lista os comandos "padrão" e os comandos fornecidos pelo `amsmath`. Estes últimos são destacados em negrito. Os definidos em itálico podem ter um subscrito/substituto na posição limite quando usado nas fórmulas exibidas.

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

![Funções e operadores](/tex/images/java/tutorial/latex-ams-math-6-2.png)

Muitas vezes, essa lista não é suficiente. O pacote `amsmath` define um método geral para definir novos" nomes de operadores ".


```tex
\DeclareMathOperator*{cmd}{text}
```

O comando `\declaremathoperator` define `cmd` para produzir 'texto' na fonte apropriada para "operadores de texto". Se espera -se que o novo operador tenha subscritos/superestritos na posição limitada (quando usados ​​nos monitores), o formulário estrelado `\declaremathoperator*` deverá ser usado. Além de usar a fonte adequada, `\declaremathoperator` configura um bom espaçamento em ambos os lados do nome do operador. O argumento do texto é processado usando um "modo pseudo-texto" no qual

 - O char do hífen é impresso como um hífen de texto (não um sinal menos) (consulte `\supminus` no próximo exemplo).
 - O Asterisk Char `*` é impresso como um asterisco de texto elevado (não centrado).
 - Caso contrário, o texto é processado no modo de matemática para que os espaços sejam ignorados e você possa usar subscritos, superscripts e outros elementos.

O exemplo a seguir mostra como fornecer o comando `\meas` para o novo nome da função" meas "(medida) e as funções do operador`\esssup` e `\supminus` (ambos podem ter subscritos/superestritos na posição limite).


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

![Novos nomes de funções e nomes de operadores](/tex/images/java/tutorial/latex-ams-math-6-3.png)

Tais declarações devem aparecer no preâmbulo, e é impossível alterá -las temporariamente. Estritamente falando, `\declaremathoperator` pode ser usado apenas para nomes de comando que não foram usados ​​anteriormente. Para substituir um comando existente, você deve primeiro remover a definição anterior antes de redeclará -lo.


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

![Redefinindo um nome de função](/tex/images/java/tutorial/latex-ams-math-6-4.png)