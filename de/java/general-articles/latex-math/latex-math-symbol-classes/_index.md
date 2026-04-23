---
translation: true
template: /templates/_template-java.md
linktitle: Verschiedene Zeichen in mathematischen Formeln
title: 4. Bedeutung verschiedener Zeichen in mathematischen Formeln
weight: 40
url: /java/latex-math-symbol-classes/
keywords: Latex, Latex-Mathe-Formeln, Latex-Mathematik, Latex-Mathe-Symbole, Latex-Mathe-Variablen, Latex-Mathe-Binäroperationen, Latex-Mathe-Beziehungen, Latex-Mathe-Akzente
description: In diesem Artikel geht es um die Einteilung der TeX-Mathesymbole in Klassen und die Bedeutung dieser Klassen in der Mathematik.
lastmod: "2024-09-26"
---

{{<section overview>}}

Die 52 Buchstaben (`A` bis `Z` und `a` bis `z`) bezeichnen kursive Symbole, die ein Mathematiker „Variablen“ nennen würde. TeX nennt sie einfach „gewöhnliche Symbole“, weil sie den Großteil der mathematischen Formeln ausmachen. LaTeX behandelt auch die folgenden 18 Zeichen

`0 1 2 3 4 5 6 7 8 9 ! ? . | ` @ "``

als gewöhnliche Symbole, was bedeutet, dass kein zusätzlicher Leerraum eingefügt wird, wenn diese Symbole nebeneinander oder neben Buchstaben auftreten. Im Gegensatz zu den Buchstaben bleiben diese 18 Zeichen in Formeln in lateinischer Schrift.

Die drei Zeichen `+`, `-` und `*` werden „binäre Operationen“ genannt, da sie zwei Teile der Formel bearbeiten. Das Sternchen (*) ist selten, verhält sich aber auch wie eine binäre Operation. Hier sind einige Beispiele für binäre Textsatzoperationen, wenn sie neben gewöhnlichen Symbolen erscheinen:

![Binäre Operationen](/tex/images/java/tutorial/latex-math-4-1.png)

TeX behandelt `/` nicht als binäre Operation, da dies zu falschen Abständen in Formeln wie `$1/2$` führen würde. Daher behandelt TeX `/` als gewöhnliches Symbol.

Hier sind einige weitere Beispiele für binäre Operationen:

![Komplexere binäre Operationen](/tex/images/java/tutorial/latex-math-4-2.png)

Im Übrigen werden binäre Operationen als gewöhnliche Symbole behandelt, wenn sie nicht zwischen zwei Größen auftreten, mit denen sie operieren können. Daher wird in Fällen wie den folgenden kein zusätzliches Leerzeichen neben +, - und * eingefügt:

![Binäroperation als gewöhnliche Symbole](/tex/images/java/tutorial/latex-math-4-3.png)

Die folgenden Beispiele zeigen, dass binäre Operationen als gewöhnliche Symbole in hoch- und tiefgestellten Zeichen verwendet werden können:

![Binäroperation als gewöhnliche Symbole in hochgestellten und tiefgestellten Zeichen](/tex/images/java/tutorial/latex-math-4-4.png)

LaTeX behandelt die vier Zeichen `=`, `<`, `>`, und `:` als „Beziehungen“, da sie eine Beziehung zwischen zwei Größen ausdrücken. Solche Beziehungen haben eine etwas andere Bedeutung als binäre Operationen und die Symbole werden etwas anders gesetzt:

![Beziehungen](/tex/images/java/tutorial/latex-math-4-5.png)

Die beiden Zeichen `,` (Komma) und `;` (Semikolon) werden in Formeln als Satzzeichen behandelt, was bedeutet, dass TeX nach ihnen etwas mehr Leerzeichen einfügt, aber nicht davor.

![Satzzeichen](/tex/images/java/tutorial/latex-math-4-6.png)

Es ist nicht üblich, nach einem `.` zusätzliche Leerzeichen einzufügen. (Punkt) in Formeln, daher behandelt TeX einen Punkt als gewöhnliches Symbol. Wenn Sie möchten, dass das Zeichen `:` ein Satzzeichen statt einer Beziehung ist, nennen Sie es einfach `\colon`. Und wenn Sie möchten, dass ein Komma wie ein gewöhnliches Symbol behandelt wird, setzen Sie es einfach in geschweifte Klammern. TeX behandelt alles in geschweiften Klammern als gewöhnliches Symbol.

