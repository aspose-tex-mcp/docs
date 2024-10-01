---
translation: true
template: /templates/_template-java.md
linktitle: Erweiterbare und anpassbare Symbole
title: 5. Erweiterbare und anpassbare Symbole | LaTeX-Handbuch
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: ams-latex, amsmath, amsxtra, Latex-Mathe-Operatoren, Latex-Mathe-Trennzeichen, Latex-Mathe-Klammern, Latex-Mathe-Klammern, Latex-Mathe-Akzente
description: In diesem Artikel werden LaTeX-Funktionen im Zusammenhang mit der Arbeit mit erweiterbaren und anpassbaren mathematischen Symbolen erläutert.
lastmod: "2024-09-26"
---

{{<section overview>}}

In LaTeX gibt es bestimmte Funktionen, die es ermöglichen, Strukturen zu erstellen, die auf jede gewünschte Größe wachsen können. Der mathematische Schriftsatz benötigt eine solche Variabilität dringend. Wir werden einige Aspekte davon in diesem Artikel besprechen. Alle in diesem Abschnitt behandelten Befehle (sofern nicht anders angegeben) werden von Standard-LaTeX bereitgestellt.


## 5.1. Ellipse...

Das Paket `amsmath` ersetzt (in fast allen Fällen) alle `\ldots`, `cdots` usw. aus Standard-LaTeX durch den einzelnen `\dots`-Befehl. Sowohl die vertikale Position der Ellipse als auch der Raum um sie herum werden automatisch abhängig von der Art des Symbols nach `\dots` ausgewählt. Wenn das nächste Symbol beispielsweise ein Pluszeichen ist, werden die Punkte zentriert angezeigt. Wenn es sich um ein Komma handelt, fallen sie auf die Grundlinie. Es sind immer drei Punkte, aber der Abstand ist variabel.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![Ellipse mit automatisch ermitteltem Abstand](/tex/images/java/tutorial/latex-ams-math-5-1.png)

