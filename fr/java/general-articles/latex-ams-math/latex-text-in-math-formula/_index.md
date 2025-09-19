---
translation: true
template: /templates/_template-java.md
linktitle: Texte dans les formules mathématiques
title: 6. Texte dans les formules mathématiques
weight: 60
url: /java/latex-text-in-math-formula/
keywords: ams-latex, amsmath, opérateurs mathématiques latex, fonctions mathématiques latex, texte mathématique latex
description: L'article concerne l'insertion de texte dans les formules mathématiques et les fonctions et opérateurs mathématiques LaTeX, et comment les définir.
lastmod: "2024-09-27"
---

{{<section overview>}}

## 6.1. La commande `\text`

Pour mettre du texte normal dans les mathématiques, il est préférable d'utiliser la commande `\text` plutôt que des commandes comme `\mathrm`. La commande `\text` garantit que le texte est défini en utilisant la taille de police correcte. La police sera la police de texte utilisée en dehors du matériel mathématique actuel.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![Texte dans les mathématiques](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. Noms des opérateurs

Il est généralement préférable de distinguer les noms des fonctions mathématiques courantes (par exemple *sin* et *log*) et des opérateurs (par exemple *min* et *sup*) des noms de variables définis en italique. Ainsi, ils sont traditionnellement définis sous forme de texte en caractères romains. Il existe des commandes prédéfinies dans LaTeX standard pour les fonctions et opérateurs les plus courants. Le package `amsmath` étend suffisamment l'ensemble de ces commandes. Le tableau suivant répertorie à la fois les commandes « standard » et les commandes fournies par « amsmath ». Ces dernières sont mises en évidence en gras. Ceux définis en italique peuvent avoir un indice/exposant en position limite lorsqu'ils sont utilisés dans les formules affichées.

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

![Fonctions et opérateurs](/tex/images/java/tutorial/latex-ams-math-6-2.png)

Il s’avère souvent que cette liste n’est pas suffisante. Le package `amsmath` définit une méthode générale pour définir de nouveaux "noms d'opérateur".


```tex
\DeclareMathOperator*{cmd}{text}
```

La commande `\DeclareMathOperator` définit `cmd` pour produire du `texte` dans la police appropriée pour les "opérateurs textuels". Si le nouvel opérateur est censé avoir des indices/exposants en position limite (lorsqu'il est utilisé dans les affichages), alors la forme étoilée `\DeclareMathOperator*` doit être utilisée. En plus d'utiliser la police appropriée, `\DeclareMathOperator` définit un bon espacement de chaque côté du nom de l'opérateur. L'argument texte est traité en utilisant un "mode pseudo-texte" dans lequel
 - Le caractère de trait d'union est imprimé sous forme de trait d'union de texte (pas de signe moins) (voir `\supminus` dans l'exemple suivant).
 - L'astérisque `*` est imprimé sous la forme d'un astérisque en relief (non centré).
 - Sinon, le texte est traité en mode mathématique afin que les espaces soient ignorés et que vous puissiez utiliser des indices, des exposants et d'autres éléments.



L'exemple suivant montre comment fournir la commande `\meas` pour le nouveau nom de fonction "meas" (mesure) et les fonctions d'opérateur `\esssup` et `\supminus` (les deux peuvent avoir des indices/exposants en position limite).


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

![Nouveaux noms de fonctions et noms d'opérateurs](/tex/images/java/tutorial/latex-ams-math-6-3.png)

De telles déclarations doivent figurer dans le préambule et il est impossible de les modifier temporairement. À proprement parler, `\DeclareMathOperator` ne peut être utilisé que pour les noms de commandes qui n'ont pas été utilisés auparavant. Pour remplacer une commande existante, vous devez d'abord supprimer la définition précédente avant de la redéclarer.


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

![Redéfinir un nom de fonction](/tex/images/java/tutorial/latex-ams-math-6-4.png)