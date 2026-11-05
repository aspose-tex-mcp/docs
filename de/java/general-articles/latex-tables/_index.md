---
translation: true
template: /templates/_template-java.md
linktitle: Tabellen in LaTeX
title: Erstellen und Bearbeiten von Tabellen in LaTeX
weight: 50
url: /java/latex-tables/
keywords: LaTeX-Tabellen, tabellarische Umgebung, LaTeX-Tabellendesign, Tabellenformatierung in LaTeX, Satztabellen in LaTeX, LaTeX-Tabellenlayout, LaTeX-Tabellenabstand, Anpassen von LaTeX-Tabellen, LaTeX-Tabellenausrichtung, mehrzeilig und mehrspaltig in LaTeX-Tabellen
description: Dieser Artikel ist eine Kurzanleitung zum Erstellen funktionaler, leserfreundlicher, optisch ansprechender und professioneller Tabellen in LaTeX.
lastmod: "2024-09-26"
---

{{<section overview>}}

## 1. Einführung

Tabellen spielen eine wichtige Rolle bei der Verbesserung der Klarheit, Organisation und visuellen Attraktivität akademischer und beruflicher Dokumente. Sie dienen als leistungsstarke Möglichkeit, komplexe Daten, Vergleiche und Beziehungen in einem strukturierten und leicht verständlichen Format darzustellen. Hier ein kurzer Überblick über ihre Bedeutung:

1. **Datenzusammenfassung**: Tabellen bieten eine komprimierte Darstellung von Informationen, deren Erläuterung andernfalls mehrere Absätze erfordern würde. Sie ermöglichen es Autoren, große Datenmengen prägnant darzustellen, was es den Lesern erleichtert, wichtige Punkte zu verstehen.

2. **Klare Visualisierung**: Komplexe Daten wie statistische Zahlen, Umfrageergebnisse und experimentelle Ergebnisse können mithilfe von Tabellen effektiver dargestellt werden. Das tabellarische Format hilft Lesern, Trends, Muster und Ausreißer viel einfacher zu erkennen.

3. **Vergleichende Analyse**: Tabellen ermöglichen den direkten Vergleich verschiedener Datensätze. Ganz gleich, ob es um den Vergleich von Produktspezifikationen, finanzieller Leistung oder Forschungsvariablen geht – Tabellen helfen den Lesern, auf einen Blick aussagekräftige Schlussfolgerungen zu ziehen.

4. **Logische Organisation**: Tabellen bieten eine logische Struktur, die Daten in Zeilen und Spalten unterteilt. Diese Organisation erleichtert die Präsentation von Daten mit unterschiedlichen Kategorien und ermöglicht den Lesern eine einfache Navigation und das Auffinden spezifischer Informationen.

5. **Datenintegrität**: Im akademischen und beruflichen Kontext ist die Datengenauigkeit von größter Bedeutung. Mithilfe von Tabellen können Autoren Rohdaten präsentieren und so das Risiko einer Fehlinterpretation eliminieren, die bei der Übermittlung von Daten in narrativer Form auftreten kann.

6. **Referenzen und Zitate**: Wenn Tabellen gut beschriftet und ordnungsgemäß referenziert sind, werden sie zu wertvollen Referenzpunkten innerhalb eines Dokuments. Autoren können bei der Erörterung von Ergebnissen auf bestimmte Tabellen verweisen, was es den Lesern erleichtert, der Argumentation zu folgen.

7. **Visuelles Engagement**: Gut gestaltete Tabellen unterbrechen die Monotonie des Textinhalts, fesseln die Leser visuell und helfen, ihr Interesse aufrechtzuerhalten. Sie tragen zur Gesamtästhetik und Professionalität eines Dokuments bei.

8. **Effizienz in der Kommunikation**: Vielbeschäftigte Fachleute und Forscher müssen Informationen oft schnell abrufen. Mithilfe von Tabellen können sie Daten anzeigen und bestimmte Details finden, ohne Textabschnitte lesen zu müssen.

9. **Standardisierung**: In der akademischen Forschung werden häufig standardisierte Tabellen verwendet, um experimentelle Methoden, Ergebnisse und statistische Analysen darzustellen. Dies stellt die Konsistenz aller Veröffentlichungen sicher und trägt zur Reproduzierbarkeit der Forschung bei.

Im Wesentlichen dienen Tabellen als Informationsdrehscheiben, die datengesteuerte Erkenntnisse effizient präsentieren und gleichzeitig ein strukturiertes und leserfreundliches Format beibehalten. Ihre Aufgabe, komplizierte Details zu vermitteln und gleichzeitig Klarheit und Zugänglichkeit zu gewährleisten, macht sie zu einem unverzichtbaren Werkzeug sowohl in der akademischen als auch in der beruflichen Kommunikation.

