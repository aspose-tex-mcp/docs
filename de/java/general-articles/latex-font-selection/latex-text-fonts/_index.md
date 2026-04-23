---
translation: true
template: /templates/_template-java.md
linktitle: So verwenden Sie LaTeX-Schriftarten in Texten
title: 3. So verwenden Sie LaTeX-Schriftarten in Texten
weight: 30
url: /java/latex-text-fonts/
keywords: Latex, Latex-Schriftarten, Latex-Textschriftbefehle, Latex groß, Latex-Schriftgröße
description: Im Artikel werden LaTeX-Schriftbefehle behandelt, die verschiedene Schriftartattribute unabhängig voneinander für die Verwendung in normalem Text ändern.
lastmod: "2024-09-26"
---

{{<section overview>}}

Wenn Sie ein LaTeX-Dokument schreiben, wählen die zur Strukturierung des Dokuments verwendeten Markup-Tags automatisch die entsprechenden Schriftarten aus. Beispielsweise werden für eine Abschnittsüberschrift Schriftartattribute wie „Groß“ und „Fett“ von der Dokumentklasse definiert und angewendet, wenn ein „\section“-Befehl verwendet wird. Daher müssen Sie Schriftartattribute selten direkt angeben.

Aber manchmal ist es notwendig. Beispielsweise möchten Sie möglicherweise eine andere Schriftfamilie (oder ein anderes allgemeines Schriftattribut) für den Haupttext auswählen. Eine solche Änderung kann oft einfach durch die Angabe eines geeigneten Pakets erfolgen.

Ein anderer Fall ist, wenn Sie bestimmte Fragmente des Dokuments als besonders kennzeichnen möchten, beispielsweise um Akronyme, Beispiele oder Firmennamen zu kennzeichnen. Wenn Sie beispielsweise eine serifenlose Schriftart für diese Fragmente verwenden möchten, können Sie dies tun, indem Sie Firmennamen mit „\textsf{...}“ umgeben. Die bessere Vorgehensweise besteht jedoch darin, zu diesem Zweck einen neuen Befehl (z. B. „\Company“) zu definieren. Das Definieren einzelner Befehle für logisch unterschiedliche Dinge erleichtert es, die Formatierung später konsistent zu ändern.

Möglicherweise möchten Sie eine Tabelle auch in einer kleineren Größe setzen, damit sie auf eine Seite passt. Da Dokumentklassen Dokumente nur bedingt automatisch formatieren können, ist dieser Wunsch berechtigt. Daraus folgt, dass zur Erstellung einer endgültigen Version häufig manuelle Formatierungen wie das Einfügen von Seitenumbrüchen erforderlich sind. Leider erschwert eine explizite Formatierung die weitere Nutzung des Dokuments und ist fehleranfällig. Daher sollte die direkte Verwendung von Befehlen zum Ändern der Schriftart in einem Dokument minimiert werden. Dies gilt auch für alle visuellen Formatierungsbefehle.


## 3.1. So verwenden Sie Schriftartbefehle in Standard-LaTeX

Die für den Haupttext eines Dokuments verwendete Schriftart wird *Hauptschriftart*, *Hauptschriftart* oder *Normalschriftart* genannt. Es wird automatisch am Anfang des Dokuments und in bestimmten Konstrukten wie Fußnoten und Abbildungen ausgewählt. Abschnittsüberschriften und andere logische Markup-Tags wechseln je nach Dokumentklasse automatisch in eine andere Schriftart oder -größe. Daher ist die Einführung des korrekten logischen Markups die einzige vom Autor erforderliche Aktion. Manchmal kann es jedoch wünschenswert sein, bestimmte Teile des Textes durch Auswahl einer geeigneten Schriftart manuell hervorzuheben. Dies geschieht mit den unten besprochenen Befehlen.

