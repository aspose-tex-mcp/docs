---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX Tiefgestellt und tiefgestellt
title: 2. LaTeX Index und Index | LaTeX-Handbuch
weight: 20
url: /java/latex-math-subscripts-superscripts/
keywords: Latex, Latex-Mathe-Formeln, Latex-Mathematik, Latex-Mathe-Indizes, Latex-Mathe-Hochstellungen
description: In diesem Artikel wird erläutert, wie Sie mit TeX und LaTeX mathematische Formeln erstellen, die tiefgestellte und hochgestellte Zeichen enthalten.
lastmod: "2024-09-26"
---

{{<section overview>}}


## Einführung in die hochgestellten und tiefgestellten Zeichen von LaTeX

**Hochgestellt** ist ein kleines Zeichen oder Symbol, das leicht über der Grundlinie des Textes positioniert ist.  Beispielsweise ist im Ausdruck „x²“ die „2“ ein hochgestellter Index.

**Tiefgestellt** ist ein kleines Zeichen oder Symbol, das etwas unterhalb der Grundlinie des Textes positioniert ist. Beispielsweise ist in der chemischen Formel für Wasser „H₂O“ die „2“ ein tiefgestellter Index.

## So schreiben Sie tiefgestellte/hochgestellte Zeichen in LaTeX

Versuchen wir nun, aus einfachen Formeln komplexere Formeln zu erstellen. Erstens können Sie hochgestellte und tiefgestellte Zeichen erhalten, indem Sie „^“ und „_“ verwenden, wie im folgenden Beispiel gezeigt:

![Einzelzeichen-Tief- und Hochstellungen](/tex/images/java/tutorial/latex-math-2-1.png)

Beachten Sie, dass „^“ und „_“ nur für das nächste Zeichen gelten. Wenn Sie einen komplexeren tiefgestellten oder hochgestellten Index wünschen, schließen Sie ihn einfach in geschweifte Klammern ein:

![Mehrstellige tiefgestellte und hochgestellte Zeichen](/tex/images/java/tutorial/latex-math-2-2.png)

Die geschweiften Klammern in diesen Beispielen geben „Unterformeln“ an – einfachere Teile einer größeren Formel. TeX erstellt für jede Unterformel ein Kästchen und behandelt dieses Kästchen, als wäre es ein einzelnes Symbol. Auch Klammern erfüllen ihren üblichen Zweck der Gruppierung.

Es ist illegal, „$x^y^z$“ oder „$x_y_z$“ einzugeben. TeX wird sich über einen „doppelten tiefgestellten“ oder „doppelten hochgestellten“ Wert beschweren. Sie müssen klarer machen, was Sie wollen, indem Sie entweder „$x^{y^z}$“ oder „$x^{yz}$“ oder „$x_{y_z}$“ oder „$x_{yz}“ eingeben. $`.

Ein hochgestellter oder tiefgestellter Index nach einem Zeichen gilt nur für dieses Zeichen. Wenn Sie jedoch einer Unterformel folgen, gilt dies für die gesamte Unterformel und wird entsprechend erhöht oder verringert.

![Tiefgestellte und hochgestellte Zeichen auf einem einzelnen Symbol und auf einer Unterformel](/tex/images/java/tutorial/latex-math-2-3.png)

In der ersten Formel sind „^3“ und „^4“ hochgestellte Zeichen auf den rechten Klammern, die ihnen unmittelbar vorangehen, aber in der zweiten Formel sind sie hochgestellte Zeichen auf den Unterformeln, die in geschweifte Klammern eingeschlossen sind. Die erste Version ist vorzuziehen, da sie einfacher zu tippen und ebenso leicht zu lesen ist.

## Tiefstellen oder hochstellen einer leeren Unterformel schreiben

Manchmal müssen Sie möglicherweise eine leere Unterformel tiefstellen oder hochstellen, um eine eher seltene Notation wie *<sub>2</sub>F<sub>3</sub>* zu erzeugen. Am besten geben Sie dazu „${}_2F_3$“ oder „${_2}F_3$“ oder „${_2F_3}$“ ein.

Sie können auch gleichzeitige „tiefgestellte Zeichen“ verwenden und diese in beliebiger Reihenfolge angeben:

![Gleichzeitige tiefgestellte Zeichen](/tex/images/java/tutorial/latex-math-2-4.png)

Diese gleichzeitigen „tiefgestellten Zeichen“ werden übereinander positioniert. Bei manchen Buchstaben wird der Index jedoch nach links verschoben; und für einige dieser Briefe ziemlich deutlich. Vergleichen Sie die folgenden beiden Formeln:

![Gleichzeitige Ausrichtung tiefgestellter Zeichen](/tex/images/java/tutorial/latex-math-2-5.png)

Wenn Sie also möchten, dass sowohl der tiefgestellte als auch der hochgestellte Index ausgerichtet sind, können Sie den in der zweiten Version gezeigten Trick verwenden. Es nutzt wiederum eine leere Unterformel aus.

## Prime in LaTeX schreiben

Das nächste, was in mathematischen Formeln häufig vorkommt, ist das Primzahlsymbol. LaTeX bietet den Befehl „\prime“, der selbst ein Primsymbol in der Größe eines normalen Buchstabens erzeugt. Daher sollten Sie es nie außer hoch- oder tiefgestellt verwenden. Sie können aber auch einfach „“ statt „^\prime“ und „“ statt „^\prime\prime“ usw. eingeben.

![Primzahlen](/tex/images/java/tutorial/latex-math-2-6.png)

## Doppelt hochgestelltes LaTeX

In LaTeX können Sie doppelt hochgestellte Zeichen schreiben, indem Sie den gesamten hochgestellten Ausdruck in geschweifte Klammern {} einschließen. Hier ist ein Beispiel: „x^{a^b}“.

## Doppelter Index LaTeX

In LaTeX können Sie doppelte Indizes auf ähnliche Weise schreiben, indem Sie den gesamten Indexausdruck in geschweifte Klammern {} einschließen. Hier ist ein Beispiel: „X_{i_{j}}“.