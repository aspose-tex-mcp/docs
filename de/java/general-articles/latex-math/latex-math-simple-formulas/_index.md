---
translation: true
template: /templates/_template-java.md
linktitle: 1. Einfache Formeln
title: Einfache Formeln | LaTeX-Handbuch
weight: 10
url: /java/latex-math-simple-formulas/
keywords: Latex, Latex-Mathe-Formeln, Latex-Mathematik, Latex-Mathe-Buchstaben, griechische Latex-Buchstaben, Latex-Zahlen
description: In diesem Artikel wird erläutert, wie Sie mit TeX und LaTeX einfache atomare mathematische Ausdrücke für komplexere Formeln erstellen.
lastmod: "2024-09-26"
---

{{<section overview>}}

Die einfachste Formel ist ein einzelner Buchstabe „*x*“ oder eine einzelne Ziffer „4“. Um eine solche Formel in einen LaTeX-Text einzufügen, geben Sie „$x$“ bzw. „$4$“ ein. Alle mathematischen Formeln sind in spezielle mathematische Klammern (`$`) eingeschlossen.

Wenn Sie „$x$“ eingeben, erscheint das „*x*“ kursiv, aber „$2$“ ergibt „2“ in lateinischer Schrift. Im Allgemeinen haben alle Zeichen auf Ihrer Tastatur eine spezielle Interpretation in mathematischen Formeln, entsprechend den normalen Konventionen beim mathematischen Drucken. Buchstaben bezeichnen kursive Buchstaben, während Ziffern und Satzzeichen römische Ziffern und Satzzeichen bezeichnen. Ein Bindestrich (-) bezeichnet ein Minuszeichen. Das linke `$` versetzt TeX in den „Mathe-Modus“ und das rechte entfernt es. Wenn Sie also ein `$` vergessen oder ein zusätzliches `$` eingeben, erhalten Sie wahrscheinlich eine Fehlermeldung, weil TeX verwirrt wird.

TeX übernimmt die meisten eigenen Abstände in mathematischen Formeln. Gleichzeitig werden alle Leerzeichen ignoriert, die Sie zwischen `$` einfügen. Sie können „$(x + y)/(x - y)$“ oder „$(x+y) / (x-y)$“ eingeben, aber beide führen zu einer Formel ![Einzelzeichen tiefgestellt und hochgestellt](/tex/images/java/tutorial/latex-math-1-1.png), bei dem um die Zeichen „+“ und „-“ etwas mehr Platz ist, um das Zeichen „/“ jedoch kein Platz. Sie müssen sich also nicht an die komplizierte Regel der mathematischen Abstände erinnern und können Leerzeichen nach Belieben verwenden. Wenn das Ende von Steuersequenzen (Befehlen) markiert werden muss, werden Leerzeichen weiterhin wie gewohnt verwendet. In den meisten Fällen wird der Abstand von TeX den Erwartungen eines Mathematikers entsprechen; Wenn Sie jedoch die Abstandsregeln von TeX außer Kraft setzen möchten, können Sie dies mit Kontrollsequenzen tun, auf die wir später noch eingehen werden.

Eines der häufigsten Dinge, die Sie in mathematischen Formeln finden können, ist die Verwendung griechischer Buchstaben. In LaTeX können Sie „$\alpha, \beta, \gamma, \delta$“ eingeben, um die ersten vier griechischen Buchstaben zu erhalten. Und „$\Gamma$“ erzeugt beispielsweise einen großen Gamma-Buchstaben. Verwechseln Sie die griechischen Buchstaben „\kappa“ und „\nu“ nicht mit den kursiven Buchstaben *v* und *x*; Das griechische „\phi“ unterscheidet sich von der durchgestrichenen Null namens „\emptyset“. Ein Kleinbuchstabe „\epsilon“ unterscheidet sich vom Symbol, das die Mitgliedschaft in einer Menge angibt. Einige griechische Kleinbuchstaben haben abweichende Formen in kursiven LaTeX-Schriftarten: „$\phi, \theta, \epsilon, \rho$“ ergibt ![Einzelzeichen-Tief- und Hochstellungen](/tex/images/java/tutorial/latex-math-1-2.png), während „$\varphi, \vartheta, \varepsilon, \varrho$` ergibt ![Einzelzeichen-Tief- und Hochstellungen](/tex/images/java/tutorial/latex-math-1-3.png)

Neben griechischen Buchstaben gibt es viele mathematische Symbole wie „ungefähr gleich“ (`$\ approx$`) und „zuordnen zu“ (`$\mapsto$`). Eine vollständige Liste dieser Steuersequenzen und ihrer entsprechenden Symbole finden Sie [hier](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/).