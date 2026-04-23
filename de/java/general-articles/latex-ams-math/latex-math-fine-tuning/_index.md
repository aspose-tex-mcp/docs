---
translation: true
template: /templates/_template-java.md
linktitle: Vorgrößenanpassungen des Layouts
title: 7. Vorgrößenanpassungen des Layouts
weight: 70
url: /java/latex-math-fine-tuning/
keywords: ams-latex, amsmath, Latex-Math-Abstände, Latex-Math-Stile, Latex-Math-Trennzeichen, Latex-Math-Klammern, Latex-Math-Ausrichtung
description: In diesem Artikel geht es um die Feinabstimmung des mathematischen Layouts – automatische Größen- und Abstände, große Trennzeichen, präzise Ausrichtung.
lastmod: 2026-04-21
---

{{<section overview>}}

Normalerweise leistet LaTeX hervorragende Arbeit bei der Erstellung mathematischer Formeln. Manchmal ist jedoch eine feinere Anpassung der Positionierung erforderlich. In diesem Artikel werden einige Techniken zur Feinabstimmung des Layouts erläutert, um mathematische Formeln etwas besser zu machen.

## 7.1. Automatische Größen- und Abstandsanpassung

Mathematische Symbole und Buchstaben werden im Allgemeinen kleiner (und mit engeren Abständen), wenn sie in Brüchen, tiefgestellten oder hochgestellten Zeichen erscheinen. Mathematische Formeln können in acht TeX-Mathe-Stilen angelegt werden:

||||
|---|---|---|
| *D, D'* | `\displaystyle`| Auf Zeilen für sich alleine angezeigt |
| *T, T'* | `\textstyle`| Im Text eingebettet |
| *S, S'* | `\scriptstyle`| In Hoch- bzw. Tiefstellungen |
| *SS, SS'* | `\scriptscriptstyle`| In allen höheren Hoch- bzw. Tiefstellungen |

Der Textstil (*T*) wird auf der obersten Ebene einer Formel verwendet, die im Fließtext steht (zwischen einem Paar `$` oder zwischen `\(` und `\)`), während der Anzeigestil auf der obersten Ebene einer angezeigten Formel verwendet wird (zwischen einem Paar `$$` oder zwischen `\[` und `\]`). Wie bei Unterformeln kann der Stil aus der folgenden Tabelle bestimmt werden:

||||||
|---|---|---|---|---|
| *D* | *S* | *S'* | *T* | *T'* |
| *D'* | *S'* | *S'* | *T'* | *T'* |
| *T* | *S* | *S'* | *S* | *S'* |
| *T'* | *S'* | *S'* | *S'* | *S'* |
| *S, SS* | *SS* | *SS'* | *SS* | *SS'* |
| *S', SS'* | *SS'* | *SS'* | *SS'* | *SS'* |

Das nächste Beispiel veranschaulicht die verschiedenen Stile:

```tex
\normalsize                 %% Style:
\[ b                        %% D
    ^0                      %% S
   +                        %% D
   \frac{(k + p)            %% T
          _{j'}             %% S'
         % \displaystyle
         \pm                %% T [D]
         \frac{(f + q)      %% S [T]
                ^{(pk)      %% SS [S]
                   ^y       %% SS
                   _{j'}}}  %% SS'
              {(h + y)}}    %% S' [T']
        {(l + q)            %% T'
          ^{(pk)}}          %% S'
\]
```

![Verschiedene Mathematikstile](/tex/images/java/tutorial/latex-ams-math-7-1.png)

Sie können das Kommentarzeichen („%“) vor `\displaystyle` entfernen und sehen, wie sich einige der Stile zu denen in Klammern geändert haben:

![Explizite geänderte Mathematikstile](/tex/images/java/tutorial/latex-ams-math-7-2.png)

Es zeigt, wie Sie den in jedem Teil zu verwendenden Stil explizit angeben.

## 7.2. Unterformeln

Im Text gibt ein Klammerpaar eine Gruppe oder einen Bereich an, innerhalb dessen eine Deklaration wirksam ist. Innerhalb einer mathematischen Formel grenzen sie außerdem eine Unterformel ab, die immer als separate Einheit gesetzt und der äußeren Formel hinzugefügt wird. Infolgedessen werden Unterformeln immer in ihrer natürlichen Breite gesetzt und nicht horizontal gedehnt oder verkleinert, wenn TeX einen Absatz aufbaut und versucht, die Formel in eine Zeile einzufügen. Wir haben bereits gezeigt, dass die Unterformel einer einfachen Klammergruppe so verarbeitet wird, als wäre sie ein einzelnes Symbol. Das bedeutet, dass eine leere Gruppe ein unsichtbares Symbol erzeugt, das den Abstand ändern kann.