Wenden wir uns nun LaTeX zu, einem leistungsstarken Satzsystem, mit dem Autoren ihre Ideen in wunderschön gestaltete Dokumente umwandeln können. LaTeX überwindet die Grenzen herkömmlicher Textverarbeitungsprogramme und bietet ein Reich an Präzision, Eleganz und Vielseitigkeit, das sich bei der Verarbeitung tabellarischer Strukturen deutlich bemerkbar macht.
Im Kern ist LaTeX mehr als nur ein Tool zur Dokumentenvorbereitung; Es ist eine Kunstform, die Typografie mit Technologie verbindet. Egal, ob Sie wissenschaftliche Arbeiten, Berichte, Präsentationen oder sogar Bücher erstellen, LaTeX zeichnet sich durch die Erstellung von Dokumenten aus, die nicht nur ästhetisch ansprechend sind, sondern auch Informationen mit äußerster Klarheit vermitteln. Seine Meisterschaft liegt unter anderem in der nahtlosen Integration komplexer Tabellenstrukturen, die das Rückgrat der Datendarstellung in verschiedenen Bereichen bilden.

Mit LaTeX geht die Anordnung von Informationen in Tabellen über ein einfaches Raster aus Zeilen und Spalten hinaus. Stattdessen handelt es sich um eine sorgfältig orchestrierte Symphonie, bei der Ausrichtung, Abstände und Stil harmonieren, um eine raffinierte Präsentation der Daten zu ermöglichen. Tabellarische Strukturen in LaTeX werden zu visuellen Erzählungen, die komplexe Datensätze, Beziehungen und Vergleiche elegant und präzise vermitteln.

Durch die Bereitstellung zahlreicher Tools und Pakete, die auf das tabellarische Design zugeschnitten sind, verwandelt LaTeX Daten in visuelles Storytelling. Von der Steuerung der Spaltenbreite bis hin zur Anpassung von Zellrändern und Schattierungen stellt der Anpassungsgrad von LaTeX sicher, dass jede Tabelle perfekt zum Zweck Ihres Dokuments passt. Für diejenigen, die mit mathematischen, technischen oder wissenschaftlichen Inhalten arbeiten, erleichtert die nahtlose Einbindung von Gleichungen und Symbolen in Tabellenzellen durch LaTeX die Kommunikation komplexer Ideen.

Dennoch geht die Leistungsfähigkeit von LaTeX über die bloße Ästhetik hinaus. Es erhöht die Effizienz durch Querverweismechanismen und macht Tabellen zu Orientierungspunkten für die Navigation in Ihrem Dokument. Darüber hinaus ermöglichen die LaTeX-Pakete die Erstellung komplexer Layouts, die sich über mehrere Zeilen oder Spalten erstrecken und so den anspruchsvollsten Datenpräsentationen gerecht werden.

Je tiefer Sie in die Welt von LaTeX eintauchen, desto differenziertere Funktionen entdecken Sie; die Funktionen, die LaTeX zu einem unverzichtbaren Werkzeug für Wissenschaftler, Fachleute und Forscher gleichermaßen machen. Sie tauchen in die Kunst ein, Tabellen zu entwerfen, die Aufmerksamkeit erregen, Informationen überzeugend präsentieren und zur Gesamtwirkung Ihres Dokuments beitragen.


## 2. Grundlagen von Tabellen in LaTeX

Das grundlegende Konzept von Tabellen in LaTeX dreht sich um die `tabellarische` Umgebung, in der Sie Spalten, Zeilen und deren Inhalt definieren, um Daten in einem strukturierten und optisch ansprechenden Format zu organisieren und darzustellen.

Die Grundstruktur einer Tabelle in LaTeX umfasst die folgenden Komponenten:

1. **Beginn der „tabellarischen“ Umgebung**: Um eine Tabelle zu erstellen, schließen Sie den Tabelleninhalt in eine `tabellarische` Umgebung ein. Diese Umgebung legt das Layout und die Struktur der Tabelle fest.

2. Spaltenspezifikation: In der tabellarischen Umgebung definieren Sie die Anzahl der Spalten und deren Ausrichtung mithilfe von Spaltenspezifizierern. Zu den gängigen Spezifizierern gehören `l` für linksbündige Spalten, `c` für zentrierte Spalten und `r` für rechtsbündige Spalten. Sie können auch festlegen, welche Spalten LaTeX durch vertikale Linien trennen und welche vertikalen Außenränder gezeichnet werden sollen.

3. **Zeileninhalt**: Jede Zeile der Tabelle wird durch Angabe des Inhalts für jede Zelle innerhalb der Zeile erstellt. Zellen werden durch das Symbol `&` getrennt und jede Zeile wird mit dem Befehl `\\` abgeschlossen.

4. **Horizontale Linien**: Mit dem Befehl `\hline` können Sie horizontale Linien zum Trennen von Zeilen sowie horizontale Außenränder hinzufügen. Dies wertet die optische Struktur des Tisches auf.

### Einfache Beispiele

Hier ist ein einfaches Beispiel einer LaTeX-Tabelle:

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}

```

In diesem Beispiel wird die `tabular`-Umgebung verwendet, um eine Tabelle mit drei Spalten zu erstellen, jede zentriert (`c`). Das Ergebnis des Satzes ist unten dargestellt:

<a href="/tex/images/java/tutorial/latex-tables-1.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-1.jpg)</a>

Das folgende Beispiel zeigt, wie Sie eine Tabelle mit links- und rechtsbündigen Spalten erstellen.
```tex
\begin{tabular}{|l r||}
  \hline
  Company & Income \\            \hline \hline
  Pinapple Computer & \$150M \\
  Megasoft & \$210M \\
  General Waters Ltd. & \$98M \\
  Alphamet & \$2117M \\           \hline