Für die meisten Befehle zum Ändern der Schriftart gibt es zwei Formen: einen Befehl mit einem Argument, wie zum Beispiel „\textbf{...}“, und eine Deklaration, wie zum Beispiel „\bfseries“. Die deklarative Form akzeptiert keine Argumente, sondern weist LaTeX vielmehr an, dass es sich von nun an (bis zum Ende der aktuellen Gruppe von geschweiften Klammern oder Umgebungen) auf eine besondere Weise verhalten soll. Das bedeutet, dass Sie nicht so etwas wie „\bfseries{...}“ schreiben sollten, da dies von diesem Punkt bis zum Ende der aktuellen Umgebung alles fett machen würde.

Um die Schriftarten für einzelne Wörter oder kurze Sätze in Ihrem Dokument zu ändern, verwenden Sie besser die Schriftartbefehle mit einem Argument. Für längere Fragmente sollten Sie die Umgebungsform der Deklaration verwenden, wie im folgenden Beispiel gezeigt:

```tex
Some words in this sentence are \begin{bfseries}typeset in bold letters.
The bold typeface\end{bfseries} continues here. 
```

![Die Umgebungsform von \bfseries](/tex/images/java/tutorial/latex-font-selection-3-1.png)

Die deklarativen Formen selbst eignen sich häufig besser zur Definition neuer Umgebungen oder Befehle.

> Es ist außerdem wichtig, dass die Schriftbefehle mit einem Argument keine Absatzumbrüche im Argument zulassen.

### Die Hauptschriftart des Dokuments

Mit dem Befehl „\textnormal“ oder der Angabe „\normalfont“ können Sie auf die Hauptdokumentschriftart umschalten. Sie kommen normalerweise nur in den Definitionen von Befehlen oder Umgebungen vor, wenn es wichtig ist, eine Möglichkeit zu definieren, unabhängig von den Umgebungsbedingungen immer die gleiche Schriftart zu verwenden. Der Befehl zum Setzen von LaTeX-Befehlsnamen würde beispielsweise wie folgt aussehen:

```tex
\newcommand\Lcs[1]{{\normalfont\ttfamily\textbackslash#1}%}
```

Die Verwendung von „\normalfont“ verhindert, dass die Befehlsnamen kursiv angezeigt werden, selbst innerhalb des kursiv gesetzten Texts.

### Standardschriftfamilien

Standardmäßig verwaltet LaTeX drei Schriftfamilien: eine Textschriftart mit Serifen, auf die mit dem Befehl `\textrm` zugegriffen werden kann; eine serifenlose Textschriftart, auf die über „\textsf“ zugegriffen werden kann; und eine Schreibmaschinenschrift (monospaced), auf die über „\texttt“ zugegriffen werden kann. Die Deklarationsformen dieser Befehle sind `\rmfamily`, „\sffamily“ bzw. „\ttfamily“.

Die genauen Namen der externen Schriftfamilien, auf die diese Befehle zugreifen, hängen von der Dokumentklasse ab, können aber in der Präambel oder durch Pakete geändert werden. Als Standardinstallation ist die Schriftfamilie mit Serifen **Computer Modern Roman**, die serifenlose Schriftfamilie **Computer Modern Sans** und die Schreibmaschinenfamilie **Computer Modern Typewriter**. Wenn Sie ein anderes Setup verwenden, sollten Sie darauf achten, diese Standardschriftfamilien zu definieren, damit die Schriftarten ohne optische Konflikte gemischt werden können. Es ist außerdem wichtig sicherzustellen, dass externe Schriftarten in der richtigen Auflösung für das Zielausgabegerät verfügbar sind.

Die meisten Dokumentklassen legen die Serifenschriftart, auf die über `\textrm` zugegriffen wird, als Hauptschriftart des Dokuments fest, sodass der Befehl `\textrm` nicht oft verwendet wird. Wenn ein Dokumentdesigner jedoch eine serifenlose Schriftart als Hauptschriftart ausgewählt hat, wäre `\textrm` die alternative Serifenschriftfamilie.

### Standard-Schriftserie

