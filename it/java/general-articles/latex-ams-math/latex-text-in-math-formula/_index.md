---
translation: true
template: /templates/_template-java.md
linktitle: Testo nelle formule matematiche
title: 6. Testo nelle formule matematiche
weight: 60
url: /java/latex-text-in-math-formula/
keywords: ams-latex, amsmath, operatori matematici LaTeX, funzioni matematiche LaTeX, testo matematico LaTeX
description: Questo articolo discute l'inserimento di testo nelle formule matematiche LaTeX. Descrive inoltre le funzioni e gli operatori matematici, nonché il metodo per definirli.
lastmod: "2026-03-30"
---

{{<section overview>}}

## 6.1. Il comando `\text`

Per inserire testo normale all'interno di una formula matematica, è preferibile utilizzare il comando `\text` anziché comandi come `\mathrm`. Il comando `\text` garantisce che il testo sia imposto utilizzando la corretta dimensione del font. Il font sarà quello in uso all'esterno dell'attuale materiale matematico.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![Testo all'interno della matematica](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. Nomi degli operatori

I nomi delle funzioni matematiche comuni (ad esempio, *sin* e *log*) e degli operatori (ad esempio, *min* e *sup*) vengono generalmente distinti dai nomi delle variabili che sono scritti in corsivo. Per questo motivo, sono tradizionalmente composti utilizzando il font Romano. Nel LaTeX standard esistono comandi predefiniti per le funzioni e gli operatori più comuni. Il pacchetto `amsmath` estende notevolmente l'insieme di tali comandi. La tabella seguente elenca sia i comandi "standard" che i comandi forniti da `amsmath`. Questi ultimi sono evidenziati in grassetto. Quelli scritti in corsivo possono avere un pedice/apice in posizione di limite quando utilizzati nelle formule visualizzate.

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
| !["Max"](/tex/images/java/tutorial/latex-ams-math-foper-6-9.png) | *`\max`* | !["Min"](/tex/images/java/tutorial/latex-ams-math-foper-6-22.png) | *`\min`* | !["Pr"](/tex/images/java/tutorial/latex-ams-math-foper-6-35.png) | *`\Pr`* |
| !["Projlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-10.png) | ***`\projlim`*** | !["Sec"](/tex/images/java/tutorial/latex-ams-math-foper-6-23.png) | `\sec` | !["Sin"](/tex/images/java/tutorial/latex-ams-math-foper-6-36.png) | `\sin` |
| !["Sinh"](/tex/images/java/tutorial/latex-ams-math-foper-6-11.png) | `\sinh` | !["Sup"](/tex/images/java/tutorial/latex-ams-math-foper-6-24.png) | *`\sup`* | !["Tan"](/tex/images/java/tutorial/latex-ams-math-foper-6-37.png) | `\tan` |
| !["Tanh"](/tex/images/java/tutorial/latex-ams-math-foper-6-12.png) | `\tanh` | !["Varinjlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-25.png) | ***`\varinjlim`*** | !["Varliminf"](/tex/images/java/tutorial/latex-ams-math-foper-6-38.png) | ***`\varliminf`*** |
| !["Varlimsup"](/tex/images/java/tutorial/latex-ams-math-foper-6-13.png) | ***`\varlimsup`*** | !["Varprojlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-26.png) | ***`\varprojlim`*** |  |  |


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

![Funzioni e operatori matematici](/tex/images/java/tutorial/latex-ams-math-6-2.png)

Spesso questo elenco non risulta sufficiente. Il pacchetto `amsmath` definisce un metodo generale per definire nuovi "nomi di operatori".


```tex
\DeclareMathOperator*{cmd}{text}
```

Il comando `\DeclareMathOperator` definisce `cmd` per produrre `text` nel font appropriato per gli "operatori testuali". Se si prevede che il nuovo operatore abbia pedici/apici in posizione di limite (se utilizzato nei display), è necessario utilizzare la forma stellata `\DeclareMathOperator*`. Oltre all'utilizzo del font corretto, `\DeclareMathOperator` imposta una spaziatura adeguata su entrambi i lati del nome dell'operatore. L'argomento di testo viene elaborato utilizzando una "modalità pseudo-testo" in cui:

 - Il carattere del trattino è stampato come un trattino di testo (non un segno meno) (si veda `\supminus` nell'esempio successivo).
 - L'asterisco `*` è stampato come un asterisco di testo rialzato (non centrato).
 - Altrimenti, il testo viene elaborato in modalità matematica in modo che gli spazi vengano ignorati e sia possibile utilizzare pedici, apici e altri elementi.

L'esempio seguente mostra come fornire il comando `\meas` per il nuovo nome di funzione "meas" (measure) e le funzioni dell'operatore `\esssup` e `\supminus` (entrambi possono avere pedici/apici nella posizione di limite).


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

![Esempi di nuovi nomi di funzioni e operatori](/tex/images/java/tutorial/latex-ams-math-6-3.png)

Tali dichiarazioni devono apparire nel preambolo ed è impossibile modificarle temporaneamente. A rigor di termini, `\DeclareMathOperator` può essere utilizzato solo per i nomi di comandi che non sono stati utilizzati in precedenza. Per sostituire un comando esistente, è necessario rimuovere la definizione precedente prima di dichiararlo nuovamente.


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

![Ridefinizione di un nome di funzione](/tex/images/java/tutorial/latex-ams-math-6-4.png)