\end{tabular}
```

Der rechte Außenrand wird doppelt gemacht, die Kopfzeile wird ebenfalls durch eine Doppellinie von der Tabelle getrennt, es gibt keine vertikale Linie, die die Spalten trennt.

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

Sie können auch horizontale Linien zeichnen, die nicht die gesamte Tabelle von links nach rechts umfassen.

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

Hier weist der Befehl `\cline{i-j}` LaTeX an, eine Linie von der i<sup>ten</sup> Spalte zur j<sup>ten</sup> Spalte zu zeichnen.

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](latex-tables-3.jpg)</a>

Spalten in einer Tabelle können eine feste Breite haben. In diesem Fall werden sie *Absatzspalten* genannt. Um solche Spalten zu erstellen, verwenden Sie den Bezeichner `p`, gefolgt von der Spaltenbreite in geschweiften Klammern. Betrachten Sie das folgende Beispiel:

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

Beachten Sie die Verwendung des Befehls `\newline`.

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

Mit dem Paket `array` stehen zwei weitere Optionen für Spalten mit fester Breite zur Verfügung: `m{width}` – wie `p{width}`, richtet den Zelleninhalt jedoch vertikal in der Mitte aus;
`b{width}` – wie `p{width}`, richtet den Zelleninhalt jedoch unten vertikal aus.

In dem seltenen Fall, dass eine Tabelle in den Text eines Absatzes eingefügt werden muss, können Sie die Position der Tabelle relativ zur Grundlinie der umschließenden Textzeile angeben. Zu diesem Zweck verwenden Sie die Option `t`, `c` (Standard) oder `b`, um die Grundlinie am oberen, mittleren oder unteren Rand der Tabelle auszurichten. Zum Beispiel,

```tex
This is the text of the paragraph
\begin{tabular}[t]{|r|l|}     \hline
  9D5 & hexadecimal \\
  4725 & octal \\             \cline{2-2}
  1001 1101 0101 & binary \\  \hline \hline
  2517 & decimal \\           \hline
\end{tabular}
that include a table.
```

Hier teilen wir LaTeX mit, dass die Grundlinie am unteren Rand der Tabelle ausgerichtet werden soll.

<a href="/tex/java/latex-tables/latex-tables-5.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### Mehrere Spalten definieren

Wenn Ihre Tabelle identisch ausgerichtete Spalten enthält, können Sie sie alle mit der Syntax `*{num}{format}` als Eins definieren. Dies ist besonders nützlich, wenn Ihre Tabelle viele Spalten enthält.

```tex
\begin{tabular}{l*{7}{c}r}
  Employee   & Sun & Mon & Tue & Wed & Thu & Fri & Sat & Total \\ \hline
  John Doe   &     &  x  &     &     &     &  x  &     &   2   \\
  Dean Jones &  x  &     &  x  &     &  x  &     &     &   3   \\
  Chris Cross&     &     &     &  x  &     &     &     &   1   \\
  Pete Brad  &     &     &     &     &     &     &  x  &   1
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-6.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-6.jpg)</a>

### Spaltenspezifikation mit `>{\command}` und `<{\command}`.

Eine andere Möglichkeit, Spalten anzugeben, besteht darin, `>{\command}` für Befehle zu verwenden, die direkt *vor* jedem Spaltenelement ausgeführt werden, und `<{\command}` für Befehle, die direkt *nach* jedem Spaltenelement ausgeführt werden. Dies ist verfügbar, wenn das Paket `array` in der Präambel des Dokuments enthalten ist. Im folgenden Beispiel verwenden wir diese Syntax, um jede von zwei Spalten zu zentrieren und die erste fett zu schreiben.

```tex
\begin{tabular}{>{\centering\textbf\bgroup}p{3.5cm}<{\egroup}>|{\centering}p{3.5cm} }
  History & Geometry
  \tabularnewline \hline
  Ancient & Elementary
  \tabularnewline
  Medieval & Affine 
  \tabularnewline
  Modern & Analytic
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. Anpassen des Tabellenlayouts

Bei LaTeX-Tabellen ist die Anpassung der Abstände entscheidend, um sicherzustellen, dass die Tabelle gut strukturiert und optisch ansprechend erscheint. Der richtige Abstand verbessert die Lesbarkeit und verhindert eine Überfüllung des Inhalts. Hier sind einige wichtige Aspekte der Abstandsanpassung in LaTeX-Tabellen:

### Abstand zwischen den Spalten

LaTeX fügt automatisch etwas Abstand zwischen den Spalten hinzu. Um den Abstand zwischen den Spalten anzupassen, können Sie den Befehl `\setlength{\tabcolsep}{value}` vor der tabellarischen Umgebung verwenden. Durch Erhöhen des Werts wird der Abstand zwischen den Spalten vergrößert. Der Standardwert ist „6pt“.

### Abstand zwischen den Reihen

Um den Abstand zwischen Zeilen zu vergrößern, können Sie den Befehl `\renewcommand{\arraystretch}{value}` vor der `tabular`-Umgebung verwenden. Durch Erhöhen des Werts werden die Zeilen auseinandergezogen und der vertikale Abstand der Tabelle vergrößert. Der Standardwert ist „1,0“.

Sie können den Sprung nach einer Zeile auch explizit angeben, indem Sie Kleber nach dem Zeilenendezeichen verwenden.

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### Verwendung der Ausdrücke `@` und „!“.
Wenn das Paket `array` in der Präambel des Dokuments enthalten ist, können Sie Spaltentrennzeichen mit den Konstrukten `@{...}` oder `!{...}` angeben.

Normalerweise verwenden sie Text als Argument und fügen diesen Text beim Anhängen an eine Spalte automatisch in jede Zelle dieser Spalte vor und/oder nach den tatsächlichen Daten für diese Zelle ein. Der Befehl `@{...}` ersetzt den Zwischenspaltenraum durch den als Argument angegebenen Inhalt. Indem Sie das Argument leer lassen, können Sie die Leerzeichen zwischen den Spalten unterdrücken.

Nehmen wir eine Basistabelle, die durch den folgenden Code angegeben wird:

```tex
\begin{tabular}{|l|l|}
  \hline
  1.1 & 1.2 \\ \hline
  2.1 & 2.2 \\
  \hline