In LaTeX ist die *Serie* eine Kombination aus zwei Attributen: Breite und Gewicht (Fettigkeit). LaTeX ermöglicht das Ändern der Reihe mit zwei Befehlen: „\textmd“ und „\textbf“. Die entsprechenden Deklarationen lauten „\mdseries“ bzw. „\bfseries“. Der erste Befehl wählt eine Schriftart mit mittleren Werten für Breite und Stärke aus, während letzterer auf eine fettere Reihe umschaltet. Auch hier hängen die tatsächlichen Werte von der Dokumentklasse und ihren Optionen oder nachfolgenden Paketen ab. In einer Standardeinstellung wechselt „\textbf“ zu einer fetten erweiterten Version der aktuellen Schriftart, während „\textmd“ zur Version mittlerer Breite und mittlerer Stärke der aktuellen Schriftart zurückkehrt.

### Standardschriftformen

Die *Form* der aktuellen Schriftart ist das dritte Schriftartattribut, das unabhängig von den anderen geändert werden kann. Die Standardform für die meisten Dokumente ist die aufrechte Form, auf die bei Bedarf mit dem Befehl „\textup“ oder der Deklaration „\upshape“ zugegriffen werden kann.

Die am häufigsten verwendeten Befehle scheinen „\textit“ und „\textsc“ zu sein, die jeweils zu einer kursiven bzw. Kapitälchenschrift wechseln. Die entsprechenden Deklarationen sind „\itshape“ und „\scshape“.

Der Befehl „\textsl“ (seine Deklarationsform ist „\slshape“) wechselt zur schrägen Form. Eine Schriftfamilie enthält oft nur eine kursive oder eine schräge Form, obwohl Computer Modern Roman beides enthält.

An der Stelle, an der man vom schrägen zum aufrechten Zeichen wechselt, rücken die Zeichen meist zu nahe beieinander, insbesondere wenn das letzte schräge Zeichen eine Oberlänge hat. Der richtige zusätzliche Platz, der an dieser Grenze hinzugefügt werden sollte, wird als **kursive Korrektur** bezeichnet. Die genaue Breite dieses Leerzeichens hängt vom einzelnen Zeichen ab und ist in der Datei „.tfm“ gespeichert. Die Schriftartbefehle mit Argumenten fügen die kursive Korrektur automatisch hinzu, aber wenn Deklarationen verwendet werden, muss sie manuell mit „\/“ eingefügt werden. Bei einer aufrechten Schriftart beträgt die Kursivkorrektur der Zeichen normalerweise Null oder ist sehr gering, obwohl es einige Ausnahmen gibt. Das nächste Beispiel zeigt, wie formverändernde Deklarationen, die zu schrägen Formen wechseln, korrekt verwendet werden.

```tex
\raggedright
When switching back from {\itshape italic\/} or {\slshape slanted\/} shapes to an upright font one
should add the {\itshape italic correction}, except when a small punctuation character follows.
```

![Die kursive Korrektur](/tex/images/java/tutorial/latex-font-selection-3-2.png)
Kapitälchen werden manchmal in Überschriften oder zur Formatierung von Namen verwendet. Für letzteren Fall können Sie beispielsweise den Befehl „\name“ wie folgt definieren:

```tex
\newcommand\name[1]{\textsc{#1}}
```

Alternativ können Sie zwei Deklarationen verwenden:

```tex
\newcommand\name[1]{{\normalfont\scshape #1}}
```

Der erste Befehl wechselt einfach zur Kapitälchenform, während die zweite Form zunächst alle Schriftattribute auf ihre Standardwerte zurücksetzt. Welche Option Sie wählen, hängt von den verfügbaren Schriftarten und der Art des Dokuments ab. Bei Computer Modern enthalten nur die Familien „Roman“ und „Typewriter“ Kapitälchenformen, daher könnte die zweite Definition in bestimmten Anwendungen bevorzugt werden, da sie auch im „\sffamily“-Kontext Kapitälchen (wenn auch mit Serifen) verwendet. Der erste Befehl würde eine mittelgroße Schriftart mit Kapitälchen und geformter Schrift der Computer Modern Sans-Familie anfordern. Diese Schriftart ist nicht verfügbar, daher würde LaTeX versuchen, einen Ersatz zu finden, indem es zunächst das Shape-Attribut auf seinen Standardwert ändert. Infolgedessen würden Sie keine Small Caps erhalten.

