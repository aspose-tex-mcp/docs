---
translation: true
template: /templates/_template-java.md
title: LaTeX eingebettete Grafiken | Aspose.TeX für Java
linktitle: LaTeX-eingebettete Grafiken
weight: 18
url: /java/latex-graphics-embedding/
keywords: includegraphics latex, latex base64-Grafiken einbetten, latex base64-kodierte Grafiken, write18, Shell-Escape, Latex-Shell-Befehl
description: Im Artikel erfahren Sie, wie Sie Base64-codierte Bilder in den LaTeX-Quellcode einfügen und lernen die \write18-Funktion kennen, die dies ermöglicht.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Eine alternative Möglichkeit, Bilder einzubinden

Einige TeX/LaTeX-Systeme ermöglichen die Einbindung von Bildern, die nicht extern relativ zur LaTeX-Datei selbst gespeichert sind; Stattdessen werden diese Bilder direkt in die LaTeX-Datei eingebettet. Da TeX/LaTeX-Dateien jedoch reiner Text sind und keine Binärdaten enthalten können, benötigen wir eine Methode, um Binärdaten in einem Textformat darzustellen. Das bedeutet, dass Binärdaten in eine Textdarstellung kodiert werden müssen. Die Herausforderung besteht darin, dass eine TeX-Engine diese codierten Bilder nicht direkt interpretieren kann. Am Ende werden Bilder mit dem bekannten Befehl `\includegraphics` aus dem Paket „graphicx“ eingebunden, dieser Befehl ist jedoch auf die Verarbeitung externer Bilddateien beschränkt. Daher muss weiterhin eine externe Bilddatei (zusammen mit einer zusätzlichen Zwischendatei) außerhalb der LaTeX-Datei erstellt werden, dies geschieht jedoch nur beim Schriftsatz. Der Vorteil besteht darin, dass Sie nur die LaTeX-Datei selbst verteilen müssen und nicht eine Reihe von Dateien.

Okay, nehmen wir an, wir haben irgendwie ein codiertes Bild in die LaTeX-Datei eingebettet. Wie entschlüsseln wir dieses Bild? Leider können wir es nicht direkt dekodieren, indem wir es aus der LaTeX-Datei lesen und in eine externe Bilddatei schreiben. Stattdessen muss die Textzeichenfolge, die das codierte Bild darstellt, zunächst in eine externe Textdatei geschrieben werden, die dann dekodiert werden kann, um die Bilddatei zu generieren.

An dieser Stelle können wir die folgenden Schritte skizzieren, um das gewünschte Ergebnis zu erzielen:

1. Kodieren Sie das Bild.
2. Fügen Sie die Textzeichenfolge, die die Bilddaten darstellt, in die LaTeX-Datei ein.
3. Schreiben Sie die Textzeichenfolge, die die Bilddaten darstellt, in eine externe Datei.
4. Dekodieren Sie die in Schritt 3 erstellte externe Datei.
5. Fügen Sie das dekodierte Bild ein.

Die ersten beiden Schritte werden vom Autor der LaTeX-Datei durchgeführt. Die TeX-Engine übernimmt natürlich die restlichen Schritte, sofern sie ordnungsgemäß angewiesen wird.

Fahren wir mit **Schritt 1** fort. Wie können wir unser Bild kodieren, um eine Zeichenfolge zu erhalten? Eine der Methoden hierfür (und wahrscheinlich die beliebteste) ist **Base64**.

## Codierung von Binärdaten mit Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) ist eine Gruppe von Binär-zu-Text-Codierungsschemata, die Binärdaten mithilfe eines Satzes von 64 eindeutigen Zeichen in eine Folge druckbarer Zeichen umwandelt. Konkret werden die Quellbinärdaten in Gruppen von 6 Bits verarbeitet, wobei jede Gruppe einem von 64 eindeutigen Zeichen zugeordnet wird. Wie alle Binär-zu-Text-Kodierungsschemata soll Base64 die Übertragung von in Binärformaten gespeicherten Daten über Kanäle erleichtern, die überwiegend Textinhalte unterstützen.