\end{tabular}
```

Durch Variation der Spaltenbeschreibung erhalten wir folgende Ergebnisse:

<a href="/tex/java/latex-tables/latex-tables-9.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-9.jpg)</a>

Um den ursprünglichen Abstand beizubehalten, können Sie `!{...}` verwenden.

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

Und hier ist ein Beispiel für eine Spalte mit Gleitkommazahlen, die am Dezimalpunkt ausgerichtet sind:

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}

```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### Verwendung des Pakets `dcolumn`.

Mit dem Paket `dcolumn`, das einen neuen Spaltenspezifizierer für Gleitkommazahlen bereitstellt, ist es möglich, eine Spalte auf dem Dezimaltrennzeichen zu zentrieren. Die einfache Verwendung dieses Pakets wird im folgenden Beispiel demonstriert:

```tex
\usepackage{dcolumn}
................................................
\newcolumntype{d}[1]{D{.}{\cdot}{#1} } %the argument for d specifies the maximum number of decimal places
\begin{tabular}{l r c d{1} }
  Left&Right&Center&\mathrm{Decimal}\\
  1&2&3&4\\
  11&22&33&44\\
  1.1&2.2&3.3&4.4\\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

Beachten Sie, dass eine dezimal ausgerichtete Spalte im Mathematikmodus gesetzt wird, weshalb im obigen Beispiel `\mathrm` für die Spaltenüberschrift verwendet wird. Außerdem wird Text in einer dezimal ausgerichteten Spalte (z. B. der Kopfzeile) vor dem Dezimaltrennzeichen rechtsbündig ausgerichtet (vorausgesetzt, der Text enthält kein Dezimaltrennzeichen). Während dies für sehr kurzen Text oder numerische Spaltenüberschriften in Ordnung sein mag, sieht es im obigen Beispiel umständlich aus. Eine Lösung hierfür ist die Verwendung des unten beschriebenen Befehls `\multicolumn`, der eine einzelne Spalte und deren Ausrichtung angibt. Um beispielsweise im obigen Beispiel die Überschrift *Decimal* über ihrer Spalte zu zentrieren, wäre die erste Zeile der Tabelle selbst `Left&Right&Center&\multicolumn{1}{c}{Decimal}\\`.

## 4. Zellen zusammenführen

Eine etwas komplexere Tabelle kann durch horizontales und/oder vertikales Zusammenführen von Zellen erhalten werden.

### Zellen, die sich über mehrere Spalten erstrecken

Die allgemeine Form des Befehls, der dafür sorgt, dass sich eine Zelle über mehrere Spalten erstreckt, lautet: `\multicolumn{num_cols}{alignment}{contents}`. Hier ist `num_cols` die Anzahl der zusammenzuführenden Spalten; `alignment` ist entweder `l`, `c`, `r` oder, um Text umzubrechen, `p{width}`. Und `Inhalt` sind die Daten, die Sie in diese Zelle einfügen möchten.

Hier ist das einfache Beispiel:

```tex
\begin{tabular}{|l|l|}
  \hline
  \multicolumn{2}{|c|}{Available currencies} \\
  \hline
  CNY & Chinese Yuan \\
  JPY & Japanese Yen \\
  GBP & Great Britain Pound \\
  USD & US Dollar \\
  CAD & Canadian Dollar \\
  EUR & Euro \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-13.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-13.jpg)</a>

### Zellen, die sich über mehrere Zeilen erstrecken

Damit sich eine Zelle über mehrere Zeilen erstreckt, müssen Sie das Paket `multirow` einbinden. Das Paket stellt den folgenden Befehl bereit: `\multirow{num_rows}{width}{contents}`.

Hier ist `num_rows` die Anzahl der zusammenzuführenden Zeilen; `width` ist die Zellenbreite (`*` für die natürliche Breite des Inhalts) und `contents` sind die tatsächlichen Daten, die in der Zelle gesetzt werden sollen.

