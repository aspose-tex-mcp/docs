---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX-Dokumentklassen
title: LaTeX-Dokumentklassen
weight: 20
url: /java/latex-document-classes/
keywords: Latex-Artikelklasse, Latex-Dokumentklasse, Latex-Dokumentvorlage, Latex-Artikel, Latex-Buch, Latex-Folien, Latex-Bericht, Latex-Brief, Dokumentklasse in Latex
description: Dieser Artikel ist eine kurze Zusammenfassung der LaTeX-Dokumentklassen und ihrer Optionen. Es enthält auch einige Beispiele.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Was ist eine Dokumentklasse in LaTeX?

LaTeX definiert einige Regeln, die jeder Dokumentautor befolgen muss. Es definiert auch die Struktur der Quelldatei, bei der es sich im Wesentlichen um ein Satzprogramm handelt. Gemäß dieser Struktur muss der Quellcode des Dokuments einen Teil enthalten, der für den Inhalt des Dokuments selbst verantwortlich ist – *body* – der in ein Befehlspaar eingeschlossen ist: `\begin{document}` und `\end{document}`. LaTeX ignoriert alles, was auf das Ende des Körpers folgt. Der Teil des Quellcodes vor `\begin{document}` wird *Präambel* genannt.

Normalerweise muss der erste Befehl in der Präambel `\documentclass` lauten, was ein einzelnes erforderliches Argument erfordert, nämlich den Namen der **Dokumentklasse**. Die Dokumentklasse selbst ist eine Reihe von Formatierungsparametern, Layoutmetriken, Makros usw., die für die Entwicklung von Dokumenten eines bestimmten Typs geeignet und nützlich sind und unter einem einzigen Namen zusammengefasst werden. In diesem Artikel besprechen wir die in LaTeX integrierten **vordefinierten** Dokumentklassen von LaTeX und zeigen deren Verwendung, Unterschiede und Gemeinsamkeiten. Wir werden auch einige optionale Argumente erwähnen, die der Befehl `\documentclass` annehmen kann und die das Erscheinungsbild des Dokuments anpassen.

## Vordefinierte LaTeX-Dokumentklassen