Der Inhalt von tiefgestellten/hochgestellten Zeichen und die Argumente vieler (aber nicht aller) Befehle, wie z. B. `\frac` und `\mathrel`, sind ebenfalls Unterformeln. Somit erhalten sie die gleiche Sonderbehandlung. Das Argument von `\bm` wird beispielsweise nicht unbedingt als Unterformel festgelegt, und dies ist eine der wichtigen Ausnahmen. Wenn Sie in einer mathematischen Formel nur den Umfang einer Deklaration einschränken müssen, definieren Sie eine Gruppe mit `\begingroup` und `\endgroup`. Denken Sie daran, dass spezielle mathematische Deklarationen, wie z. B. Stiländerungen, bis zum Ende der aktuellen Unterformel gelten, unabhängig davon, ob andere Gruppen vorhanden sind oder nicht.

## 7.3. Große Trennzeichen

LaTeX definiert vier Befehle – `\big`, `\Big`, `\bigg` und „Bigg“, um eine direkte Steuerung der Größe erweiterbarer Trennzeichen zu ermöglichen. Sie nehmen ein einzelnes Argument, das ein erweiterbares Trennzeichen sein muss, und erzeugen größere Versionen des Trennzeichens, vom 1,2- bis 3-fachen der Basisgröße.

Es gibt außerdem drei Varianten für jeden der vier Befehle, die vier Größen des *Eröffnungssymbols* ergeben (`\bigl`, `\bigl`, `\biggl` und `\Biggl`). vier Größen von *Relationssymbol* (`\bigm`, `\Bigm`, `\biggm` und `\Biggm`); und vier Größen von *Schlusssymbolen* (`\bigr`, `\Bigr`, `\biggr` und `\Biggr`). Alle 16 dieser Befehle müssen mit jedem Symbol verwendet werden, das entweder nach `\left`, `\right` oder (mit eTeX) `\middle` stehen kann (siehe diese [Tabelle](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols#53-symbols-that-are-vertically-extensible)). 

Die Größen dieser Trennzeichen sind im Standard-LaTeX festgelegt. Mit dem Paket `amsmath` passen sich die Größen jedoch an die Größe des umgebenden Materials an, je nach verwendeter Schriftgröße und mathematischem Stil. Dies wird im folgenden Beispiel gezeigt.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\[ \biggl( \mathbf{E}_{y} \int_0^{t_\varepsilon}
   L_{x, y^x(s)} \varphi(x)\, ds \biggr) \]
\Large
\[ \biggl( \mathbf{E}_{y} \int_0^{t_\varepsilon}
   L_{x, y^x(s)} \varphi(x)\, ds \biggr) \]
```

![Trennzeichen passen sich der aktuellen Schriftgröße und dem mathematischen Stil an](/tex/images/java/tutorial/latex-ams-math-7-3.png)

## 7.4. Anpassen des Indexes an einem Radikal

Die Platzierung des Index auf einem Wurzelzeichen ist in Standard-LaTeX nicht immer gut. Sie können jedoch die im Paket `amsmath` definierten Befehle `\leftroot` und `\uproot` verwenden, um die Positionierung dieses Indexes anzupassen. Positive ganzzahlige Argumente für diese Befehle verschieben den Index nach links bzw. oben, während negative Argumente ihn nach rechts und unten verschieben. Diese Argumente werden in mathematischen Einheiten angegeben, die recht klein sind, sodass diese Befehle zur Feinabstimmung geeignet sind.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\[
  \sqrt[\beta]{k} \qquad
  \sqrt[\leftroot{2}\uproot{4} \beta]{k} \qquad
  \sqrt[\leftroot{1}\uproot{3} \beta]{k}
\]
```

![Anpassen des Index eines Radikalzeichens](/tex/images/java/tutorial/latex-ams-math-7-4.png)

## 7.5. Feinabstimmung mit Streben und Phantomen

Wann immer Sie den mathematischen Abstand und die Ausrichtung „perfekt“ setzen möchten, ist es in der Regel am besten, auf die einzigartigen und erweiterten Fähigkeiten von primitivem TeX zurückzugreifen. Der Zugriff auf diese Funktionen erfolgt über eine Reihe von Befehlen im Zusammenhang mit `\phantom` und `\smash`. Diese Befehle können entweder in mathematischen Formeln oder im Fließtext verwendet werden.

Schauen wir uns das folgende Beispiel an:

```tex
\usepackage{amsmath}
\newcommand\relphantom[1]{\mathrel{\phantom{#1}}}
\newcommand\ve{\varepsilon} \newcommand\tve{t_{\varepsilon}}
\newcommand\vf{\varphi} \newcommand\yvf{y_{\varphi}}
\newcommand\bfE{\mathbf{E}}
% -------------------------------------------------------------------------------
\begin{equation} \begin{split}
  f_{h, \ve}(x, y)
    &= \ve \bfE_{x, y} \int_0^{\tve} L_{x, \yvf(\ve u)} \vf(x) \,du  \\
    &= h \int L_{x, z} \vf(x) \rho_x(dz)                             \\
    &\relphantom{=} {} + h \biggl[
       \frac{1}{\tve}
       \biggl( \bfE_{y} \int_0^{\tve}  L_{x, y^x(s)} \vf(x) \,ds
               - \tve \int L_{x, z} \vf(x) \rho_x(dz)      \biggr) + \\
    &\relphantom{=} \phantom{{} + h \biggl[ }
       \frac{1}{\tve}
       \biggl( \bfE_{y} \int_0^{\tve}  L_{x, y^x(s)} \vf(x) \,ds
               - \bfE_{x, y} \int_0^{\tve} L_{x, \yvf(\ve s)}
                                            \vf(x) \,ds    \biggr) \biggr]
\end{split} \end{equation}
```

![Die Phantome der Formel](/tex/images/java/tutorial/latex-ams-math-7-5.png)

Hier wird mit dem Befehl `\phantom` die horizontale Positionierung angepasst. In der Präambel wird es verwendet, um ein unsichtbares Beziehungssymbol zu definieren, dessen Breite seinem Argument entspricht (in diesem Beispiel „=“). In mathematischen Umgebungen wird es verwendet, um bestimmte Zeilen auszurichten, indem sie mit einer „Phantom“ oder unsichtbaren Unterformel begonnen werden. Das leere Klammerpaar `{}` ist dasselbe wie `\mathord{}`, was ein unsichtbares Symbol mit der Breite Null erzeugt, das benötigt wird, um den korrekten Abstand von „+ *h*“ zu erhalten (ohne `{}`, das Plus Vorzeichen erzeugt ein unäres Plus mit einem ungeeigneten Abstand vor *h*).

Im Gegensatz zu `\phantom` setzt der Befehl `\smash` seinen Inhalt (in einer LR-Box), ignoriert dann aber sowohl deren Höhe als auch Breite, als ob sie beide Null wären. Der im Standard-LaTeX definierte Befehl `\hphantom` ist eine Kombination aus beiden. Es erzeugt das Äquivalent von `\smash{\phantom{einige Phantominhalte}}`, d. h. eine unsichtbare Box mit einer Höhe und Tiefe von Null, aber der Breite des Phantominhalts.

Der Befehl `\vphantom` ist ähnlich, setzt jedoch die Breite des Phantoms auf Null und behält seine Gesamthöhe plus Tiefe bei. Der Befehl `\mathstrut` ist als `\vphantom(` definiert und erzeugt ein Feld mit der Breite Null, dessen Höhe und Tiefe der einer Klammer entsprechen.

Mit dem Paket `amsmath` kann der Befehl `\smash` ein optionales Argument annehmen, sodass `\smash[t]{...}` die Höhe des Inhalts der Box ignoriert und die Tiefe beibehält, während `\smash[ b]{...}` ignoriert die Tiefe und behält die Höhe bei.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$\sqrt{x} + \sqrt{y} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\mathstrut y} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\smash{y}} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\smash[b]{y}} + \sqrt{z}$
```

![Den radikalen Ausdruck zerschlagen](/tex/images/java/tutorial/latex-ams-math-7-6.png)

Es scheint, dass die Radikale ähnlich aussehen, wenn man dem *y* mit einer Strebe etwas mehr Höhe verleiht. Stattdessen sehen sie dadurch nur noch anders und insgesamt hässlicher aus. Es stellt sich heraus, dass es der beste Weg ist, den Boden des *y* zu zertrümmern.

Das folgende Beispiel zeigt eine sehr häufige Verwendung von Smashing. Der Befehl `\smash` wird dort verwendet, um eine genaue Kontrolle über die Höhe der umgebenden Trennzeichen zu ermöglichen. Es zeigt sich auch, dass das Zertrümmern zu Problemen führen kann, da die tatsächliche Höhe der Linie bekannt sein muss. Dies wird von `\vphantom` repariert. `\Hmjd` ist das zusammengesetzte Symbol, definiert als:


```tex
\newcommand\Hmjd{\widetilde{\mathcal{H}^2}_{MJD}(\chi)}
```

Um den resultierenden vertikalen Raum anzuzeigen, haben wir Regeln hinzugefügt:

| *Aussehen* | `Code` | *Kommentar* |
|:---:|:---:|---|
| !["Äußere Klammern zu groß"](/tex/images/java/tutorial/latex-ams-math-smashing-7-1.png) | `\left( {\Hmjd } \right)` | *Äußere Klammern zu groß* |
| !["Äußere Klammern zu klein und Linien zu eng"](/tex/images/java/tutorial/latex-ams-math-smashing-7-2.png) | `\left( \smash{\Hmjd } \right)` | *Äußere Klammern zu klein und Linien zu eng* |
| !["Genau richtig"](/tex/images/java/tutorial/latex-ams-math-smashing-7-3.png) | `\left( \smash[t]{\Hmjd } \right) \vphantom{\Hmjd}` | *Genau richtig!* |
| !["Sowohl Vphantom als auch Partial Smash erforderlich"](/tex/images/java/tutorial/latex-ams-math-smashing-7-4.png) | `\left( \smash[t]{\Hmjd } \right)` | *Sowohl `\vphantom` als auch Partial Smash sind erforderlich* |

> An einigen Stellen können Mängel in der TeX-Verarbeitung auf niedriger Ebene zu Fehlern in den Feinheiten des Schriftsatzes führen. Dies kann in bestimmten Layouts passieren, in denen (a) eine Unterformel (Zähler/Nenner eines Bruchs oder tiefgestellter/hochgestellter Index) aus genau einer LR-Box oder einer ähnlich konstruierten mathematischen Box besteht und (b) diese Box nicht ihre natürliche Größe hat, wie bei den komplexeren Formen von `\makebox`, Schrägstrichen und einigen Phantomen.

Um dies zu sehen, schauen wir uns das folgende Beispiel an:


```tex
\[
\sqrt{ \frac{a+b}{x_j} } \quad
\sqrt{ \frac{a+b}{\smash{x_j}} } \quad
\sqrt{ \frac{a+b}{{}\smash{x_j}} } \quad
\sqrt{ \frac{a+b}{\smash{x_j+b}} }
\]
```

![Probleme durch Smashes](/tex/images/java/tutorial/latex-ams-math-7-7.png)

Um die Tiefe des Radikals zu verringern, wurde im zweiten Radikal ein `\smash` hinzugefügt, was jedoch keine Wirkung hatte. Im dritten Radikal funktionierte es mit einer leeren Klammergruppe.  Aber im vierten Radikal war keine leere Klammergruppe erforderlich. Um es zusammenzufassen: Wenn Sie feststellen, dass `\smash` nicht funktioniert, versuchen Sie, vor dem einsamen Feld eine leere mathematische Unterformel (`{}`) einzufügen, damit es richtig behandelt wird.

## 7.6. Horizontaler Abstand

Für eine feinere und schwierigere Abstimmung sind die in der folgenden Tabelle aufgeführten expliziten Abstandsbefehle erforderlich:

![Horizontale Abstandsbefehle](/tex/images/java/tutorial/latex-ams-math-7-8.png)
Sowohl die Voll- als auch die Kurzform dieser Befehle sind robust und können auch außerhalb mathematischer Formeln in normalem Text verwendet werden. Sie hängen mit den dünnen, mittleren und dicken Leerzeichen zusammen, die auf den Maschinen zur Verfügung standen, die Mitte des 20. Jahrhunderts zum Setzen von Mathematik eingesetzt wurden.

Die aktuellen Werte der drei TeX-Parameter `\thinmuskip`, `\medmuskip` und `\thickmuskip` definieren die Menge an Speicherplatz, die durch diese `\..space`-Befehle hinzugefügt wird. Ihre Standardwerte mit `amsmath` sind in der Tabelle aufgeführt. Diese Low-Level-Parameter erfordern Werte in mathematischen Einheiten (*mu*). Daher können sie nur über TeX-Zuweisungen auf niedriger Ebene festgelegt werden, nicht über `\setlength` oder ähnliches. Darüber hinaus sollten ihre Werte normalerweise nicht geändert werden, da sie intern vom mathematischen Schriftsatz von TeX verwendet werden (siehe folgende Tabelle).

![Abstand zwischen Symbolen](/tex/images/java/tutorial/latex-ams-math-7-9.png)

> In der Tabelle bedeutet 0 „kein Leerzeichen“, 1 bedeutet `\thinmuspace`, 2 bedeutet `\medmuskip`, 3 bedeutet `\thickmuskip`, * bedeutet `unmöglich`. Fettgedruckte Einträge bedeuten, dass in mathematischen Schriftstilen das entsprechende Leerzeichen nicht hinzugefügt wird.

Eine mathematische Einheit (`1mu`) entspricht 1/18 eines *em* in der aktuellen mathematischen Schriftgröße. Daraus folgt, dass der absolute Wert eines *mu* je nach Mathematikstil variiert, sodass unabhängig vom verwendeten Stil ein konsistenter Abstand entsteht.