```tex
\begin{tabular}{|l|l|l|}
  \hline
  \multicolumn{3}{ |c| }{Available currencies} \\
  \hline
  South America & BRL & Brazilian Real \\ \hline
  \multirow{3}{*}{Asia} & CNY & Chinese Yuan \\
   & JPY & Japanese Yen \\
   & HKD & Hong Kong Dollar \\ \hline
  \multirow{3}{*}{Europe} & EUR & Euro \\
   & GBP & Great Britain Pound \\
   & CHF & Swiss Franc \\ \hline
  Oceania & AUD & Australian Dollar \\ \hline
  \multirow{2}{*}{North America} & USD & US Dollar \\
   & CAD & Canadian Dollar \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-14.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-14.jpg)</a>

Sie müssen bedenken, dass Sie bei Verwendung des Befehls `\multirow` für jede entsprechende Zelle in jeder nachfolgenden zu überspannenden Zeile einen leeren Eintrag einfügen müssen.

### Überspannende Zellen in beide Richtungen

Das folgende Beispiel zeigt, wie man Zellen gleichzeitig in beide Richtungen erstreckt und die Ränder korrekt zeichnet:

```tex
\begin{tabular}{cc|c|c|c|c|l}
  \cline{3-6}
  & & \multicolumn{4}{ c| }{Primes} \\ \cline{3-6}
  & & 2 & 3 & 5 & 7 \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{504} & 3 & 2 & 0 & 1 & \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{540} & 2 & 3 & 1 & 0 & \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{gcd} & 2 & 2 & 0 & 0 & min \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{lcm} & 3 & 3 & 1 & 1 & max \\ \cline{1-6}
\end{tabular}
```

Der Befehl `\multicolumn{1}{` wird verwendet, um sowohl vertikale linke als auch rechte Ränder zu zeichnen. Obwohl es mit `\multirow{2}{*}{...}` kombiniert wird, zeichnet es immer noch vertikale Ränder, die nur die erste Zeile umfassen. Um dies zu kompensieren, fügen wir `\multicolumn{1}{` in den folgenden Zeilen hinzu, die von „mutltirow“ überspannt werden.

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-15.jpg)</a>

## 5. Tischgröße

Das „graphicx“-Paket stellt den Befehl `\resizebox{width}{height}{object}` bereit, der mit der `tabular`-Umgebung verwendet werden kann, um eine Tabelle auf eine bestimmte Breite und Höhe zu strecken oder zu verkleinern. Im folgenden Beispiel ändern wir die Größe der Tabelle auf 12 cm Breite und behalten dabei das Seitenverhältnis bei.

```tex
\resizebox{12cm}{!} {
  \begin{tabular}{|c|c|c|}                           \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
}
```

<a href="/tex/java/latex-tables/latex-tables-16.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-16.jpg)</a>

Sie können `\scalebox{ratio}{object}` auch auf die gleiche Weise verwenden, jedoch mit Verhältnissen statt fester Größe:

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```

## 6. Positionierungstische

Sie können eine Tabelle einfach auf einer Seite positionieren, wenn Sie sie in einer „Tabellen“-Umgebung platzieren.

```tex
\begin{table}[positioning_option]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

Verfügbare Positionierungsoptionen sind:

`h` – platziert den Tisch ungefähr *hier*.

`t` – positioniert die Tabelle *oben* auf der Seite.

`b` – positioniert die Tabelle am *unten* der Seite.

`p` – Platzieren Sie die Tabelle auf einer speziellen Seite (nur für Tabellen).

`!` – überschreibt interne LaTeX-Parameter.

`h` – platzieren Sie den Tisch genau an dieser Stelle (ähnlich wie „h!“).

Um eine Tabelle horizontal zu zentrieren, können Sie der `tabular`-Umgebung den Befehl `\centering` innerhalb einer `table`-Umgebung voranstellen.

## 7. Bildunterschriften, Etiketten und Referenzen

Sie können eine Tabelle mit Text beschriften. In der Ausgabe wird dem Text *Tabelle N.* vorangestellt, wobei *N* die entsprechende Tabellennummer ist, die von LaTeX automatisch verfolgt wird. Verwenden Sie dazu den Befehl `\caption`. Es ist auch möglich, einer Tabelle eine Beschriftung zuzuweisen, sodass die Tabelle von überall im Dokument aus referenziert werden kann. Das entsprechende Befehlspaar ist `\label` und `\ref`. Betrachten Sie das folgende Beispiel:

```tex
Table \ref{table:1} is an example of a referenced \LaTeX{} element.

\begin{table}[h!]
  \centering
  \begin{tabular}{|c|c|c|} \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
  \caption{A caption for the table.}
  \label{table:1}
\end{table}
```

Dabei wird die Referenz in der ersten Zeile automatisch durch die durch den Befehl `\label` festgelegte Nummer ersetzt.

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-17.jpg)</a>

## 8. Maltabellen

### Farben in Tabellenzeilen ändern

Das Paket `xcolor` stellt die notwendigen Befehle bereit, um Tabellen mit alternativen Zeilenfarben zu erstellen. Das Paket muss mit der Tabellenoption geladen werden: `\usepackage{table]{xcolor}`.
Der Befehl `\rowcolors{starting_row}{odd_color}{even_color}` muss erfolgen, bevor die `tabular`-Umgebung startet.

```tex
\begin{center}
  \rowcolors{2}{green}{pink}

  \begin{tabular}{lll}
    \multicolumn{3}{c}{The header} \\
    odd & odd & odd \\
    even & even & even\\
    \hiderowcolors odd & odd & odd \\
    \showrowcolors even & even & even\\
     even & even & even\\
  \end{tabular}
\end{center}
```

Der Befehl `\hiderowcolors`, der im Paket `xcolor` bereitgestellt wird, deaktiviert die Hervorhebung ab der Zeile, in der sie auftritt, bis zum Ende der Tabelle. Um die Hervorhebung wieder zu aktivieren, verwenden Sie den Befehl `\showrowcolors`.

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### Einfärben einzelner Zellen

Mit dem Paket `xcolor` können Sie auch die Farbe einer bestimmten Zelle angeben.

```tex
\begin{tabular}{|l|l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  \cellcolor{red} odd & odd & odd \\
  \hline
  even & \cellcolor{red} even & even\\
  \hline
  odd & odd & \cellcolor{red} odd \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-19.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-19.jpg)</a>

### Verwendung des Pakets `colortbl`.

Das Paket `colortbl` stellt den Befehl `\columncolor` bereit, um die Spaltenfarbe in der Präambel einer tabellarischen Umgebung innerhalb des Konstrukts `>{...}` anzugeben. Das bedeutet, dass Sie auch das Paket `array` enthalten müssen. (Vergessen Sie nicht, auch das Paket `xcolor` einzuschließen.)

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-20.jpg)</a>

Mit dem Befehl `\rowcolor` können die Zeilenfarben angegeben werden. Es muss am Anfang der Zeile verwendet werden. Der Befehl hat die gleiche Syntax wie `\columncolor`.

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

Sie können auch vertikale Linien einfärben. Zum Beispiel, 

```tex
\setlength{\arrayrulewidth}{2pt}
\begin{tabular}{!{\color{blue}\vline} l !{\color{blue}\vline} l !{\color{blue}\vline}
    l !{\color{blue}\vline}}
  \multicolumn{3}{c}{The header} \\
  odd & odd & odd \\
  even & even & even\\
  odd & odd & odd \\
\end{tabular}
```

wird dazu führen

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

Beachten Sie die Verwendung von `\setlength{\arrayrulewidth}{2pt}` zum Ändern der Liniendicke.

Allerdings ist das Färben von `\hline` und `\cline` etwas kniffliger und mit zusätzlichen Befehlen möglich (die dann auch für vertikale Linien gelten). Der Befehl `\arrayrulecolor` kann global oder innerhalb einer Tabelle verwendet werden. In beiden Fällen wirkt es sich auf alle nachfolgenden Regeln aus. Wenn Sie also eine andere Farbe für vertikale Linien wünschen, sollten Sie diese in der Tabellenpräambel angeben. Zum Beispiel,

```tex
\setlength\arrayrulewidth{2pt}
%\arrayrulecolor{blue} % to set the color for all rules
\begin{tabular}{|l!{\color{green}\vline}l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  odd & odd & odd \\
  \arrayrulecolor{blue} \hline
  even & even & even\\
  \hline
  odd & odd & odd \\ \arrayrulecolor{red}
  \hline
\end{tabular}
```

wird dazu führen

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-23.jpg)</a>