Das Standard-LaTeX enthält die folgenden Dokumentklassen:

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **Artikel** | Die LaTeX-Artikelklasse wird zum Erstellen von Artikeln für wissenschaftliche Zeitschriften, Kurzberichte, Programmdokumentationen und im Allgemeinen für jedes kurze Dokument verwendet, das keine komplexe Unterteilung in Kapitel und Teile benötigt. |
| **Bericht** | Die LaTeX-Berichtsklasse wird für lange Artikel verwendet, die mehrere Kapitel enthalten können (etwa kleine Bücher und Abschlussarbeiten). |
| **Buch** | Wird zum Setzen echter Bücher verwendet. Es umfasst alle Arten von Satzstandards, die für gedruckte Bücher geeignet sind: Kapitel und Teile, zwei Arten von Seiten, Titelei, Nachspann usw.|
| **Folien** | Kann zum Erstellen von Folien verwendet werden, obwohl es das externe Paket [Beamer](https://ctan.org/pkg/beamer) gibt, das für diesen Zweck viel leistungsfähiger ist. |
| **Brief** | Diese Dokumentklasse wird zum Schreiben von Briefen verwendet. |

Die ersten beiden Dokumentklassen sind grundlegend. Beginnen Sie also mit **Artikel**, wenn Sie nicht sicher sind, welche Klasse Sie benötigen.

Die Klasse **report** ist sehr ähnlich. Der Hauptunterschied zu **article** besteht darin, dass Sie Kapitel mit dem Befehl `\chapter` einfügen können, während die Dokumentklasse **article** keine solche Abschnittseinheit definiert.

## Die LaTeX-Buchklasse

In typografischen Standards haben Bücher ein Vorderteil und ein Hinterteil, die den Hauptunterschied zwischen Büchern und beispielsweise Berichten oder Artikeln ausmachen. Das Titelblatt eines Buches besteht normalerweise aus einer Halbtitelseite, einer Haupttitelseite, einer Copyright-Seite, einem Vorwort oder Vorwort und einer Inhaltstabelle. Weniger obligatorische Teile sind Danksagungen, eine Widmung, ein Abbildungsverzeichnis, ein Tabellenverzeichnis, eine Liste anderer Bücher derselben Reihe sowie andere redaktionelle und werbliche Inhalte. Der Hintergrundtext umfasst typischerweise ein Index und kann ein Nachwort sowie Danksagungen, eine Bibliographie, ein Kolophon usw. enthalten.

Die Buchdokumentklasse bietet Ihnen Befehle zum Erstellen der oben genannten logischen Strukturen, während andere Dokumentklassen Ihnen solche Werkzeuge nicht zur Verfügung stellen können. Verschiedene Herausgeber verfügen jedoch in der Regel über eigene Pakete mit zusätzlichen Befehlen zum Gestalten von Strukturen nach ihrem eigenen Stil.

## Befehle für Vordermaterie, Hauptmaterie und Hintermaterie

Die Hauptsache ist, was den Hauptteil des Buches umfasst, beginnend mit dem ersten Kapitel oder Teil und endend mit den Anhängen. Die Vor-, Haupt- und Rückangelegenheiten beginnen jeweils mit den Befehlen „\frontmatter“, „\mainmatter“ und „\backmatter“.

> In der Standardbuchklasse werden die Titelseiten mit römischen Ziffern nummeriert, während die Haupt- und Nachspannseiten mit arabischen Ziffern nummeriert werden.

> Der Befehl `\chapter` erzeugt keine Kapitelnummer im Titel und Nachspann, obwohl er einen Eintrag im Inhaltsverzeichnis erstellt. Dies wird normalerweise verwendet, um ein Vorwort oder einen Danksagungsabschnitt zu erstellen. Innerhalb solcher Kapitel sollten nur die mit Sternchen versehenen Versionen anderer Abschnittsbefehle (wie `\section*` und `\subsection`) verwendet werden.

## Ein Beispiel für die Verwendung der LaTeX-Buchklasse

```tex
% Book document class
\documentclass{book}

\title{My first book}
\author{Me}
\date{\today}

\begin{document}

\maketitle

\frontmatter
\chapter{Dedication}
\chapter{Copyright}
\chapter{Acknowledgements}

\tableofcontents

\listoffigures
\listoftables

\mainmatter
\part{The first part}
\chapter{Chapter one}
\chapter{Chapter two}

\part{Last part}
\chapter{Chapter three}

\appendix
\chapter{First and only appendix}

\backmatter
\chapter{Bibliography}
\chapter{Other titles in this collection}

\end{document}
```

Unten ist die von diesem LaTeX-Code generierte Dokumentstruktur:

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![Beispielausgabe](/tex/images/java/tutorial/latex-document-classes-1.png) </a>
<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![Beispielausgabe](/tex/images/java/tutorial/latex-document-classes-2.png) </a>

Und hier das Inhaltsverzeichnis im Detail:

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![Inhaltsverzeichnis](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## **Ungerade** und **gerade** Seiten in Büchern
In Büchern sehen **ungerade** und **gerade** Seiten nicht gleich aus. Die Ränder und in der Regel Kopf- und Fußzeilen sind unterschiedlich, um die Lesbarkeit des Buchs im gebundenen Zustand zu verbessern. Die LaTeX-Dokumentklasse übernimmt dies, und möglicherweise finden Sie Folgendes:

- **linke (gerade)** Seiten haben einen größeren linken Rand, die Seitenzahl befindet sich oben rechts auf der Seite und der Titel des aktuellen Kapitels befindet sich rechts;
- **rechte (ungerade)** Seiten haben einen größeren rechten Rand und nur die Seitenzahl oben rechts auf der Seite.

Beachten Sie, dass neue Kapitel immer auf der rechten Seite beginnen, wobei der Seitenkopf leer ist und nur die Seitenzahl in der Mitte des Fußes verbleibt.

## Der Abschnitt **Zusammenfassung** fehlt

Wissenschaftliche Arbeiten wie Artikel oder Berichte enthalten normalerweise einen einleitenden Abschnitt mit der Bezeichnung **„Zusammenfassung“**. Sein Zweck besteht darin, einen schnellen Überblick über das im Dokument behandelte Thema zu geben. Möglicherweise finden Sie es direkt nach dem Titel und vor dem Inhaltsverzeichnis, wobei die Überschrift „Zusammenfassung“ fett gedruckt ist. In LaTeX wird eine solche Struktur als „abstrakte“ Umgebung implementiert.

Die **Abstract**-Umgebung wird von der Buchdokumentklasse nicht bereitgestellt, und dies ist ein weiterer Unterschied zu den Artikel- und Berichtsklassen.

## LaTeX **Buchstaben**-Klasse

Derzeit scheint die Briefdokumentklasse etwas altmodisch zu sein (genauso wie die Foliendokumentklasse). Wenn Sie herkömmliche Briefe verfassen, diese in Umschläge stecken und per Post versenden müssen, wird Ihnen diese Dokumentenklasse wahrscheinlich nützlich sein. Obwohl es sich dabei um eine Art veraltete Kommunikationsform handelt, gibt es immer noch Fälle, in denen Sie möglicherweise ein briefähnliches Dokument vorbereiten müssen. Zum Beispiel ein Empfehlungsschreiben oder ein Präsentationsschreiben.

Hier also der kurze Überblick über die Klasse.

Mit einer einzigen Eingabedatei können Sie beliebig viele Briefe generieren. Ihr Name und Ihre Adresse, die in der Regel für alle Briefe gleich sind, werden in der Regel in der Präambel des Dokuments angegeben. Die Rücksprungadresse wird durch einen „\address“-Befehl deklariert, der mehrere durch „\\“ (den LaTeX-Zeilenumbruchbefehl) getrennte Zeilen als Argument akzeptiert. Ebenso akzeptiert der Befehl „\signature“ mehrere Zeilen, einschließlich Ihres Namens, Titels usw. Sie können die Absenderadresse und Signatur jedoch jederzeit ändern.

Jeder Brief wird von einer separaten „Brief“-Umgebung generiert, die als Argument den Namen und die Adresse des Empfängers benötigt. Der Brief beginnt mit einem „\opening“-Befehl, der die Anrede erzeugt, und endet mit einem „\closing“-Befehl, der den Schlusssatz und die Signatur erzeugt. Der Textkörper des Briefes ist eine normale LaTeX-Eingabe.

Alle diese Befehle sind einfach zu verwenden und sehr leistungsstark, da LaTeX die Formatierung der Buchstaben automatisch übernimmt. Lassen Sie sich also nicht von der Anzahl der Befehle abschrecken oder verwirren.

Das folgende Beispiel zeigt, wie das alles funktioniert.

```tex
% Example of a letter document class
\documentclass{letter}
 
\address{1234 Heart Avenue\\ Thoraxland, 12555}

\signature{Dr.~Lung\\ Head of Department}

\begin{document}

\begin{letter}
{Dr.~Gallbladder \\ University of Digestion\\ 66 Liver Street\\ Abdomenia, 45888}

\opening{Appreciated Anything,}

I write you a letter, and this is the body of the
letter.

\closing{I look forward to your reply,}

\end{letter}

\end{document}
```

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![Ein Beispiel für eine Briefdokumentklasse](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

Beachten Sie, dass auch das aktuelle Datum automatisch erzeugt wird. Sie können jedoch den Befehl „\today“ umdefinieren, um das Datum in Ihren Briefen zu ändern. So machen Sie es:

```tex
\renewcommand{\today}{01th of March of 2492}
```

Wenn Sie diese Erklärung in eine bestimmte „Brief“-Umgebung einfügen, ändert sich dadurch nur das Datum für diesen Brief. Wenn Sie es andernfalls in die Präambel einfügen, gilt es für alle von der Eingabedatei generierten Buchstaben (es sei denn, es wird in eine bestimmte „Buchstaben“-Umgebung eingefügt).

## Optionen für LaTeX-Dokumentklassen

Werfen wir nun einen Blick auf die am Anfang des Artikels erwähnten Befehlsoptionen `\documentclass`.

### Schriftgröße

Die Schriftgröße wird durch drei Optionen gesteuert: 10pt, 11pt, 12pt. Standardmäßig gilt 10pt. Diese Optionen bestimmen die im gesamten Dokument verwendete Grundschriftgröße, sofern diese nicht irgendwann geändert wurde. Sie wirken sich auch auf die Skalierungsfaktoren für einige Formatierungsdimensionen aus.

```tex
\documentclass[12pt]{article}
```

> Diese Optionen sind für die Klasse „Slides“ nicht erkennbar.

### Papierformat
„Papiergröße“ bezieht sich hier auf die Größe des Papierblatts, auf dem Sie das Dokument drucken möchten. Es hat keinen Einfluss auf die Größe der Seitendarstellung in der Ausgabe von Satzsystemen wie **PDF TeX**. Die Steuerung erfolgt über 6 Optionen: „Briefpapier“ (8,5 Zoll x 11 Zoll), „Rechtspapier“ (8,5 Zoll x 14 Zoll), „Executive-Papier“ (7,25 Zoll x 10,5 Zoll), „A4-Papier“ (210 mm x 297 mm), „A5-Papier“. ` (148mm x 210mm) und `b5paper` (176mm x 250mm). Der Standardwert ist „Briefpapier“.

```tex
\documentclass[a4paper]{article}
```

### Seitenausrichtung

Mit der Option „Querformat“ wird die Ausgabe für den Querformatdruck auf dem ausgewählten Papierformat formatiert. Tatsächlich sorgt es dafür, dass LaTeX die Breiten- und Höhenmaße überall dort austauscht, wo sie im Schriftsatzprozess verwendet werden. Die Option „Hochformat“ hat keinen solchen Effekt und wird standardmäßig verwendet.

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### Entwurfsmodus

Wenn TeX beim Erstellen eines Absatzes keinen ausreichend guten Zeilenumbruch erzielen kann (es verfügt über einen Algorithmus zur Schätzung der Güte), erzeugt es eine Linie, die sich über den rechten Rand des Textbereichs erstreckt. Darüber hinaus werden solche Vorfälle in der Transkriptdatei (und am Terminal) mit der Warnung „überfüllte Kästchen“ gemeldet. Die Option „Entwurf“ bewirkt, dass LaTeX solche Zeilen in der Ausgabe mit schwarzen Kästchen markiert. Die Option „final“ erzeugt keine Blackbox und wird standardmäßig verwendet.

### Zweiseitiger Druck

Mit der Option „openany“ können Kapitel auf jeder Seite beginnen, während mit der Option „openright“ alle Kapitel auf einer rechten Seite beginnen. Der Standardwert ist „openany“ in der Klasse „report“ und „openright“ in der Klasse „book“. Beide Optionen werden in anderen Dokumentklassen nicht erkannt.

### Seite für den Titel

Mit der Option „titlepage“ erstellt LaTeX eine separate Seite für den Titel, der durch den Befehl „\maketitle“ erstellt wurde. Es bewirkt außerdem, dass die „Abstract“-Umgebung die Zusammenfassung auf einer neuen Seite beginnt und danach einen Seitenumbruch einfügt. Der Standardwert ist „titlepage“ für alle Klassen außer „article“, für den es „notitlepage“ ist. 

> Diese Optionen werden von der Klasse „Letter“ nicht erkannt.

### Nummerierte angezeigte Formeln

Die Option „leqno“ bewirkt, dass LaTeX Gleichungszahlen (angezeigte mathematische Formeln) oder Tags auf der linken Seite anstelle der rechten Seite einfügt, was das Standardverhalten ist.

### Angezeigte Formelausrichtung

Die Option „fleqn“ richtet die angezeigten Formeln linksbündig aus. Andernfalls sind sie standardmäßig zentriert.
