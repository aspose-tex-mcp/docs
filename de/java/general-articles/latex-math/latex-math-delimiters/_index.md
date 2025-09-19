---
translation: true
template: /templates/_template-java.md
linktitle: Trennzeichen
title: 3. Trennzeichen | LaTeX-Handbuch
weight: 70
url: /java/latex-math-delimiters/
keywords: Latex, Latex-Mathe-Formeln, Latex-Mathematik, Latex-Mathe-Trennzeichen, Latex-Mathe-Klammern, Latex-Mathe-Klammern, Latex-Mathe-Klammern
description: In diesem Artikel wird erläutert, wie Formeln logisch in Unterformeln mit verschiedenen Arten von Trennzeichen unterteilt werden.
lastmod: "2024-09-26"
---

{{<section overview>}}

Wie groß eine mathematische Formel auch sein mag, TeX kennt eine Möglichkeit, einige Symbole groß genug zu machen, damit sie richtig aussehen. Zum Beispiel das Ergebnis einer Eingabe

```tex
$$\sqrt{1+\sqrt{1+\sqrt{1+
            \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+x}}}}}}}$$
```

zeigt eine Vielzahl verfügbarer Radikal- oder Quadratwurzelzeichen:

![Radikale unterschiedlicher Größe](/tex/images/java/tutorial/latex-math-7-1.png)

Die drei größten Zeichen hier sind gleich, mit Ausnahme eines vertikalen Segments, das so oft wie nötig wiederholt wird, um die erforderliche Größe zu erreichen. Gleichzeitig sind die kleineren Zeichen unterschiedliche Zeichen, die den Mathe-Schriftarten von TeX entnommen sind.

Ähnliches geschieht mit Klammern und anderen sogenannten „Trennzeichen“. Solche Symbole sind in der Mathematik wichtig, weil sie visuelle Hinweise auf die zugrunde liegende Struktur komplexer Ausdrücke geben. Mit anderen Worten: Sie begrenzen die Grenzen einzelner Unterformeln. Hier ist die Liste der 22 grundlegenden Trennzeichen, die LaTeX bereitstellt:

![Die 22 grundlegenden Trennzeichen, die in LaTeX definiert sind](/tex/images/java/tutorial/latex-math-7-2.png)

Um eine etwas größere Version eines dieser Symbole zu erhalten, geben Sie einfach `\bigl` oder „\bigr“ als öffnendes bzw. schließendes Trennzeichen ein. Dies erleichtert die Lesbarkeit von Formeln mit verschachtelten Trennzeichen:

![Die Beispiele für die Verwendung von \big delimiters](/tex/images/java/tutorial/latex-math-7-3.png)

Die `\big`-Trennzeichen sind gerade so groß, dass der Unterschied erkennbar ist, und dennoch klein genug, um im Text eines Absatzes verwendet zu werden:

![Die \großen Trennzeichen im Vergleich zu den normalen](/tex/images/java/tutorial/latex-math-7-4.png)

Sie können noch eine Stufe größere, für die Anzeige geeignete Symbole erhalten, wenn Sie `\bigl` und „\Bigr“ anstelle von `\bigl` und „\bigr“ eingeben:

![Die \Großen Trennzeichen](/tex/images/java/tutorial/latex-math-7-5.png)

Diese sind 50 % höher als die Versionen im vorherigen Schritt. Angezeigte Formeln verwenden oft noch höhere Trennzeichen (doppelt so groß wie `\big`). Sie können sie erhalten, indem Sie `\biggl` und „\biggr“ eingeben:

![Die \bigg-Trennzeichen](/tex/images/java/tutorial/latex-math-7-6.png)

Schließlich können Sie die Versionen `\biggl` und „\Biggr“ eingeben, die 2,5-mal so groß sind wie die Trennzeichen `\bigl` und „\bigr“:

![Die \Bigg-Trennzeichen](/tex/images/java/tutorial/latex-math-7-7.png)

LaTeX bietet außerdem die Befehle „\bigm“, „\Bigm“, „\biggm“ und „\Biggm“, um Trennzeichen zu erzeugen, die in der Mitte von Formeln verwendet werden können. Ein solches Trennzeichen verhält sich wie eine Relation, daher fügt TeX auf beiden Seiten etwas Platz ein:

![Trennzeichen in der Mitte von Formeln](/tex/images/java/tutorial/latex-math-7-8.png)

Es ist auch möglich, nur `\big`, `\big`, `\bigg` oder `\bigg` zu sagen, um ein Trennzeichen zu erzeugen, das sich wie eine gewöhnliche Variable verhält. Diese Befehle würden hauptsächlich mit Schrägstrichen und Backslashes verwendet:

![Große gewöhnliche Symbole](/tex/images/java/tutorial/latex-math-7-9.png)

TeX implementiert einen Algorithmus, der ermittelt, wie hoch ein Trennzeichenpaar sein muss, um eine bestimmte Unterformel einzuschließen. Sie können es verwenden, anstatt zu entscheiden, ob ein Trennzeichen `\big` oder `\bigg` oder was auch immer sein soll. Sag es einfach


```tex
\left<delim1><subformula>\right<delim2>
```

und TeX setzt eine Unterformel und setzt die angegebenen Trennzeichen links und rechts. Die Größe der Trennzeichen ist gerade groß genug, um die Unterformel abzudecken:

![Trennzeichen gesetzt durch \left- und \right-Befehle](/tex/images/java/tutorial/latex-math-7-10.png)
Wenn Sie `\left` und `\right` verwenden, müssen sie gepaart werden, genau wie geschweifte Klammern dies bei Gruppen tun. Sie können nicht `\left` in einer Unterformel und `\right` in einer anderen haben. Außerdem können Sie keine Dinge wie „\left(...{...\right...}“ oder „\left(...\begingroup...\right)...\endgroup“ eingeben. Dies liegt daran, dass TeX die Unterformel setzen muss, die zwischen `\left` und `\right` erscheint, bevor es entscheiden kann, wie groß die Trennzeichen sein sollen. Wenn Sie `\left` und `\right` nicht verwenden, tun Sie dies nicht. Die Klammern und Klammern müssen nicht übereinstimmen. Daher können Sie beispielsweise „$[0,1)$“ oder „$)($“ oder sogar „$)$“ eingeben. Und selbst wenn Sie `\left` und `\right` verwenden, müssen die jeweiligen Symbole nicht übereinstimmen, sodass „\left)“ oder „\right(“ keinen Fehler verursachen.

Aber warum sollten Sie sich die Mühe machen, etwas über `\bigl` und „\bigr“ und andere ihrer Art zu lernen, wenn TeX automatisch Größen für `\left` und `\right` berechnen kann? Es gibt mindestens drei Fälle, in denen Sie selbst über die Auswahl der richtigen Trennzeichengröße entscheiden möchten:

(1) Vergleichen Sie einfach die folgenden beiden Formeln:

![\left und \right vs. \bigl und \bigr mit vertikalen Balken](/tex/images/java/tutorial/latex-math-7-11.png)

Tatsächlich war die Verwendung von `\left` und `\right` keine kluge Wahl, da sie nicht herausfinden konnten, welche Trennzeichengröße für die beste Lesbarkeit geeignet wäre.

(2) Andererseits wählen `\left` und `\right` manchmal ein größeres Trennzeichen als gewünscht. Dies geschieht meist, wenn sie einen großen Operator in eine Anzeige einschließen:

![\left und \right vs. \bigl und \bigr mit einer Summation](/tex/images/java/tutorial/latex-math-7-12.png)

Der TeX-Algorithmus bewirkt, dass `\left` und `\right` das `\sum` zusammen mit seinen Grenzen einschließen, aber in besonderen Fällen wie diesem scheint es besser, die Grenzen etwas hängen zu lassen. Daher sind `\bigg`-Trennzeichen hier besser.

(3) Wenn Sie eine große angezeigte Formel setzen müssen, müssen Sie sie in zwei oder mehr Zeilen aufteilen. Und Sie möchten sicherstellen, dass die öffnenden und schließenden Trennzeichen die gleiche Größe haben; Sie können jedoch nicht `\left` in der ersten Zeile und `\right` in der letzten Zeile verwenden, da `\left` und `\right` paarweise vorkommen müssen. Die einzige Lösung besteht darin, beispielsweise `\biggl` in der ersten Zeile und „\Biggr“ in der letzten Zeile zu verwenden.

> Obwohl `\left` und `\right` normalerweise beliebig große Trennzeichen darstellen können, haben Schrägstriche und spitze Klammern eine maximale Größe. Wenn Sie nach wirklich großen Versionen dieser Symbole fragen, erhalten Sie die größten verfügbaren.

Sie können auch einen Trick verwenden, der ein sogenanntes Null-Trennzeichen (Leerzeichen) erzeugt. Sie benötigen ein solches Trennzeichen, wenn Sie eine Formel setzen müssen, die optisch nur ein großes Trennzeichen enthält. Zum Beispiel,

![Ein Nulltrennzeichen in Groß- und Kleinschreibung](/tex/images/java/tutorial/latex-math-7-13.png)

hat '{', aber kein '}'. Es kann durch eine Konstruktion der Form hergestellt werden


```tex
$$|x|=\left\{ ... \right.$$ 
```

wobei „\right.“ das rechte Nulltrennzeichen generiert.

LaTeX bietet außerdem noch einige weitere Trennzeichen, die jedoch nicht im Basissatz von 22 aufgeführt sind, da sie etwas Besonderes sind. Die Befehle „\arrowvert“, „\Arrowvert“ und „\bracevert“ erzeugen Trennzeichen, die aus den wiederholbaren Teilen der vertikalen Pfeile, doppelten vertikalen Pfeile bzw. großen Klammern bestehen, ohne Pfeilspitzen oder die geschweiften Teile der Klammern. Sie liefern ähnliche Ergebnisse wie „\vert“ und „\Vert“, sind jedoch von mehr Leerraum umgeben und haben eine andere Gewichtung. Es gibt auch „\lgroup“ und „\rgroup“, die aus geschweiften Klammern ohne Mittelteile bestehen; und „\lmoustache“ und „\rmoustache“, die die obere und untere Hälfte großer Klammern erzeugen. Hier sind Anzeigen mit den Versionen `\big` und `\bigg` von „\vert“, „\Vert“ und diesen sieben speziellen Trennzeichen:

![Zusätzliche Trennzeichen von LaTeX](/tex/images/java/tutorial/latex-math-7-14.png)

Sie werden feststellen, dass „\lgroup“ und „\rgroup“ eher wie fette Klammern sind, mit schärferen Krümmungen an den Ecken; Dies macht sie für bestimmte große Displays attraktiv. Beachten Sie, dass Sie sie nicht genau wie Klammern verwenden können, da sie nur in den Größen `\big` und mehr verfügbar sind.