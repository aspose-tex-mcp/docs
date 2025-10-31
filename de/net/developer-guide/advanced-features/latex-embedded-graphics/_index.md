---
translation: true
template: /templates/_template-net.md
title: LaTeX eingebettete Grafiken | Aspose.TeX für .NET
linktitle: LaTeX-eingebettete Grafiken
weight: 18
url: /net/latex-embedded-graphics/
keywords: includegraphics latex, latex base64-Grafiken einbetten, latex base64-kodierte Grafiken, write18, Shell-Escape, Latex-Shell-Befehl
description: In diesem Artikel wird beschrieben, wie Sie Base64-codierte Bilder in den LaTeX-Quellcode einbinden, sowie die \write18-Funktion, die dies ermöglicht.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Eine andere Möglichkeit, Bilder einzubinden

Einige TeX/LaTeX-Systeme ermöglichen das Einbinden von Bildern, die nicht extern in Bezug auf die LaTeX-Datei selbst gespeichert sind, sondern direkt in der LaTeX-Datei enthalten sind. Da es sich bei TeX/LaTeX-Dateien jedoch um reine Textdateien handelt und sie daher keine Binärdaten enthalten können, benötigen wir eine Möglichkeit, Binärdaten in Textform darzustellen. Mit anderen Worten: Binärdaten müssen in eine Textdarstellung kodiert werden. Das Problem besteht darin, dass eine TeX-Engine solche codierten Bilder nicht direkt interpretieren kann. Tatsächlich erfolgt das Einbinden eines Bildes mit dem guten alten Befehl `\includegraphics` aus dem Paket „graphicx“. Allerdings kann dieser Befehl nur mit externen Bilddateien umgehen. Ja, eine externe Bilddatei (zusammen mit einer weiteren Zwischendatei) wird weiterhin außerhalb der LaTeX-Datei erstellt. Der entscheidende Punkt ist, dass Sie nur die LaTeX-Datei alleine verteilen müssen.

Okay, nehmen wir an, wir haben irgendwie ein codiertes Bild in die LaTeX-Datei eingefügt. Aber wie bekommen wir das Bild entschlüsselt? Leider können wir die Datei nicht dekodieren, indem wir sie aus der LaTeX-Datei lesen und in die externe Bilddatei schreiben. Die Textzeichenfolge, die das kodierte Bild darstellt, muss zunächst in eine externe Textdatei geschrieben werden, die dann dekodiert werden kann, um eine Bilddatei zu erzeugen.

Jetzt können wir die folgenden Schritte skizzieren, um das gewünschte Ergebnis zu erzielen:

1. Kodieren Sie das Bild.
2. Fügen Sie die Textzeichenfolge, die die Bilddaten darstellt, in die LaTeX-Datei ein.
3. Geben Sie die Textzeichenfolge, die die Bilddaten darstellt, in eine externe Datei aus.
4. Dekodieren Sie die externe Datei aus Schritt 3.
5. Fügen Sie das dekodierte Bild ein.

Die ersten beiden Schritte werden vom Autor der LaTeX-Datei ausgeführt. Eine TeX-Engine übernimmt die restlichen Schritte, vorausgesetzt natürlich, sie ist richtig angewiesen.

Fangen wir ganz von vorne an. Wie können wir unser Bild kodieren, um eine Zeichenfolge zu erhalten? Eine der Methoden hierfür (und wahrscheinlich die beliebteste) ist **Base64**.

## Codierung von Binärdaten mit Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) ist eine Gruppe von Binär-zu-Text-Codierungsschemata, die Binärdaten in eine Folge druckbarer Zeichen umwandelt, die auf einen Satz von 64 eindeutigen Zeichen beschränkt ist. Genauer gesagt werden den binären Quelldaten jeweils 6 Bits entnommen, dann wird diese Gruppe von 6 Bits einem von 64 eindeutigen Zeichen zugeordnet. Wie alle Binär-zu-Text-Codierungsschemata ist **Base64** darauf ausgelegt, in Binärformaten gespeicherte Daten über Kanäle zu übertragen, die nur Textinhalte zuverlässig unterstützen.

Aus dieser kurzen Erklärung können wir ersehen, dass **Base64** das ist, was wir brauchen. Um eine Bilddatei in **Base64** zu kodieren, können Sie ein Befehlszeilenprogramm (sofern auf Ihrem Betriebssystem verfügbar), Standard- oder Drittanbieterfunktionen fast jeder Programmiersprache oder Online-Tools wie [Base64.guru](verwenden.2) oder ähnlich.

## Platzieren des codierten Bildes in der LaTeX-Datei

Die Zeichenfolge, die Sie als Ergebnis der Kodierung erhalten, muss wie folgt in der Standard-LaTeX-Umgebung „filecontents*“ in der Präambel einer LaTeX-Datei platziert werden:


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Hier ist es. Schritt 2 ist abgeschlossen. Wir haben das Bild in der LaTeX-Datei! Aber was passiert, wenn wir den Satz dieser Datei mit LaTeX ausführen?