![Doppelpunkt als Satzzeichen und Komma als gewöhnliches Symbol](/tex/images/java/tutorial/latex-math-4-7.png)

Die Zeichen `(` und `[` werden „Eröffnungen“ genannt, während `)` und `]` „Abschlüsse“ genannt werden. Sie verhalten sich ähnlich wie gewöhnliche Symbole, helfen TeX jedoch bei der Entscheidung, wann eine binäre Operation nicht wirklich binär verwendet wird.

Schließlich reserviert LaTeX die anderen 10 Zeichen:

`\ $ % # & ~ { } _ ^`

Sie können sie nicht im Mathematikmodus verwenden. Obwohl `{` und `}` die Gruppierung angeben, können die Befehle `\{` und `\}` verwendet werden, um `{` als Eröffnung und `}` als Abschluss zu erhalten.

Die Sonderzeichen `^` und `_` sollten nur in Formeln verwendet werden. Umgekehrt dürfen die Namen von mathematischen Symbolen wie `\alpha` und `\approx` sowie die Befehle für mathematische Operationen wie `\overline` nicht im normalen Text erscheinen. Außerdem ist eine Leerzeile oder `\par` im Mathematikmodus nicht zulässig.

Mathematiker verwenden auch gerne Akzente über Buchstaben, um Beziehungen zwischen mathematischen Objekten effektiv anzuzeigen. Außerdem wird die Anzahl der verfügbaren Symbole erheblich erweitert, ohne dass sich die Anzahl der erforderlichen Schriftarten erhöht. Mathematische Akzente unterscheiden sich etwas von den Akzenten, die in gewöhnlichen Texten verwendet werden. Der Abstand ist nicht derselbe; TeX folgt speziellen Regeln für Akzente in Formeln, damit die beiden Arten von Akzenten nicht miteinander verwechselt werden. LaTeX bietet die folgenden mathematischen Akzente:

![Akzente](/tex/images/java/tutorial/latex-math-4-8.png)

Die ersten neun davon heißen `\^`, `\v`, `\~`, `\'`, ``\` ``, `\.`, `\"`, `\u` und `\=` ist jeweils ein Akzent, der nur in Formeln vorkommt, wenn Sie versuchen, `\^` oder `\v` usw. zu verwenden. in Formeln oder wenn Sie versuchen, `\hat` oder `\check` usw. in normalem Text zu verwenden.

Normalerweise ist es am besten, Makros für Buchstaben mit Akzent zu definieren, die Sie häufig benötigen. Sie können setzen

```tex
\def\Ahat{{\hat A}}
\def\chat{{\hat c}}
\def\scheck{{\check s}}
```

am Anfang einer LaTeX-Datei. Dies erspart Ihnen viele Tastenanschläge und erleichtert das Lesen der Datei.

Wenn die Buchstaben *i* und *j* in mathematischen Formeln akzentuiert werden, sollten Sie punktlose Symbolbasen verwenden, die `\imath` und `\jmath` heißen. Ein Artikel, der die gehassten i und j verwendet, könnte also mit den folgenden Definitionen beginnen:

```tex
\def\ihat{{\hat\imath}}
\def\jhat{{\hat\jmath}}
```

Es ist möglich, jeder Unterformel mathematische Akzente zu setzen. Dies hat jedoch normalerweise keinen großen Sinn, da TeX lediglich den Schwerpunkt auf die gesamte Unterformel legt. Insbesondere behält ein `\bar`-Akzent immer die gleiche Größe; Es ist nicht wie `\overline`, das mit der Formel darunter wächst. Manche Leute bevorzugen die längere Zeile von `\overline`, selbst wenn es sich um einen einzelnen Buchstaben handelt. Allerdings bietet LaTeX zwei Akzente, die wachsen; sie heißen `\widehat` und `\widetilde`. Schauen wir uns nun die Fallbeispiele an, die in diesem Absatz besprochen werden.

![Breite Akzente](/tex/images/java/tutorial/latex-math-4-9.png)

Das letzte Beispiel zeigt die maximal verfügbare Größe.