Ein weiterer LaTeX-Sonderformbefehl ist der Befehl „\emph“, der Fragmente in normalem Text hervorhebt. Seine deklarative Form ist „\em“. Hervorgehobene Wörter im Text werden traditionell kursiv gesetzt; Wenn jedoch eine Hervorhebung in einem bereits kursiv geschriebenen Textfragment gewünscht wird, wechselt man in der Regel wieder zur Hochschrift. Der Befehl „\emph“ unterstützt diese Konvention, indem er zur „\itshape“-Form wechselt, wenn die aktuelle Schriftart aufrecht ist, und zur „\upshape“-Form, wenn die aktuelle Schriftart bereits schräg ist (d. h. wenn die Form „\itshape“ ist). ` oder `\slshape`). Der Benutzer muss sich also keine Gedanken über den aktuellen Status des Textes machen, wenn er den Befehl „\emph“ oder die Deklaration „\em“ verwendet.

```tex
{\em Nevertheless, one has to be careful about the\/ {\em proper\/} use of italic corrections
on both ends of the emphasized text}. It is therefore better to use the \verb=\emph= command,
which \emph{automatically} takes care of the italic correction on both sides.
```

![Hervorhebung von Textfragmenten](/tex/images/java/tutorial/latex-font-selection-3-3.png)

### Standardschriftgrößen

In LaTeX gibt es 10 Befehle zum Ändern der Größe. Diese Befehle haben keine entsprechenden Befehlsformen mit einem Argument, da Änderungen der Schriftgröße normalerweise nur in den Definitionen von Befehlen verwendet werden.

![Standardschriftgrößen](/tex/images/java/tutorial/latex-font-selection-3-4.png)

Die von diesen Befehlen ausgewählte Größe hängt von den Einstellungen in der Dokumentklasse und möglicherweise von damit angegebenen Optionen (z. B. „11pt“) ab. Im Allgemeinen entspricht „\normalsize“ der Hauptgröße des Dokuments, und die Befehle zum Ändern der Größe bilden eine geordnete Reihenfolge, beginnend mit „\tiny“ als kleinster Größe und bis zu „\Huge“ als größter Größe. Es kann vorkommen, dass sich mehrere Befehle auf die gleiche Größe beziehen. Wenn beispielsweise ein großes „\normalsize“ gewählt wird, kann „\Huge“ dasselbe sein wie „\huge“. Aber der Auftrag wird immer eingehalten.

Die Größenänderungsbefehle für die Haupttextgrößen (d. h. „\normalsize“, „\small“ und „\footnotesize“) wirken sich normalerweise auf den Abstand um Listen und Anzeigen aus. Um ihr Verhalten zu ändern, sollte man daher nicht einfach ihre Definition durch einen Aufruf von „\fontsize“ ersetzen, sondern stattdessen mit ihrer ursprünglichen Definition beginnen, wie in „classes.dtx“ dokumentiert.

## 3.2. So kombinieren Sie Standardschriftbefehle

Wie bereits gezeigt, können die Standardbefehle und -deklarationen zum Ändern der Schriftart kombiniert werden, was zur Auswahl einer Schriftart führt, die der Kombination der Schriftartattribute entspricht. Siehe das Beispiel unten:

```tex
One can typeset a text {\sffamily\bfseries\large in a large sans serif
bold typeface} but note the unchanged leading! \LaTeX{} uses the value
in force at the \emph{end} of the paragraph!
```

![LaTeX-Schriftart-Befehlskombinationen](/tex/images/java/tutorial/latex-font-selection-3-5.png)
Intern wechselt der Befehl „\sffamily“ zur serifenlosen Standardfamilie, dann wechselt „\bfseries“ zur Standard-Fettdruckreihe in dieser Familie und schließlich wählt „\large“ eine große Größe aus, lässt aber alle anderen Attribute unverändert. Der Anfang scheint unverändert zu sein, da der Gültigkeitsbereich von „\large“ vor dem Ende des Absatzes endet. Schriftartmetrikdateien werden für alle Zwischenschriftarten geladen, auch wenn diese Schriftarten nie verwendet werden. Im obigen Beispiel lauten sie „Sans Serif Medium 10pt“ nach „\sffamily“, dann „Sans Serif Bold Extended 10pt“ nach „\bfseries“ und schließlich „Sans Serif Bold Extended 14pt“. die Schriftart, die tatsächlich verwendet wird. Daher können solche Befehle auf hoher Ebene dazu führen, dass die Schriftartenauswahl von LaTeX unnötigerweise Schriftarten lädt, die nie verwendet werden. Wenn eine bestimmte Kombination zum ersten Mal verwendet wird, kommt es nur zu einem geringen Verlust an Verarbeitungsgeschwindigkeit. Wenn Sie jedoch viele verschiedene Kombinationen dieses Typs haben, sollten Sie besser darüber nachdenken, sie in Form von [primitiven Deklarationen zum Ändern der Schriftart](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/) zu definieren.

## 3.3. Vergleich von Schriftartbefehlen und -deklarationen

Die Befehle zum Ändern der Schriftart mit Argumenten beginnen alle mit „\text...“ (außer „\emph“), um hervorzuheben, dass sie für die Verwendung in normalem Text gedacht sind. Die Verwendung solcher Befehle anstelle der deklarativen Formen hat den Vorteil, dass die Konsistenz mit anderen LaTeX-Konstrukten gewahrt bleibt. Sie sind zum Setzen kurzer Textabschnitte in einer bestimmten Familie, Reihe oder Form gedacht. Die folgende Tabelle zeigt die Wirkung dieser Befehle.

![Befehle und Deklarationen](/tex/images/java/tutorial/latex-font-selection-3-6.png)

Ein weiterer Vorteil dieser Befehle besteht darin, dass sie automatisch alle erforderlichen Kursivkorrekturen auf beiden Seiten ihres Arguments einfügen. Sie müssen sich also keine Sorgen über fehlende Kursivkorrekturen machen, wenn Sie Schriftarten ändern.

Die automatisch eingefügte Kursivschrift ist in sehr wenigen Situationen falsch. Es empfiehlt sich in der Regel, auf die Kursivschriftkorrektur zu verzichten, wenn ein kleines Interpunktionszeichen (ein Komma oder ein Punkt) direkt auf die Schriftartänderung folgt. Sie können festlegen, in welchen Fällen die Kursivkorrektur unterdrückt werden soll. Dies geschieht durch die Angabe der Zeichen, die eine vorangegangene Kursivkorrektur aufheben sollen, in der Liste „\nocorrlist“. Die Standarddefinition für diesen Befehl lautet

```tex
\newcommand{\nocorrlist}{,.}
```

Es ist auch möglich, die Kursivkorrektur in einzelnen Fällen zu unterdrücken. Zu diesem Zweck steht der Befehl „\nocorr“ zur Verfügung. Beachten Sie, dass Sie „\nocorr“ am linken oder rechten Ende innerhalb des Arguments der „\text...“-Befehle einfügen müssen, je nachdem, auf welcher Seite des Fragments die Kursivkorrektur unterdrückt werden muss.

```tex
\emph{When using the \LaTeX{} high-level font commands, the \emph{proper} use of
italic corrections is automatically taken care of}. Only \emph{sometimes} one has
to help \LaTeX{} by adding a \verb=\nocorr= command.
```

![Die kursive Korrektur](/tex/images/java/tutorial/latex-font-selection-3-7.png)

Im Gegensatz dazu eignen sich die Deklarationsformulare häufig besser zum Definieren eigener Befehle oder Umgebungen.

```tex
% Part of the preamble
\newenvironment{bfitemize}{\begin{itemize}%
  \normalfont\bfseries\raggedright}{\end{itemize}}