## 9. Lange Tische bauen

Die tabellarische Umgebung hat einen wesentlichen Nachteil. Es erstellt Tabellen, die mit dem integrierten Seitenumbruchalgorithmus von TeX nicht auf Seiten aufgeteilt werden können. Wenn Ihre Tabelle also lang ist, reicht sie einfach bis unter den Seitenrand.

Glücklicherweise gibt es das Paket `longtable`, das heutzutage in den meisten Distributionen enthalten ist und die `longtable`-Umgebung für den Umgang mit solchen langen Tabellen definiert. In den meisten Punkten funktioniert diese Umgebung auf die gleiche Weise wie die `tabellarische` Umgebung. Es gibt jedoch einige Unterschiede.

Im folgenden Beispiel demonstrieren wir die meisten Funktionen der `longtable`. Dort finden Sie auch Hinweise zur Verwendung und Unterschiede zur `tabular`-Umgebung. (Das Beispiel verwendet auch das Paket `verbatim` für einige Textformatierungen, daher muss es ebenfalls enthalten sein.)

```tex
\begin{longtable}{|r||p{1in}|}
  \caption[An optional table caption ...]{A long table\label{long}}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of the table}\\
  \textsc{First}&\textsc{Second}\\
  \hline\hline
  \endfirsthead % Everything above this command will appear at the beginning of the table, in the first page.

  \caption[]{(continued)}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of every other page}\\
  \textbf{First}&\textbf{Second}\\
  \hline\hline
  \endhead % Whatever you put before this command and below \endfirsthead will be displayed at the top of the table in every page except the first one.

  \hline
  This goes at the&bottom.\\
  \hline
  \endfoot % What you put after \endhead and before this command will appear at the bottom of the table in every page except the last one.

  \hline
  These lines will&appear\\
  in place of the & usual foot\\
  at the end& of the table\\
  \hline
  \endlastfoot % The elements after \endfoot and before this command will be displayed at the bottom of the table but only in the last page where the table appears.

  \texttt{longtable} columns are specified& in the \\
  same way as in the \texttt{tabular}& environment.\\
  \verb!|r||p{1in}|! & inthis case. \\
  Each row ends with a & \verb|\\| command. \\
  The \verb|\\| command has an & optional \\
  argument, just as in & the \\
  \texttt{tabular} & environment. \\ [10pt]
  See the effect of \verb|\\[10pt]| & ? \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Also \verb|\hline| may be used, & as in \texttt{tabular}. \\
  \hline
  That was a \verb|\hline| & . \\
  \hline\hline
  That was a \verb|\hline\hline| & . \\
  \multicolumn{2}{||c||}
    {This is a \texttt{\textbackslash multicolumn\{2\}\{||c||\}}} \\
  If a page break occurs at a \verb|\hline| then & a line is drawn \\
  at the bottom of one page and at the & top of the next. \\
  \hline
  The \texttt{[t] [b] [c]} argument of \texttt{tabular} & cannot be used. \\
  The optional argument may be one of & \texttt{[l] [r] [c]} \\
  to specify whether the table should be & adjusted \\
  to the left, right, & or centrally. \\
  \hline\hline
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Some lines may take up a lot of space, like this: &
  \raggedleft This last column is a ``p'' column so this ``row'' of the table can take
  up several lines. Note however that \TeX will never break a page within such a row.
  Page breaks only occur between rows of the table or at \verb|\hline| commands.
  \tabularnewline
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  \hline
  Lots of lines& like this.\\
  Lots of lines& like this.\\
\end{longtable}
```

