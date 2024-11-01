---
translation: true
template: /templates/_template-java.md
linktitle: Verzierte Symbole und zusammengesetzte Strukturen
title: 4. Verzierte Symbole und zusammengesetzte Strukturen | LaTeX
weight: 40
url: /java/latex-math-decorations/
keywords: ams-latex, amsmath, amsxtra, Latex-Integrale, Latex-Brüche, Latex-Dekorationen, Latex-Pfeile, Latex-Grenzwerte, modulare Latex-Beziehungen
description: In diesem Artikel werden eine Reihe von Befehlen besprochen, die mithilfe des amsmath-Pakets verschiedene mittelgroße mathematische Strukturen erzeugen.
lastmod: "2024-09-26"
---

{{<section overview>}}

Das Paket `amsmath` bietet einige Befehle zum Erstellen von Strukturen wie bruchähnlichen Objekten und dekorierten Symbolen. Hier werden einige davon besprochen.


## 4.1. Allgemeine Brüche

Das Paket `amsmath` definiert den Befehl `\genfrac`, der einen verallgemeinerten Bruch erzeugt.

```tex
\genfrac{ldelim}{rdelim}{thick}{style}{num}{denom}
```

Die ersten beiden Argumente definieren linke bzw. rechte Trennzeichen. Mit dem dritten Argument *thick* können Sie die Standarddicke der Bruchregel überschreiben. Binominalkoeffizienten (siehe unten) verwenden beispielsweise den Wert `0pt` für dieses Argument, um die Linie unsichtbar zu machen. Der Standardwert (wenn leer gelassen) der Linienstärke wird durch die aktuelle Schriftarteinstellung für den mathematischen Schriftsatz bestimmt. Die folgende Liste enthält die in den Beispielen dieses Artikels verwendeten Standardwerte.

| ***Style*** | ***Default Thickness*** |
|:---:|:---:|
| text/display | 0.4pt |
| script | 0.34pt |
| scriptscript | 0.24pt |

Das vierte Argument, *style*, überschreibt (sofern es nicht leer gelassen wird) den mathematischen Stil für das verwendete Layout und die verwendete Schriftgröße. Der Wert muss im Bereich 0-3 liegen: 0 – `\displaystyle`, 1 – `\textstyle`, 2 – `\scriptstyle`, 3 – `\scriptscriptstyle`. Wenn dieses Argument leer bleibt, wird der Stil gemäß den normalen Regeln für Brüche ausgewählt. Die letzten beiden Argumente sind Zähler und Nenner.

> Die alten Bruchbefehle `\over`, `\overwithdelims`, `\atop`, `\atopwithdelims`, `\above` und `\abovewithdelims`, die Standard-LaTeX von TeX erbt, erzeugen Warnungen, wenn sie mit dem Paket `amsmath` verwendet werden.

### 4.1.1. Einfache Brüche

Mit dem Befehl `\genfrac` definiert das Paket `amsmath` außerdem drei Befehle als praktische Abkürzungen: `\frac`, `\dfrac` und `\tfrac`.

```tex
\newcommand\frac [2]{\genfrac{}{}{}{}{#1}{#2}}
\newcommand\dfrac[2]{\genfrac{}{}{}{0}{#1}{#2}}
\newcommand\tfrac[2]{\genfrac{}{}{}{1}{#1}{#2}}
```

Das folgende Beispiel zeigt die Verwendung dieser Befehle:

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \frac{1}{k} \log_2 c(f)
  \quad \tfrac{1}{k} \log_2 c(f)
\end{equation}
Text: $ \sqrt{ \frac{1}{k} \log_2 c(f) } \quad
        \sqrt{ \dfrac{1}{k} \log_2 c(f) }\, $.