-----------------------------------------------
\begin{bfitemize}
\item This environment produces boldface items.
\item It is defined in terms of \LaTeX's
\texttt{itemize} environment and NFSS declarations.
\end{bfitemize}
```

![Die Liste mit fettgedruckten Elementen](/tex/images/java/tutorial/latex-font-selection-3-8.png)

## 3.4. So greifen Sie auf alle Zeichen einer Schriftart zu

Selbst wenn ein Zeichen in einer Schriftart vorhanden ist, ist es manchmal nicht möglich, es über die Tastatur einzugeben. Auf viele nützliche Zeichen kann über Befehle wie „\ss“ oder „\AE“ zugegriffen werden. Einige Zeichen können implizit aus Buchstabenfolgen generiert werden, wie „ffi“, das die Ligatur „ffi“ erzeugt, und „---“, das den langen Bindestrich in den Standard-TeX-Schriftarten erzeugt.

Darüber hinaus können Sie mit dem Befehl „\symbol“ auf jedes Zeichen in einer Schriftart zugreifen, indem Sie dessen Nummer im aktuellen Codierungsschema entweder als Dezimalzahl, Oktalzahl (mit vorangestelltem „“) oder Hexadezimalzahl (mit vorangestelltem „““) angeben .

```tex
\fontencoding{T1}\selectfont
-----------------------------------------------
In the font encoding (\texttt{T1}), characters like \symbol{"DE},
symbol{'237}, and \symbol{32} are included and can be accessed with
the \verb=\symbol= command.
```

![Der \symbol-Befehl](/tex/images/java/tutorial/latex-font-selection-3-9.png)

## 3.5. So ändern Sie die Standardschriftarten für Texte

Wenn Sie das Gesamterscheinungsbild eines Dokuments einfach ändern möchten, können Sie die integrierten Hooks von LaTeX verwenden, die das Verhalten der zuvor besprochenen Befehle zum Ändern von Schriftarten auf hoher Ebene ändern. Die Werte dieser Hooks können in Paketdateien oder in der Präambel eines Dokuments mithilfe von „\renewcommand“ festgelegt werden. Hier ist die Liste der Hooks:

![Die Hooks für die Änderung von Schriftarten auf hoher Ebene](/tex/images/java/tutorial/latex-font-selection-3-10.png)
Zum Beispiel, wenn Sie in der Präambel schreiben

```tex
\renewcommand\familydefault{cmss}
```

Ein ganzes Dokument würde in Computer Modern Sans herauskommen, da diese Neudefinition die Schriftfamilie für die von LaTeX verwendete Hauptschriftart ändert. Im Detail wird die Hauptschriftart des Dokuments durch die Werte von „\encodingdefault“, „\familydefault“, „\seriesdefault“ und „\Shapedefault“ bestimmt. Das bedeutet, dass Sie sicherstellen müssen, dass diese Befehle so definiert sind, dass ihre Kombination auf eine vorhandene Schriftform in den internen Tabellen von LaTeX verweist.

Der Standardwert von `\encodingdefault` (`OT1`) dient eigentlich der Kompatibilität. Das bedeutet, dass LaTeX davon ausgeht, dass die meisten Schriftarten die Originalkodierung verwenden. In den meisten Fällen ist es besser, die Kodierung `.fd` zu verwenden, da sie viele zusätzliche Glyphen enthält, die mit `OT1` nicht verfügbar sind, und eine ordnungsgemäße Silbentrennung für Wörter mit Akzentzeichen ermöglicht. Heutzutage unterstützen einige Schriftarten `OT1` überhaupt nicht, da sie für die Verwendung mit `.fd` konzipiert sind.

Es ist wichtig zu bedenken, dass nicht jede Schriftart als Standardschriftart für die Dokumentkodierung verwendet werden kann. Voraussetzung ist, dass die Kodierung die meisten sichtbaren ASCII-Buchstaben an ihren Standardpositionen enthält. Der „\encodingdefault“ kann durch Laden des „fontenc“-Pakets mit einer oder mehreren Optionen geändert werden.

Die anfängliche Einstellung von „\familydefault“ bedeutet, dass eine Änderung von „\rmdefault“ implizit „\familydefault“ auf den neuen Wert ändert, sofern keine spezielle Einstellung für „\familydefault“ definiert ist. Aber wenn „\familydefault“ geändert wird, ist „\rmdefault“ nicht betroffen.