Dies führt zu zwei Seiten:

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-24.jpg)</a>

<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

Seien Sie nicht verwirrt, wenn Sie nach dem ersten Durchlauf von TeX nicht das gleiche Ergebnis erhalten. Aufgrund der technischen Einschränkungen von TeX kann es einige Durchläufe dauern, bis die in den Bildern gezeigte Tabelle angezeigt wird.

## 10. Ein komplexes Tabellenbeispiel

Wir werden ein weiteres recht komplexes Beispiel für eine Tabelle bereitstellen, die viele der oben genannten Funktionen vereint.

```tex
\documentclass{article}
  \usepackage{dcolumn}
  \usepackage{verbatim}
  \usepackage{colortbl}
  \usepackage[table]{xcolor}
  \usepackage{longtable}
\begin{document}
  \hbox{}\vspace{100pt} % To make the table break between pages

  \newcolumntype{A}{>{\color{white}\columncolor{red}[.5\tabcolsep]\raggedright}
    p{2cm}}
  \newcolumntype{B}{>{\columncolor{blue}[.5\tabcolsep]\color{yellow}\raggedright}
    p{3cm}}
  \newcolumntype{C}{>{\columncolor{yellow}[.5\tabcolsep]}D{.}{\cdot}{-1}}
  \newcolumntype{E}{>{\large\bfseries \columncolor{cyan}[.5\tabcolsep]}c}
  \newcolumntype{F}{>{\color{white} \columncolor{magenta}[.5\tabcolsep]}c}
  \newcolumntype{G}{>{\columncolor[gray]{0.8}[.5\tabcolsep][\tabcolsep]}l}
  \newcolumntype{H}{>{\columncolor[gray]{0.8}}l}
  \newcolumntype{I}{>{\columncolor[gray]{0.8}[\tabcolsep][.5\tabcolsep]}D{.}{\cdot}
    {-1}}
  \setlength\minrowclearance{2pt} %Before starting give a little space

  \begin{longtable}{ABC}
    \multicolumn{3}{E}{A long table example} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endfirsthead

    \multicolumn{3}{E}{A long table example (continued)} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endhead

    \multicolumn{3}{E}{Continued\ldots}
    \endfoot

    \multicolumn{3}{E}{The End}
    \endlastfoot

    P-column & and another one & 12.34 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6}\\
    Some long text in the first column & bbb & 1.2 \\
    aaa & and some long text in the second column & 1.345 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6} \\
    aaa&bbb & 1.345 \\
    Note that the colored rules in all columns stretch to accommodate large entries
      In one column. & bbb & 1.345 \\
    aaa & bbb & 100 \\
    aaa & Depending on your driver you may get unsightly gaps or lines
      where the `screens' used to produce different shapes interact
      badly. You may want to cause adjacent panels of the same color by
      specifying a larger overhang or by adding some negative space (in a
      \verb|\noalign| between rows. & 12.4 \\
    aaa & bbb & 45.3 \\
  \end{longtable}
\end{document}
```

Vor der `longtable`-Umgebung definieren wir Spaltentypen mit dem Befehl „\newcolumntype“, der vom Paket `dcolumn` bereitgestellt wird. Innerhalb der Argumente verwenden wir die Notation `>{...}`, um Spaltenformate zu definieren. Die Spaltendefinitionen wiederum verwenden Befehle zur Angabe von Farben, Ausrichtung, Schriftarten und Spaltenbreiten. Die `longtable`-Umgebung selbst ist ein weiteres eingesetztes Feature. Innerhalb der Umgebung verwenden wir den Befehl `\multicolumn`, um Zellen horizontal zusammen mit den zuvor definierten Spaltentypen zusammenzuführen.

Das Ergebnis aller Bemühungen ist unten:

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-26.jpg)</a>

<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![Beispielausgabe](/tex/images/java/tutorial/latex-tables-27.jpg)</a>

## 11. Best Practices und Tipps

Das Setzen von Tabellen in LaTeX kann eine differenzierte Aufgabe sein, aber die Befolgung von Best Practices und Tipps kann Ihnen dabei helfen, klare, ästhetisch ansprechende und professionell aussehende Tabellen zu erstellen. Hier finden Sie einige wertvolle Best Practices und Tipps zum Setzen von Tabellen in LaTeX:

1. **Verwenden Sie aussagekräftige Spaltenüberschriften:**
   - Geben Sie für jede Spalte klare und beschreibende Überschriften an, um den Lesern das Verständnis des Inhalts zu erleichtern.
   
2. **Numerische Daten am Dezimalpunkt ausrichten:**
   - Richten Sie bei der Darstellung numerischer Daten die Zahlen am Dezimalpunkt aus, um die Lesbarkeit zu verbessern. Zu diesem Zweck können Sie das Paket `dcolumn` verwenden.
   
3. **Vermeiden Sie vertikale Ranken**:
   - In Fachpublikationen wird oft empfohlen, die Verwendung vertikaler Linien zur Trennung von Spalten zu vermeiden. Verwenden Sie horizontale Linien aus Gründen der Klarheit sparsam.

4. **Konsistenz beibehalten:**
   - Behalten Sie im gesamten Dokument eine einheitliche Formatierung bei, einschließlich Schriftarten, Schriftgrößen und Ausrichtung innerhalb von Tabellen.
   
5. **Zelleninhalt minimieren:**
   - Vermeiden Sie eine Überlastung der Zellen mit übermäßigem Inhalt. Wenn eine Zelle zu viel Text enthält, sollten Sie erwägen, sie in mehrere Zeilen oder Spalten aufzuteilen.
   
6. **Untertitel und Labels hinzufügen:**
   - Fügen Sie über oder unter Ihren Tabellen informative Beschriftungen ein und verwenden Sie den Befehl `\label`, um Querverweise in Ihrem Dokument zu ermöglichen.

7. **Setzen Sie `multirow` und „multicolumn“ sparsam ein:**
    - Während `multirow` und „multicolumn“ zum Zusammenführen von Zellen nützlich sind, vermeiden Sie eine übermäßige Verwendung, da dies die Tabellen komplex und schwerer lesbar machen kann.

8. **Vermeiden Sie übermäßig komplexe Tabellen:**
    - Wenn Ihre Daten für eine einzelne Tabelle zu komplex sind, sollten Sie sie in mehrere kleinere Tabellen aufteilen oder andere visuelle Hilfsmittel wie Grafiken oder Diagramme verwenden.
    
9. **Nutzen Sie den horizontalen Raum mit Bedacht:**
    - Passen Sie den Abstand zwischen den Spalten mit `\setlength{\tabcolsep}{value}` und den Abstand zwischen den Zeilen mit `\renewcommand{\arraystretch}{value}` an, um das Tabellenlayout zu optimieren.

10. **Korrekturlesen Sie Ihre Tabellen:**
    - Lesen Sie Ihre Tabellen sorgfältig Korrektur und überprüfen Sie sie auf Fehler, einschließlich Datengenauigkeit, Formatierung und Ausrichtung.


    
Durch die Umsetzung dieser Best Practices und Tipps können Sie LaTeX-Tabellen erstellen, die nicht nur Ihre Daten effektiv kommunizieren, sondern auch die Gesamtqualität und Professionalität Ihrer Dokumente verbessern.

## 12. Fazit

Wir sind durch die komplexe Welt der Tabellenstrukturen in LaTeX gereist und haben die bemerkenswerte Vielseitigkeit und Präzision dieses Satzsystems entdeckt. Die Fähigkeit von LaTeX, Tabellen nahtlos in Dokumente zu integrieren, ermöglicht es Benutzern, komplexe Daten, Vergleiche und Beziehungen elegant und klar zu kommunizieren.

Von den grundlegenden Konzepten der „tabularen“ Umgebung bis hin zu fortgeschrittenen Techniken mit `multirow`- und `longtable`-Paketen haben wir die Werkzeuge und Strategien untersucht, die LaTeX zu einem Kraftpaket für die Erstellung von Tabellen machen. Wir haben gelernt, wie LaTeX nicht nur unsere Tabellen verschönert, sondern auch die Datenpräsentation optimiert und so zu einer effektiven Kommunikation beiträgt. 

Wir haben die Bedeutung von Best Practices betont: aussagekräftige Spaltenüberschriften, Ausrichtung, richtige Abstände und Konsistenz. Diese Praktiken ermöglichen es uns, Tische zu schaffen, die nicht nur funktional, sondern auch optisch ansprechend und professionell sind.

Denken Sie beim weiteren Erkunden von LaTeX daran, dass das Beherrschen von Tabellenstrukturen sowohl eine Kunst als auch eine Wissenschaft ist. Es handelt sich um eine Fähigkeit, die die Wirkung Ihrer wissenschaftlichen Arbeiten, Berichte und Präsentationen erheblich steigern kann. 

Bringen Sie Ihre Dokumente also mit dem Wissen über die Tabellenfunktionen von LaTeX auf die nächste Stufe. Experimentieren, verfeinern und innovieren Sie im Bereich der Tabellenstrukturen und lassen Sie LaTeX Ihr vertrauenswürdiger Begleiter bei der Erstellung von Dokumenten sein, die Informationen effektiv, schön und professionell vermitteln.