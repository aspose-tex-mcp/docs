---
translation: true
template: /templates/_template-java.md
linktitle: Text in mathematischen Formeln
title: 6. Text in mathematischen Formeln
weight: 60
url: /java/latex-text-in-math-formula/
keywords: ams-latex, amsmath, Latex-Mathe-Operatoren, Latex-Mathe-Funktionen, Latex-Mathe-Text
description: Im Artikel wird das Einfügen von Text in LaTeX-Formeln, mathematische Funktionen und Operatoren sowie die Methode zu deren Definition erläutert.
lastmod: "2024-09-26"
---

{{<section overview>}}

## 6.1. Der Befehl „\text“.

Um normalen Text in die Mathematik einzufügen, ist es besser, den Befehl „\text“ zu verwenden, als Befehle wie `\mathrm`. Der Befehl „\text“ stellt sicher, dass der Text mit der richtigen Schriftgröße gesetzt wird. Die Schriftart ist die Textschriftart, die außerhalb des aktuellen Mathematikmaterials verwendet wird.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![Text innerhalb der Mathematik](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. Betreibernamen

Die Namen gängiger mathematischer Funktionen (z. B. *sin* und *log*) und Operatoren (z. B. *min* und *sup*) werden normalerweise bevorzugt, um sie von kursiv geschriebenen Variablennamen zu unterscheiden. Daher werden sie traditionell als Text in lateinischer Schrift gesetzt. Im Standard-LaTeX gibt es vordefinierte Befehle für die gängigsten Funktionen und Operatoren. Das Paket `amsmath` erweitert den Satz solcher Befehle ausreichend. In der folgenden Tabelle sind sowohl die „Standard“-Befehle als auch die von `amsmath` bereitgestellten Befehle aufgeführt. Letztere sind fett hervorgehoben. Bei Verwendung in angezeigten Formeln können kursiv geschriebene Zeichen an der Grenzposition einen tiefgestellten/hochgestellten Index haben.

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

![Funktionen und Operatoren](/tex/images/java/tutorial/latex-ams-math-6-2.png)

Es stellt sich oft heraus, dass diese Liste nicht ausreicht. Das Paket `amsmath` definiert eine allgemeine Methode zum Definieren neuer „Operatornamen“.


```tex
\DeclareMathOperator*{cmd}{text}
```

Der Befehl „\DeclareMathOperator“ definiert „cmd“, um „Text“ in der entsprechenden Schriftart für „Textoperatoren“ zu erzeugen. Wenn erwartet wird, dass der neue Operator tiefgestellte/hochgestellte Zeichen an der Grenzposition hat (bei Verwendung in Anzeigen), sollte die Sternform „\DeclareMathOperator*“ verwendet werden. Zusätzlich zur Verwendung der richtigen Schriftart richtet „\DeclareMathOperator“ einen guten Abstand auf beiden Seiten des Operatornamens ein. Das Textargument wird im „Pseudotextmodus“ verarbeitet

 - Das Bindestrichzeichen wird als Textbindestrich (kein Minuszeichen) gedruckt (siehe „\supminus“ im nächsten Beispiel).
 - Das Sternchenzeichen „*“ wird als erhabenes Textsternchen (nicht zentriert) gedruckt.
 - Andernfalls wird der Text im Mathematikmodus verarbeitet, sodass Leerzeichen ignoriert werden und Sie tiefgestellte, hochgestellte und andere Elemente verwenden können.

Das folgende Beispiel zeigt, wie Sie den Befehl „\meas“ für den neuen Funktionsnamen „meas“ (Maßnahme) und die Operatorfunktionen „\esssup“ und „\supminus“ bereitstellen (beide dürfen an der Endposition tiefgestellt/hochgestellt sein).


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

![Neue Funktionsnamen und Operatornamen](/tex/images/java/tutorial/latex-ams-math-6-3.png)

Solche Erklärungen müssen in der Präambel erscheinen und dürfen nicht vorübergehend geändert werden. Streng genommen kann „\DeclareMathOperator“ nur für Befehlsnamen verwendet werden, die zuvor noch nicht verwendet wurden. Um einen vorhandenen Befehl zu ersetzen, müssen Sie zunächst die vorherige Definition entfernen, bevor Sie ihn erneut deklarieren.


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

![Funktionsnamen neu definieren](/tex/images/java/tutorial/latex-ams-math-6-4.png)