---
translation: true
template: /templates/_template-java.md
linktitle: Eingabe und Ausgabe
title: 1. Eingabe- und Ausgabekodierungen
weight: 10
url: /java/latex-font-encodings/
keywords: Latex, Latex-Schriftarten, Latex-Schriftkodierungen, NFSS
description: In diesem Artikel werden kurz die Konzepte der Eingabe- und Ausgabekodierungen in LaTeX erläutert. Es erwähnt auch das New Font Selection Scheme (NFSS).
lastmod: "2024-09-26"
---

{{<section overview>}}

Wenn wir eine Taste auf einer Tastatur drücken, wird ein numerischer Code generiert, der ein bestimmtes Zeichen darstellt. Eine Eingabekodierung ordnet ein Zeichen dem entsprechenden Code zu. Beispielsweise können auf einer deutschen Tastatur Akzentzeichen (z. B. „a-Umlaut“-Zeichen) unter verschiedenen Betriebssystemen unterschiedlichen Codes zugeordnet werden.

Ein in einer Computerdatei gespeichertes Dokument enthält nur Zeichencodes, die Informationen zur Eingabekodierung sind jedoch nicht explizit enthalten. Wenn Sie also eine Datei in eine andere Umgebung übertragen, beispielsweise aus den Vereinigten Staaten in das Vereinigte Königreich, werden Sie möglicherweise feststellen, dass die Dollarzeichen in Ihrem Dokument plötzlich als Pfundsymbole interpretiert werden, wenn Sie Ihre Datei mit einem Programm anzeigen, das dies tut die falsche Annahme über die Eingabekodierung.

Das vom LaTeX-Projektteam entwickelte Paket „inputenc“ sollte bei Problemen mit der Eingabekodierung helfen. Es ermöglicht Benutzern, die für Dokumente oder Teile von Dokumenten verwendete Eingabekodierung explizit anzugeben. Dieser Mechanismus ermöglicht die sichere Übertragung von Dokumenten von einer LaTeX-Installation auf eine andere und erzielt identische Druckergebnisse.

Das Paket „inputenc“ interpretiert Zeichencodes in der Datei und ordnet sie einer *internen LaTeX-Darstellung* zu, die alle in LaTeX darstellbaren Zeichen eindeutig abdeckt. Bei der weiteren Verarbeitung, beispielsweise beim Schreiben in eine Hilfsdatei, verwendet LaTeX diese interne Darstellung und vermeidet so Fehlinterpretationen.

Früher oder später muss LaTeX diese internen Zeichendarstellungen jedoch mit *Glyphen* (Zeichenformen in bestimmten Schriftarten) verknüpfen, sodass eine andere Zuordnung erforderlich ist. Es gibt höchstens 256 Glyphen in jeder TeX-Schriftart. Diese Glyphen werden nicht namentlich angesprochen, sondern durch 8-Bit-Zahlen, die die Positionen der Glyphen in der Schriftart darstellen. Das bedeutet, dass wir von einem großen eindeutigen Namensraum auf mehrere kleine zuordnen müssen, und diese Glyphenpositionen können stark variieren, was nicht überraschend ist.

Auch wenn wir also die Bedeutung des Dollarzeichens aus der externen Datei in den internen Dateien von LaTeX beibehalten haben, könnten wir immer noch falsche Formen auf dem Papier finden, wenn wir zum Drucken eine Schriftart auswählen, die an der Position, von der wir angenommen haben, dass sie für einen Dollar reserviert ist, ein unerwartetes Glyph enthält Zeichen. Eine der Aufgaben von **NFSS** (LaTeXs **New Font Selection Scheme**) besteht darin, sicherzustellen, dass entweder jede LaTeX-interne Zeichendarstellung ordnungsgemäß gerendert wird oder, falls dies aus irgendeinem Grund nicht möglich ist, dass der Benutzer eine erhält richtige Fehlermeldung.

Wenn eine Schriftart Akzentzeichen als einzelne Glyphen enthält und nicht nur Basiszeichen plus Akzente (aus denen TeX intern Akzentzeichen erstellt), ist die Verwendung dieser Glyphen vorzuziehen, da sie normalerweise ein besseres Erscheinungsbild haben. Ein weiterer (technischer) Grund für die Verwendung dieser zusammengesetzten Glyphen besteht darin, dass das Grundelement „\accent“ die Silbentrennung unterdrückt.

Um verschiedenen Fällen gerecht zu werden, muss ein Befehl wie „\'e“ (die interne Darstellung von LaTeX für das Zeichen „e-acute“) manchmal komplizierte Aktionen mit dem Grundelement „\accent“ auslösen, und manchmal informiert er den Absatzersteller einfach darüber benötigt die Glyphe aus einem bestimmten *Slot* (Position) in der aktuellen Schriftart.

All dies wird durch das Konzept der *Ausgabekodierungen* erreicht, bei denen es sich um Zuordnungen der internen Zeichendarstellungen von LaTeX zu geeigneten Glyphenpositionen oder zu Aktionen zum Erstellen von Glyphen handelt, abhängig von den tatsächlichen Glyphen, die in der für den Schriftsatz verwendeten Schriftart verfügbar sind.

In den folgenden Artikeln geht es um Release 2 von NFSS, das 1994 Teil des Standard-LaTeX wurde.