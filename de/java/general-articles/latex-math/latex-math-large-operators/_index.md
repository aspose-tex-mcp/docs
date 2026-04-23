---
translation: true
template: /templates/_template-java.md
linktitle: Große Betreiber
title: 6. Große Betreiber
weight: 60
url: /java/latex-math-large-operators/
keywords: Latex, Latex-Mathe-Formeln, Latex-Mathematik, große Latex-Mathe-Operatoren, Latex-Summe, Latex-Integral
description: In diesem Artikel wird erläutert, wie man mathematische Formeln erstellt, die große Operatoren wie Summierung und Integration mit TeX und LaTeX enthalten.
lastmod: "2024-09-26"
---

{{<section overview>}}

In der Mathematik gibt es Symbole, die beispielsweise die Operationen Summation oder Integration bezeichnen. Sie werden große Operatoren genannt und Sie geben sie genauso ein wie gewöhnliche Symbole und Buchstaben. Der Unterschied besteht darin, dass TeX im Anzeigestil ein größeres Symbol für den großen Operator wählt als im Textstil.

![Summierung und Integration ohne Hoch-/Tiefstellungen](/tex/images/java/tutorial/latex-math-6-1.png)

Eine angezeigte `\sum` erfolgt in der Regel mit Limits, also mit Unterformeln, die darüber und darunter erscheinen sollen. Grenzwerte sollten so eingegeben werden, als wären sie tiefgestellte und hochgestellte Zeichen.
`$$\sum_{n=1}^m$$` oder `$$\sum^m_{n=1}$$` produzieren beide

![Summierung mit Grenzen](/tex/images/java/tutorial/latex-math-6-2.png)

Die normalen Konventionen des mathematischen Schriftsatzes gehen davon aus, dass die obige Formel geändert werden sollte

![Summierung ohne Grenzen](/tex/images/java/tutorial/latex-math-6-3.png)

(d. h. ohne Einschränkungen), wenn es im Text und nicht in einer Anzeige auftritt. Und TeX folgt diesen Konventionen.

Hochgestellte und tiefgestellte Zeichen auf dem Integrationszeichen sind auch im Anzeigestil nicht als Begrenzung festgelegt:

![Einbindung in Text und in eine Anzeige](/tex/images/java/tutorial/latex-math-6-4.png)

Das Festlegen von tiefgestellten und hochgestellten Zeichen als Grenzwerte sorgt für ein besseres Erscheinungsbild, wenn die Unterformeln komplex sind, nimmt jedoch mehr Platz auf der Seite ein. Sie können TeX zwingen, die Formel auf diese Weise zu verarbeiten, indem Sie `\limits` direkt nach `\int` oder `\sum` oder einen anderen Operator eingeben, unabhängig davon, welcher Stil in der Unterformel verwendet wird. Andererseits sind Begrenzungen der angezeigten Summenzeichen manchmal nicht wünschenswert. Sie können die Konvention von TeX ändern, indem Sie `\nolimits` direkt nach dem großen Operator eingeben.

![Grenzwerte und keine Grenzen für Summation und Integration erzwingen](/tex/images/java/tutorial/latex-math-6-5.png)

Wenn Sie `\nolimits\limits` sagen (einige Makros wie `\int` geben beispielsweise `\nolimits` an), hat der letzte Befehl Vorrang. Mit dem Befehl `\displaylimits` können Sie zu den normalen Konventionen von TeX wechseln; d. h. die Grenzwerte werden nur in den Stilen *D* und *D'* angezeigt.

Wenn Sie mehr als eine Zeile mit Grenzwerten unter einen großen Operator setzen müssen, können Sie dies mit „\atop“ tun. Die richtige Art, die folgende Formel einzugeben, ist 

```tex
$$\sum_{\scriptstyle0\le i\le m\atop\scriptstyle0<j<n}P(i,j)$$.
```

![Mehrzeilige Grenzen unter dem Summenzeichen](/tex/images/java/tutorial/latex-math-6-6.png)

Hier ist der Befehl `\scriptstyle` erforderlich, da sonst beide Zeilen des Limits in Scriptscript-Größe vorliegen würden, was zu klein ist. Dies ist ein weiterer seltener Fall, in dem die Stilregeln von TeX überschrieben werden müssen.