Wenn die Punkte jedoch zufällig am Ende einer Formel erscheinen, ist das nächste Objekt etwas wie `\end` oder `\)` oder `$` und es gibt LaTeX keinen Hinweis auf die Positionierung der Punkte. In einem solchen Fall müssen Sie helfen, indem Sie `\dotsc` für Punkte gefolgt von Kommas, `\dotsb` für Punkte gefolgt von *Binäroperator* oder *Relationssymbol*, `\dotsm` für Punkte gefolgt von Multiplikationspunkten, `\dotsi` für Punkte, denen Integrale folgen, oder `\dotso` in jedem anderen Fall.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![Auslassungspunkte am Ende einer Formel](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2. Symbole, die horizontal erweiterbar sind

Grundsätzlich ermöglicht LaTeX die Einrichtung eines beliebigen mathematischen Akzentbefehls, um die entsprechende Glyphe aus einem Bereich von Breiten zu erzeugen, sofern diese von den verfügbaren Schriftarten bereitgestellt werden. Im Standard-LaTeX gibt es jedoch nur zwei solcher Befehle: `\widehat` und `\widetilde`.

Im nächsten Beispiel demonstrieren wir die Verwendung einiger Befehle, die Konstrukte erzeugen, die den oben genannten erweiterbaren Akzenten ähneln. Sie alle erzeugen zusammengesetzte Symbole des Mathematikunterrichts *Gewöhnlich*.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
\widehat {\psi_\delta(t) E_t h}
&= \widetilde {\psi_\delta(t) E_t h} \\
\overline {\psi_\delta(t) E_t h}
&= \underline {\psi_\delta(t) E_t h} \\
\overbrace {\psi_\delta(t) E_t h}
&= \underbrace {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\
\overrightarrow {\psi_\delta(t) E_t h} 
&= \overleftarrow {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\[-3pt]
& & & \text{without \textsf{amsmath}} \\
\underrightarrow {\psi_\delta(t) E_t h}
&= \underleftarrow {\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}} \\
\overleftrightarrow {\psi_\delta(t) E_t h}
&=\underleftrightarrow{\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}}
\end{align*}
```

![Erweiterbare Akzente](/tex/images/java/tutorial/latex-ams-math-5-3.png)

„Stil ändern“ bedeutet hier, dass das verwendete Symbol vom verwendeten mathematischen Stil beeinflusst wird, sodass es beispielsweise bei der Verwendung in Brüchen oder tiefgestellten/hochgestellten Zeichen richtig aussieht. Diejenigen, die den Stil nicht ändern, werden nur auf der obersten Ebene der angezeigten Formeln richtig angezeigt.

## 5.3. Symbole, die vertikal erweiterbar sind

Die vertikale Erweiterbarkeit ist viel größer. In der folgenden Tabelle sind alle vertikal erweiterbaren Symbole aufgeführt.

*Vertikal erweiterbare Symbole*

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Klammern"](/tex/images/java/tutorial/latex-ams-math-delim-5-1.png) | `(` `)` | !["Geschweifte Klammern öffnen"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\{` `\}` | !["Doppelte vertikale Striche"](/tex/images/java/tutorial/latex-ams-math-delim-5-18.png) | *`\lVert` `\rVert`* |
| !["Winkelklammern"](/tex/images/java/tutorial/latex-ams-math-delim-5-2.png) | `\langle` `\rangle` | !["Geschweifte Klammern schließen"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\lbrace` `\rbrace` | !["Einzelne vertikale Striche"](/tex/images/java/tutorial/latex-ams-math-delim-5-19.png) | *`\lvert` `\rvert`* |
| !["Lgroup und Rgroup"](/tex/images/java/tutorial/latex-ams-math-delim-5-3.png) | `\lgroup` `\rgroup` | !["Eckige Klammern öffnen"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `[` `]` | !["Vertikaler Balken"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `|` |
| !["Schnurrbärte"](/tex/images/java/tutorial/latex-ams-math-delim-5-4.png) | `\lmoustache` `\rmoustache` | !["Eckige Klammern schließen"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `\lbrack` `\rbrack` | !["Vertikaler Balken"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\vert` |
| !["Pfeil nach unten"](/tex/images/java/tutorial/latex-ams-math-delim-5-5.png) | `\Downarrow` | !["Deckenhalterungen öffnen"](/tex/images/java/tutorial/latex-ams-math-delim-5-13.png) | `\lceil` `\rceil` | !["Pfeil, senkrechter Balken"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\arrowvert` |
| !["Pfeil nach oben"](/tex/images/java/tutorial/latex-ams-math-delim-5-6.png) | `\Uparrow` | !["Bodenhalterungen schließen"](/tex/images/java/tutorial/latex-ams-math-delim-5-14.png) | `\lfloor` `\rfloor` | !["Vertikaler Balken mit Klammern"](/tex/images/java/tutorial/latex-ams-math-delim-5-21.png) | `\bracevert` |
| !["Pfeil nach oben/unten"](/tex/images/java/tutorial/latex-ams-math-delim-5-7.png) | `\Updownarrow` | !["Doppelte Klammern öffnen"](/tex/images/java/tutorial/latex-ams-math-delim-5-15.png) | ***`\llbracket` `\rrbracket`*** | !["Vertikaler Balken mit Doppelpfeil"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Arrowvert` |
| !["Einzelner Pfeil nach unten"](/tex/images/java/tutorial/latex-ams-math-delim-5-8.png) | `\downarrow` | !["Schrägstrich"](/tex/images/java/tutorial/latex-ams-math-delim-5-16.png) | `/` | !["Doppelte vertikale Linie"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\|` |
| !["Einzelner Pfeil nach oben"](/tex/images/java/tutorial/latex-ams-math-delim-5-9.png) | `\uparrow` | !["Umgekehrter Schrägstrich"](/tex/images/java/tutorial/latex-ams-math-delim-5-17.png) | `\backslash` | !["Doppelte vertikale Linie"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Vert` |
| !["Einzelner Auf-Ab-Pfeil"](/tex/images/java/tutorial/latex-ams-math-delim-5-10.png) | `\updownarrow` | | `.` | !["Quadratwurzelzeichen"](/tex/images/java/tutorial/latex-ams-math-delim-5-23.png) | `\sqrtsign` |


> *Kursiv gedruckte Symbole erfordern entweder das Paket `amsmath` oder, wenn zusätzlich fett gedruckt, das Paket `stmaryrd`. Ein Punkt (.) ist selbst kein erweiterbares Symbol, kann aber verwendet werden, um ein „unsichtbares“ Trennzeichen zu erzeugen. Das Symbol `\sqrtsign` kann nicht mit `\left`, `\right` oder `\middle` verwendet werden.*

> *Synonyme: [ - `\lbrack`, `[`; ] - `\rbrack`, `]`; { - `\lbrace`, `\{`; } - `\rbrace`, `\}`; | - `\vert`, `|`; || - `\Vert`, `\|`.*

Diese Symbole sind nur in bestimmten Verwendungszwecken erweiterbar. Sie müssen auf folgender Konstruktion basieren:

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> Wenn LaTeX das eTeX-Programm verwendet, können Sie diese erweiterbaren Symbole auch mit `\middle` verwenden.

Hier können `<ext-Open>` und `<ext-Close>` jedes der in der obigen Tabelle aufgeführten Symbole (außer `\sqrtsign`) sein. Es müssen Symbole sein, die erweiterbar eingerichtet wurden, wie im [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf) beschrieben. Daher muss ein Symbol verfügbar sein, das das Fehlen einer tatsächlichen Glyphe darstellt. Es kam vor, dass dieses Symbol, auch als *Null-Trennzeichen* bekannt, der Punkt (.) ist. Die Größen der tatsächlichen Glyphen zum Setzen eines erweiterbaren Symbols werden so gewählt, dass sie zur Höhe und Tiefe der dazwischen liegenden Unterformel passen.

Das Wurzelsymbol `\sqrtsign` wächst sowohl vertikal als auch horizontal, um sich an die Größe seines Arguments anzupassen. In LaTeX würden Sie lieber den Befehl `\sqrt` verwenden, um dieses Symbol zu erhalten.


```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![Verlängernde Radikale](/tex/images/java/tutorial/latex-ams-math-5-24.png)