---
translation: true
template: /templates/_template-java.md
linktitle: 9. Angezeigte Gleichungen
title: Angezeigte Gleichungen | LaTeX-Handbuch
weight: 90
url: /java/latex-math-displayed-equations/
keywords: Latex, Latex-Mathe-Formeln, Latex-Mathematik, angezeigte Latex-Mathe-Formel, angezeigte Latex-Mathe-Gleichung, Latex-Mathe-Gleichungsarray, angezeigte Latex-Mathe-Ausrichtung
description: Erfahren Sie, wie Sie mit den von LaTeX bereitgestellten Befehlen große mathematische Formeln oder eine große Anzahl von Formeln anzeigen können.
lastmod: "2024-09-26"
---

{{<section overview>}}

Mittlerweile haben wir den Umgang mit einzelnen Formeln besprochen; Bei Displays handelt es sich jedoch häufig um eine ganze Reihe verschiedener Formeln oder um verschiedene Teile einer riesigen Formel, und es kann eine Herausforderung sein, sie so anzuordnen, dass sie richtig aufeinander abgestimmt sind. Glücklicherweise lassen sich große Displays im Allgemeinen in ein paar einfache Muster einteilen.

### 9.1. Einzeilige Anzeigen

Angezeigte Gleichungen enthalten oft gewöhnlichen Text. Wir haben bereits [besprochen](/tex/{{lang.url-fragment}}java/latex-math-fine-points/#82-non-italic-letters), wie man römische Schrift in Formeln einfügt, ohne den Mathematikmodus zu verlassen, aber der beste Weg, Text in eine Anzeige zu bekommen, besteht darin, ihn in eine „\hbox“ einzufügen. Eigentlich muss es überhaupt keine Mathematik geben. Zum Eingeben von set

![Angezeigter Text ohne jegliche Mathematik](/tex/images/java/tutorial/latex-math-9-1.png)

Sie können „$$\hbox{Angezeigter Text}$$“ sagen. Aber hier ist ein interessanteres Beispiel:

![Text in einer mathematischen Anzeige](/tex/images/java/tutorial/latex-math-9-2.png)

In diesem Fall wurden Formeln und Text wie folgt kombiniert:


```tex
$$\X_n=X_k \qquad\hbox{if and only if}\qquad
     Y_n=Y_k \quad\hbox{and}\quad Z_n=Z_k.$$
```

Wie Sie sehen können, erscheint „\qquad“ um „wenn und nur wenn“, aber ein einzelnes „\quad“ umgibt „und“; Dies unterstreicht die Tatsache, dass die *Y*- und *Z*-Teile der Anzeige enger miteinander verknüpft sind als mit dem *X*-Teil. 

Schauen wir uns die folgende Anzeige an:

![Text in einer mathematischen Anzeige](/tex/images/java/tutorial/latex-math-9-3.png)

Eine Möglichkeit, dies zu spezifizieren, ist


```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all }n\ge0.$$
```

Aber der bessere Weg wäre (siehe zweite Zeile)


```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all $n\ge0$.}$$
```

Ja, das ist der Mathematikmodus innerhalb des horizontalen Modus innerhalb des Anzeige-Mathematikmodus, aber diese Lösung sieht natürlicher aus als die erste.

Wenden wir uns nun den Gleichungsnummern zu, diesen kleinen Beschriftungen, die an der Seite der Anzeigen erscheinen. Wenn Sie tippen


```tex
$$<formula>\eqno<formula>$$
```

TeX zeigt die erste Formel an und fügt außerdem eine Gleichungsnummer (die zweite Formel) am rechten Rand ein. Zum Beispiel,


```tex
$$x^2-y^2 = (x+y)(x-y).\eqno(15)$$
```

wird produzieren

![Gleichungsnummern rechts](/tex/images/java/tutorial/latex-math-9-4.png)

Sie können Gleichungsnummern auch am linken Rand erhalten, indem Sie „\leqno“ verwenden. Zum Beispiel,

```tex
$$x^2-y^2 = (x+y)(x-y).\leqno(15)$$
```

wird produzieren

![Gleichungsnummern links](/tex/images/java/tutorial/latex-math-9-5.png)

Beachten Sie, dass Sie die Gleichungsnummer immer an zweiter Stelle angeben, auch wenn diese links angezeigt wird.

Angezeigte Gleichungen werden unabhängig vom Vorhandensein der Gleichungsnummern zentriert angezeigt. Aber wenn eine Formel groß ist, stellt TeX sicher, dass sie ihre Zahl nicht beeinträchtigt; Die Gleichungsnummer kann sogar einzeln in eine Zeile gestellt werden.

LaTeX bietet auch die Gleichungsumgebung, um Ihre Gleichungen automatisch zu nummerieren. Zum Beispiel Tippen

```tex
\begin{equation}
  f(x)=(x+a)(x+b)
\end{equation}
```

ergibt

![Die Verwendung der Gleichungsumgebung](/tex/images/java/tutorial/latex-math-9-6.png)

Es ist auch möglich, Gleichungen mit `\label` und `\ref` zu beschriften und zu referenzieren. Zum Beispiel,

```tex
\begin{equation} \label{eq:someequation}
  f(x)=(x+a)(x+b)
\end{equation}
this references equation \ref{eq:someequation}.
```

ergibt

![Die Verwendung der Gleichungsumgebung mit einer Bezeichnung und einer Referenz](/tex/images/java/tutorial/latex-math-9-7.png)

### 9.2. Mehrzeilige Anzeigen

Manchmal entspricht eine Anzeige möglicherweise nicht dem einfachen Muster einer einzeiligen Formel mit oder ohne Gleichungsnummer. Für die meisten übrigen Fälle stellt LaTeX spezielle Befehle zur Verfügung.

Mehrzeilige Anzeigen enthalten normalerweise mehrere Gleichungen, die mit ihren „=“-Zeichen aneinandergereiht werden sollten, wie in

![Ein mehrzeiliger Gleichungssatz mit der Array-Umgebung](/tex/images/java/tutorial/latex-math-9-8.png)

Die empfohlene Methode für eine solche Anzeige ist die Verwendung der von LaTeX bereitgestellten `array`-Umgebung:

```tex
$$\begin{array}{rl}
  X_1+\cdots+\X_p&=m,\\
  Y_1+\cdots+\Y_q&=n.}
\end{array}$$
```

Diese Umgebung hilft Ihnen, Ihre Gleichungen als mehrspaltiges (in diesem Fall zwei Spalten) rechteckiges Array darzustellen. Die Zeilen enthalten einzelne Gleichungen, die durch den Befehl „\\“ (ein Zeilenumbruch) getrennt sind. Die linke und rechte Seite jeder Gleichung werden durch das Symbol „&“ getrennt. Es ist nicht erforderlich, dass die letzte Zeile mit „\\“ endet. Die Umgebung verfügt außerdem über ein Argument, das die Ausrichtung in jeder Spalte angibt. Im Beispiel ist der entsprechende Wert „rl“, was bedeutet, dass die linken Seiten der Gleichungen rechtsbündig und die rechten Seiten linksbündig ausgegeben werden.

LaTeX bietet auch die „eqnarray*“-Umgebung, die ähnlich funktioniert, aber um beide Seiten von Gleichungen richtig auszurichten, sind zwei Ausrichtungspunkte erforderlich, und leider weichen die Abstände etwas von den mathematischen Schreibkonventionen ab. Der folgende Code

```tex
\begin{eqnarray*}
  X_1+\cdots+X_p&=&m,\\
  Y_1+\cdots+Y_q&=&n.
\end{eqnarray*}
```

erzeugt die folgende Ausgabe:

![Ein mehrzeiliger Gleichungssatz mit der eqnarray*-Umgebung](/tex/images/java/tutorial/latex-math-9-9.png)

Die „eqnarray“-Umgebung von LaTeX liefert das gleiche Ergebnis, außer dass sie die Gleichungen automatisch nummeriert.

In einer `array`-Umgebung kann eine beliebige Anzahl von Gleichungen vorhanden sein. Das allgemeine Muster ist

```tex
\begin{array}{rl}
  <left-hand side_1>&<right-hand side_1>\\
  <left-hand side_2>&<right-hand side_2>\\
  ...
  <left-hand side_n>&<right-hand side_n>
\end{array}
```

Dabei beginnt jedes „<rechte Seite>“ mit dem Symbol, an dem die Ausrichtung erfolgen soll.

Das Ergebnis der `array`-Umgebung ist eine vertikal zentrierte Box. Dies macht es einfach, eine Formel wie zu erhalten

![Zwei Gruppen von Gleichungen in einer Anzeige](/tex/images/java/tutorial/latex-math-9-10.png)

Sie verwenden die Umgebung `array` einfach zweimal in der Zeile:

```tex
$$\left\{
  \begin{array}{rl}
    \alpha&=f(z)\\ \beta&=f(z^2)\\ \gamma&=f(z^3)
  \end{array}
\right\}\qquad\left\{
  \begin{array}{rl}
    x&=\alpha^2-\beta\\ y&=2\gamma
  \end{array}
\right\}.$$
```

Die nächste Komplexitätsstufe entsteht, wenn Sie mehrere ausgerichtete Gleichungen mit mehreren Gleichungsnummern haben. Oder einige der Zeilen sind möglicherweise nummeriert und andere nicht:

![Beliebig nummeriertes Array von Gleichungen mit Tags auf der rechten Seite](/tex/images/java/tutorial/latex-math-9-11.png)

Leider gibt es selbst in der Umgebung „eqnarray*“ (mit ihrem falschen Abstand) keine Möglichkeit, Gleichungsnummern in einer mehrzeiligen Anzeige manuell anzugeben. Das kann nur das Paket `amsmath`. 
helfen. Der empfohlene Weg, das obige Ergebnis zu erhalten, besteht also darin, Folgendes einzugeben:

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```

Wenn Sie sowohl „\tag“ als auch „\notag“ in einer Zeile der „align“-Umgebung weglassen, wird die Gleichungsnummer automatisch anhand des aktuellen Werts generiert, der im entsprechenden internen Zähler gespeichert ist.

Wenn Sie das Paket `amsmath` mit der Option „leqno“ laden, erscheinen die Gleichungsnummern am linken Rand. Daher

```tex
%% Preamble
\usepackage[leqno]{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```
produziert

![Beliebig nummeriertes Array von Gleichungen mit Tags auf der linken Seite](/tex/images/java/tutorial/latex-math-9-12.png)

Weitere Informationen zum Setzen mathematischer Formeln mithilfe der Funktionen des Pakets `amsmath` finden Sie in diesen [Artikeln](/tex/{{lang.url-fragment}}java/what-is-ams-latex/).

### 9.3. Lange Formeln

Lassen Sie uns nun besprechen, was zu tun ist, wenn eine Formel so lang ist, dass sie nicht in eine einzelne Zeile passt. Angenommen, Sie stoßen auf die Gleichung

![Gekürzte lange Formel, die die Zeile überfüllt](/tex/images/java/tutorial/latex-math-9-13.png)

Du musst es irgendwie auflösen; TeX hat sein Bestes getan, um alles zusammenzudrücken, indem es die Leerzeichen neben den Zeichen „+“ und „-“ auf Null reduziert hat, aber trotzdem ist die Zeile überfüllt.

Versuchen wir, diese Gleichung kurz vor „+7“ zu durchbrechen. Die `array`-Umgebung lässt zu viel Platz rechts vom „=“, wenn Sie sie auf die gleiche Weise wie für mehrzeilige Gleichungen verwenden:

```tex
$$\begin{array}{rl}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1)
\end{array}$$
```

Daher ist es am besten, erneut auf das Paket `amsmath` zurückzugreifen. Aber dieses Mal sollten Sie das Array „align*“ verwenden, da die Gleichungsnummern nicht benötigt werden:

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).
\end{align*}$$
```

Das ergibt

![Lange Formel mit der align*-Umgebung aufgebrochen](/tex/images/java/tutorial/latex-math-9-14.png)

Die Idee besteht darin, eine lange einzeilige Formel wie eine zweizeilige Formel zu behandeln und in der zweiten Zeile „\qquad“ zu verwenden, sodass der zweite Teil der Formel deutlich rechts vom „=“-Zeichen in der ersten Zeile erscheint .
Es ist eigentlich keine leichte Aufgabe, zu entscheiden, wie man lange angezeigte Formeln in Zeilen aufteilt; TeX versucht dies nie, da kein Regelwerk wirklich ausreichend ist. Der Autor eines mathematischen Manuskripts kann im Allgemeinen am besten beurteilen, was zu tun ist, da die Bruchpositionen von subtilen Faktoren mathematischer Darlegungen abhängen. Beispielsweise ist es oft wünschenswert, einen Teil der Symmetrie oder einer anderen Struktur hervorzuheben, die der Formel zugrunde liegt, und solche Dinge erfordern ein solides Verständnis dessen, was genau in dieser Formel vor sich geht.

Dennoch lassen sich einige Faustregeln für den Umgang mit langen Formeln in Darstellungen aufstellen, da es einige Grundsätze gibt, denen der beste mathematische Schriftsetzer tendenziell folgt:

1. Obwohl Formeln innerhalb eines Absatzes immer *nach* binären Operationen und Beziehungen unterbrochen werden, brechen angezeigte Formeln immer *vor* binären Operationen und Beziehungen. Deshalb haben wir die erste Zeile unseres vorherigen Beispiels nicht mit „(2^{34}-1)+“ beendet; Wir haben es mit „(2^{34}-1“ beendet und die zweite Zeile mit „+“ begonnen.

2. Wenn eine Gleichung vor einer binären Operation gebrochen wird, sollte die zweite Zeile mindestens zwei Quadrate rechts von der Stelle beginnen, an der die innerste Unterformel, die diese binäre Operation enthält, in der ersten Zeile beginnt. Zum Beispiel, wenn Sie eine Pause einlegen möchten

```tex
$$\sum_{0<k<n}\left(<formula_1>+<formula_2>\right)$$
```

Beim Pluszeichen zwischen „<Formel_1>“ und „<Formel_2>“ ist es fast zwingend erforderlich, dass das Pluszeichen in der zweiten Zeile etwas rechts von der großen linken Klammer erscheint, die „\left(“ entspricht.

Im gerade betrachteten Beispiel ist besondere Sorgfalt erforderlich, um die Formel in zwei Zeilen aufzuteilen, da die Trennzeichen `\left` und `\right` nicht isoliert verwendet werden können: Sie können nicht nur `\left` in einer Zeile von a haben Formel und nur `\right` in der zweiten. Darüber hinaus möchten Sie, dass die beiden Trennzeichen die gleiche Größe haben, auch wenn sie in unterschiedlichen Zeilen vorkommen. Die beste Lösung besteht normalerweise darin, die Größe des Trennzeichens selbst zu wählen; Sie könnten zum Beispiel tippen

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sum_{0<k<n}\biggl(&<formula_1>\\
    &\qquad+<formula_2>\biggr)
\end{align*}
```

wenn `\bigg`-Trennzeichen am besten sind. Beachten Sie, dass die „&“-Markierungen in diesem Beispiel nicht an „=“-Zeichen vorkommen, sondern lediglich einen Ausrichtungspunkt markieren.

Es gibt eine andere Möglichkeit, lange Formeln aufzuteilen, die manchmal als *zweizeilige* Form bezeichnet wird. Die Idee besteht darin, den ersten Teil der Formel fast linksbündig und den zweiten Teil fast rechtsbündig zu platzieren, wobei „fast bündig“ „ein Quader entfernt“ bedeutet. Somit ist die zuvor betrachtete zweizeilige Form einer langen Sigma-Gleichung

![Zweizeilige Form einer Gleichung](/tex/images/java/tutorial/latex-math-9-15.png)

Um diesen Zweizeileneffekt zu erzielen, geben Sie einfach Folgendes ein:

```tex
$$\displaylines{\quad\sigma(2^{34}-1,2^{35},1)
  =-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1)\hfill{}\cr
\hfill{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).\quad\cr}$$
```

In der zweiten Zeile wurde hier ein zusätzliches `{}` eingegeben, damit TeX weiß, dass es sich bei „+“ um eine binäre Operation handelt. Die zweizeilige Form empfiehlt sich besonders für Gleichungen, die eine lange linke Seite haben; in diesem Fall kommt die Pause im Allgemeinen direkt vor dem =-Zeichen.