```

![\frac, \dfrac und \tfrac](/tex/images/java/tutorial/latex-ams-math-4-1.png)

### 4.1.2. Binomialkoeffizienten

Eine weitere bruchartige Struktur sind Binomialkoeffizienten. Um Ihnen beim Schreiben zu helfen, bietet das Paket `amsmath` ähnliche Befehle `\binom`, `\dbinom` und `\tbinom`.

So wird der Befehl `\genfrac` abgekürzt:


```tex
\newcommand\binom[2]{\genfrac{(}{)}{0pt}{}{#1}{#2}}
\newcommand\dbinom[2]{\genfrac{(}{)}{0pt}{0}{#1}{#2}}
\newcommand\tbinom[2]{\genfrac{(}{)}{0pt}{1}{#1}{#2}}
```

Und hier ist das Beispiel:

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \binom{k}{2} 2^{k - 1} + \tbinom{k - 1}{2} 2^{k - 2}
\end{equation}
Text: $ \binom{k}{2} 2^{k - 1} + \dbinom{k - 1}{2} 2^{k - 2} $.
```

![\binom, \dbinom und \tbinom](/tex/images/java/tutorial/latex-ams-math-4-2.png)

### 4.1.3. Fortsetzungsbrüche

Wenn Sie ein Brucharray setzen müssen, das im Wesentlichen ein unendlicher Bruch ist, der auch als „Fortsetzungsbruch“ bezeichnet wird, gibt es den Befehl `\cfrac` im Paket `amsmath`. Übergeben Sie das optionale Argument `[l]` oder `[r]`, um einen Zähler links oder rechts auszurichten, der standardmäßig zentriert ist.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
\cfrac {1}{\sqrt{2} +
  \cfrac {1}{\sqrt{3} +
    \cfrac {1}{\sqrt{4} +
      \cfrac[r] {1}{\sqrt{5} +
        \cfrac[l] {1}{\sqrt{6} + \dotsb }
}}}}
\end{equation*}
```

![Ein Kettenbruch](/tex/images/java/tutorial/latex-ams-math-4-3.png)

## 4.2. Box-Mathematik

Das Paket `amsmath` stellt den Befehl „\boxed“ ähnlich wie `\fbox` bereit, um den Inhalt des Mathematikmodus in eine Box zu packen.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \boxed { f(x_0 - x) \leq f(x_0) \leq f(x_0 + x) }
\end{equation}
```

![Eine Boxformel](/tex/images/java/tutorial/latex-ams-math-4-4.png)

## 4.3. Grenzen setzen

Tiefgestellte und hochgestellte Zeichen für Integrale, Summen, Produkte oder andere Operatoren können entweder über und unter dem mathematischen Operator (der „Grenzposition“) oder an der tiefgestellten/hochgestellten Position rechts vom Operator platziert werden. Normalerweise werden im Text keine Begrenzungen verwendet (andernfalls können sich die Zeilen ausbreiten). In einer angezeigten Formel hängt die Platzierung vom Operator ab. Das folgende Beispiel zeigt die Standardplatzierung in LaTeX.

```tex
\[
\sum_{n=1}^N \qquad \int_{-\infty}^\infty \qquad \lim_{x \to x_0}
\]
Text: $\sum_{n=1}^N$, $\int_{-\infty}^\infty$, $\lim_{x \to x_0}$.
```

![Die Standardplatzierung der tiefgestellten/hochgestellten Zeichen in LaTeX](/tex/images/java/tutorial/latex-ams-math-4-5.png)

Das Paket `amsmath` bietet Optionen zur Steuerung der Positionierung. Sie sind unten aufgeführt, wobei *default* das Verhalten markiert, falls das Paket `amsmath` mit einer Standard-LaTeX-Dokumentklasse, aber ohne eine dieser Optionen verwendet wird.

|||
|:---:|---|
| `intlimits`, `nointlimits` | Platziert hochgestellte/tiefgestellte Zeichen der Integrationssymbole jeweils oberhalb und unterhalb bzw. seitlich (Standard). Wird nur in angezeigten Formeln verwendet. |
| `sumlimits`, `nosumlimits` | Platziert hochgestellte/tiefgestellte Zeichen von *großen Operatoren* (Summe, Produkt usw.) jeweils oberhalb und unterhalb (Standard) bzw. seitlich. Wird nur in angezeigten Formeln verwendet. |
| `namelimits`, `nonamelimits` | Ähnlich wie `sumlimits` oder `nosumlimits`, aber für bestimmte Operatoren oder „Operatornamen“ wie `inf`, `sup`, `lim`, `min`, `max`, die traditionell mit tiefgestellten Zeichen darunter gesetzt werden, zumindest wenn sie in einer angezeigten Formel vorkommen. |

TeX verfügt über drei primitive Befehle, die unmittelbar nach dem Symbol- oder Operatornamen erscheinen und die Positionierung von tiefgestellten/hochgestellten Zeichen steuern: `\limits`, `\nolimits` und `\displaylimits`. Der Befehl `\displaylimits` erzeugt tiefgestellte/hochgestellte Zeichen an der Grenzposition, wenn der aktuelle Mathematikstil ein Anzeigestil ist. Dies ist das Standardverhalten, wenn ein Symbol der Klasse *Operator* erscheint oder ein `\mathop`-Befehl verwendet wird. Wenn Sie einen Operator mit tiefgestellten/hochgestellten Zeichen an der Grenzposition außerhalb einer Anzeige setzen müssen, müssen Sie ihn einzeln mit dem Befehl `\limits` deklarieren.

Vergleichen Sie das folgende Beispiel mit dem vorherigen.

```tex
\[
\sum\nolimits_{n=1}^N \qquad \int\limits_{-\infty}^\infty \qquad \lim\displaylimits_{x \to x_0}
\]
Text: $\sum\nolimits_{n=1}^N$, $\int\limits_{-\infty}^\infty$, $\lim\displaylimits_{x \to x_0}$.
```

![Steuern der Platzierung der tiefgestellten/hochgestellten Zeichen mit TeX-Primitiven](/tex/images/java/tutorial/latex-ams-math-4-6.png)

## 4.3. Mehrere Integrale

Um mehrere Integralzeichen mit gut angepassten Abständen dazwischen sowohl im Text als auch in der Anzeige zu setzen, verwenden Sie die Befehle `\iint`, `\iiint` und `\iiiint`. `\idotsint` erzeugt zwei Integralzeichen mit Auslassungspunkten dazwischen.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\iint \limits _V f(x,y) \,dx \,dy \\
\iiint \limits _V f(x,y,z) \,dx \,dy \,dz \\
\iiiint \limits _V f(t,x,y,z) \,dt \,dx \,dy \,dz \\
\idotsint \limits _V f(x_1, \dots, x_k) \,\mathbf{dx}
\end{gather*}
```

![Mehrere Integrale](/tex/images/java/tutorial/latex-ams-math-4-7.png)

## 4.4. Modulare Beziehungen

Die `mod`-Notation für Äquivalenzklassen ganzer Zahlen unterliegt den speziellen Abstandskonventionen. Um damit umzugehen, bietet das Paket `amsmath` die Befehle `\mod`, `\bmod`, `\pmod` und `\pod`. Das folgende Beispiel zeigt die Verwendung dieser Befehle.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
u & \equiv v + 1 \mod{n^2} \\
u & \equiv v + 1 \bmod{n^2} \\
u & = v + 1 \pmod{n^2} \\
u & = v + 1 \pod{n^2}
\end{align*}
The in-text layout: $ u = v + 1 \pmod{n^2} $
\begin{gather*}
(m \bmod n) = k^2 \, ; \quad x \equiv y \pmod b \, ; \\
x \equiv y \mod c \, ; \quad x \equiv y \pod d\, .
\end{gather*}
```

![Modulare Beziehung](/tex/images/java/tutorial/latex-ams-math-4-8.png)

> Mit `amsmath` wird der Abstand von `\pmod` innerhalb einer nicht angezeigten Formel verringert.

## 4.5. Mathematische Punktakzente

Zusätzlich zu den mathematischen Akzenten `\dot` und `\ddot` stellt das Paket `amsmath` die Befehle `\dddot` und `\ddddot` bereit, die dreifache bzw. vierfache Punktakzente erzeugen.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$ \dot{A} \quad \ddot{B} \quad \dddot{C} \quad \ddddot{D} $
```

![Punktakzente](/tex/images/java/tutorial/latex-ams-math-4-9.png)

## 4.6. Hochgestellte Zeichen aus Akzenten machen: das Paket `amsxtra`.

Das Paket `amsxtra` bietet eine nützliche Funktion, eine Sammlung einfacher Befehle zum Platzieren von Akzenten als hochgestellte Zeichen für Unterformeln:

```tex
\usepackage{amsxtra}
% -------------------------------------------------------------------------------
$(abc)\spdddot$ \quad $(abc)\spddot$ \quad $(abc) \spdot$ \\
$(abc)\spbreve$ \quad $(abc)\spcheck$ \\
$(abc)\sphat$ \quad $(abc)\sptilde$
```

![Akzente als hochgestellte Zeichen](/tex/images/java/tutorial/latex-ams-math-4-10.png)

## 4.7. Andere Dekorationen

Standard-LaTeX verfügt über den Befehl `\stackrel`, der einen hochgestellten Index über einem *Relation*-Symbol platziert. Darüber hinaus definiert das Paket `amsmath` die Befehle `\overset` und `\underset`. Verwenden Sie es, um Material über oder unter einem *Ordinary*- oder *Relation*-Symbol oder einem *Binary-Operator*-Symbol zu platzieren.

Der Befehl `\sideset` fügt zusätzlich zu den normalen Grenzwerten Dekorationen zu jedem *Operator*-Symbol (Summe, Produkt usw.) hinzu. Diese werden an den tiefgestellten und hochgestellten Positionen links und rechts vom *Operator* platziert.

```tex
\[ \overset{*}{X} > \underset{*}{X}
\iff \sideset{}{'}\sum_{a,b \in \mathbf{R^*}}
\overset{a}{\underset{b}{X}} = X \]
```

![Mehr Dekoration](/tex/images/java/tutorial/latex-ams-math-4-11.png)