Ein LaTeX-Prozessor schreibt die Zeichenfolge in der Umgebung in eine externe Datei mit dem Namen „sample-image.64“. Durch die Verwendung der Option „Überschreiben“ wird die Datei überschrieben, wenn sie bereits existiert (z. B. wenn sie bei einem vorherigen Lauf erstellt wurde). Und das ist es auch, was Schritt 3 erreicht!

## Dekodierung einer Base64-Zeichenfolge

In Schritt 4 unseres Plans kommen die Unterschiede in den TeX-Implementierungen ins Spiel. Das Dekodieren einer Base64-Zeichenfolge erfolgt mithilfe einer häufigeren Funktion, die als „\write18“-Funktion bekannt ist.

### `\write18`

In klassischen TeX-Engines ist „\write<Nummer>(<Token-Liste>)“ das Grundelement, das eine *Liste von Token* schreibt. Bei Verwendung folgt auf dieses Grundelement eine Ganzzahl. Wenn diese Zahl negativ ist, werden die Token in die Transkriptdatei (Protokolldatei) geschrieben. Ist die Zahl größer als „15“, werden die Token auf das Terminal geschrieben. Wenn die Zahl im Bereich „0..15“ liegt, werden die Token in eine Datei geschrieben, deren Name durch ein vorangehendes Vorkommen des Primitivs `\openout` angegeben wird. Das Primitiv „\openout<4-bit integer>=<file name>“ ordnet einen Dateinamen einer Zahl zu.

Neuere TeX-Implementierungen (wie PDF TeX) ermöglichen die Verwendung von „\write18“. In diesem Fall interpretieren sie die „<token list>“ als Befehlszeile, die in der Betriebssystem-Shell ausgeführt werden soll. Da es sich bei dieser Funktion offensichtlich um eine potenzielle Hintertür handelt, könnten Sie einen Hauch von Mysterium spüren, wenn sie in der TeX-bezogenen Dokumentation oder im Internet erwähnt wird. Aus diesem Grund verfügen die ausführbaren Dateien von PDF TeX/LaTeX über Befehlsoptionen, um den Zugriff auf diese Funktion zu verwalten.

Im Allgemeinen gibt es drei Stufen der Barrierefreiheit: deaktiviert, aktiviert mit Einschränkungen und vollständig aktiviert.

In **Aspose.TeX** gibt es eine TeX-Joboption namens „ShellMode“, aber es gibt nur zwei geeignete Werte: „NoShellEscape“ und „ShellRestricted“. Der Wert „NoShellEscape“ bedeutet, dass die Funktion deaktiviert ist. Der zweite Wert gibt an, dass jeder Befehl, der ausgeführt werden muss, vom Benutzer als Erweiterung der Klasse „Executable“ implementiert werden muss. Hier werden wir nicht auf die Details solcher Implementierungen eingehen, aber wir werden erwähnen, dass die „base64“-Befehlsemulation bereits in Aspose.TeX implementiert ist. Standardmäßig finden Sie die Prototypinstanz in der Sammlungseigenschaft „Executables“ der Klasseninstanz „TeXOptions“.

### Base64-kodierte Daten dekodieren

Um den Inhalt einer Datei zu dekodieren, bei der es sich angeblich um Base64-kodierte Daten handelt, würden wir normalerweise die folgende Befehlszeile verwenden:


```
base64 -d  FILE1 > FILE2
```

Dabei ist FILE1 die „codierte“ Datei und „> FILE2“ bedeutet, dass die Ausgabe in die Datei „FILE2“ umgeleitet werden muss.

Daher sollten wir im Hauptteil unserer LaTeX-Datei die folgende Zeile hinzufügen:


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> Das Präfix `\immediate` ist erforderlich, um sicherzustellen, dass die Operation `\write` ausgeführt wird, sobald der TeX-Scanner den primitiven Befehl findet. Andernfalls wird er beim Seitenversand verarbeitet.

Wenn wir jetzt den Satz der Datei ausführen, werden wir sehen, dass die Bilddatei „sample-image.png“ erstellt wird. Komm schon, öffne es in einem Viewer, um es zu überprüfen!

## Einschließlich des dekodierten Bildes

Wie wir am Anfang des Artikels erwähnt haben, verwenden wir zum Einbinden des dekodierten Bildes den bekannten LaTeX-Befehl `\includegraphics`:


```tex
\includegraphics[options]{sample-image.png}
```

Die vollständige (fast) LaTeX-Datei könnte also wie folgt aussehen:


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

Und der C#-Code, der die **Aspose.TeX**-API verwendet, ähnelt dem in anderen Artikeln, außer dass die Option „ShellMode“ angegeben wird:

{{< gist "aspose-com-gists" "7f54d335270200ebf5987d071bad028a" "Examples_LaTeXEmbeddedBase64EncodedImage" >}}

Und jetzt sind wir mit **Schritt 5** fertig. Wirklich vollständige Beispiele finden Sie in unserem [Beispielprojekt](https://github.com/aspose-tex/Aspose.TeX-for-.NET).

**Sie können sich auch die kostenlose Konvertierungs-[Web-App](https://products.aspose.app/tex/conversion/latex/) ansehen, die auf der Grundlage von [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) erstellt wurde.**