Diese kurze Erklärung zeigt, dass **Base64** genau das ist, was wir brauchen. Um eine Bilddatei in **Base64** zu kodieren, können Sie ein Befehlszeilenprogramm (sofern auf Ihrem Betriebssystem verfügbar), Standard- oder Drittanbieterfunktionen nahezu jeder Programmiersprache oder Online-Tools wie [Base64.guru](https://base64.guru/converter/encode/file) oder ähnlich.

## Einbetten des codierten Bildes in die LaTeX-Datei

Die aus dem Kodierungsprozess generierte Zeichenfolge muss wie folgt in der Standard-LaTeX-Umgebung „filecontents*“ in der Präambel einer LaTeX-Datei platziert werden:

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Hier ist es! **Schritt 2** ist abgeschlossen. Wir haben das Bild erfolgreich in die LaTeX-Datei eingebettet! Aber was passiert, wenn wir den Satz dieser Datei mit LaTeX ausführen?“
Ein LaTeX-Prozessor schreibt die Zeichenfolge aus der Umgebung in eine externe Datei mit dem Namen „sample-image.64“. Aufgrund der Option „Überschreiben“ wird die Datei überschrieben, wenn sie bereits existiert (z. B. wenn sie während eines vorherigen Laufs erstellt wurde). So gelingt auch **Schritt 3**!

## Dekodierung einer Base64-Zeichenfolge

**Schritt 4** unseres Plans ist, wo die Unterschiede in den TeX-Implementierungen ins Spiel kommen. Das Dekodieren einer Base64-Zeichenfolge erfolgt mithilfe einer häufigeren Funktion, die als „\write18“-Funktion bekannt ist.

### `\write18`

In klassischen TeX-Engines ist „\write<Nummer>(<Token-Liste>)“ das Grundelement, das zum Schreiben einer *Liste von Token* verwendet wird. Bei Verwendung folgt auf dieses Grundelement eine Ganzzahl. Wenn die Ganzzahl negativ ist, werden die Token in die Transkriptdatei (Protokolldatei) geschrieben. Wenn die Ganzzahl größer als „15“ ist, werden die Token an das Terminal gesendet. Wenn die Ganzzahl im Bereich von „0..15“ liegt, werden die Token in eine Datei geschrieben, deren Name durch ein vorangehendes Vorkommen des Primitivs `\openout` angegeben wird. Das Grundelement „\openout<4-Bit-Ganzzahl>=<Dateiname>“ verknüpft einen Dateinamen mit einer Zahl.

Neuere TeX-Implementierungen, wie z. B. PDF TeX, ermöglichen die Verwendung von „\write18“. In diesem Fall interpretieren sie die „<token list>“ als Befehlszeile, die in der Betriebssystem-Shell ausgeführt werden soll. Da diese Funktion offensichtlich ein potenzielles Sicherheitsrisiko darstellt, könnten Sie einen Hauch von Geheimnis verspüren, wenn in der TeX-bezogenen Dokumentation oder im Internet darauf verwiesen wird. Aus diesem Grund bieten die ausführbaren Dateien von PDF TeX/LaTeX Befehlsoptionen zur Steuerung des Zugriffs auf diese Funktion.

Typischerweise gibt es drei Stufen der Barrierefreiheit: deaktiviert, aktiviert mit Einschränkungen und vollständig aktiviert.

In **Aspose.TeX** gibt es eine TeX-Joboption namens „ShellMode“, die einen von zwei möglichen Werten annehmen kann: „NoShellEscape“ und „ShellRestricted“. Der Wert „NoShellEscape“ gibt an, dass die Funktion deaktiviert ist. Der letztgenannte Wert bedeutet, dass jeder Befehl, der ausgeführt werden muss, vom Benutzer als Erweiterung der Klasse „Executable“ implementiert werden muss. Wir werden hier nicht auf die Einzelheiten solcher Implementierungen eingehen, aber es ist wichtig zu beachten, dass die Befehlsemulation „base64“ bereits in Aspose.TeX implementiert und standardmäßig in der Sammlungseigenschaft „Executables“ der Klasse „TeXOptions“ enthalten ist Beispiel.

### Base64-kodierte Daten dekodieren

Um den Inhalt einer Datei zu dekodieren, von der erwartet wird, dass sie Base64-kodierte Daten enthält, verwenden wir normalerweise die folgende Befehlszeile:


```
base64 -d  FILE1 > FILE2
```

Dabei ist FILE1 die „codierte“ Datei und „> FILE2“ leitet die Ausgabe in die Datei „FILE2“ um.

Daher sollten wir die folgende Zeile in den Hauptteil unserer LaTeX-Datei einfügen:


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> Das Präfix `\immediate` ist erforderlich, um sicherzustellen, dass die Operation `\write` sofort ausgeführt wird, wenn der TeX-Scanner auf dieses Primitiv trifft. Andernfalls wird es während der Seitenausgabe verarbeitet.

Wenn wir jetzt den Satz der Datei ausführen, werden wir feststellen, dass die Bilddatei „sample-image.png“ erstellt wurde. Öffnen Sie es einfach in einem Viewer, um es zu überprüfen!

## Einschließlich des dekodierten Bildes

Wie wir am Anfang des Artikels erwähnt haben, verwenden wir zum Einbinden des dekodierten Bildes den bekannten LaTeX-Befehl `\includegraphics`:


```tex
\includegraphics[options]{sample-image.png}
```

Die (fast) vollständige LaTeX-Datei könnte also wie folgt aussehen:


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \write18{base64 -d  sample-image.64 > sample-image.png}
  \includegraphics[options]{sample-image.png}
\end{document}
```

Und der Java-Code, der die **Aspose.TeX**-API verwendet, ähnelt dem, was in anderen Artikeln zu finden ist, mit Ausnahme der Angabe der Shell-Modus-Option:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.java" >}}

Und jetzt ist **Schritt 5** abgeschlossen. Wirklich umfassende Beispiele finden Sie in unserem [Beispielprojekt](https://github.com/aspose-tex/Aspose.TeX-for-Java).

**Sie können sich auch die kostenlose Konvertierungs-[Web-App](https://products.aspose.app/tex/conversion/latex/) ansehen, die auf der Grundlage von [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) erstellt wurde.**