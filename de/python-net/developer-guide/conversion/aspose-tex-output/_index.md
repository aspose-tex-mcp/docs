---
translation: true
template: /templates/_template-python-net.md
title: Die Ausgabeschnittstelle von Aspose.TeX | Python
linktitle: Die Ausgabeschnittstelle von Aspose.TeX
weight: 16
url: /python-net/aspose-tex-output/
description: Hier finden Sie eine Erläuterung der Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für Python mit TeX als Ausgabeformat und Codebeispielen.
lastmod: "2024-09-26"
---

{{<section overview>}}

> Formale Definitionen der E/A-Implementierung finden Sie in der [API-Referenz](https://reference.aspose.com/tex/python-net/aspose.tex.io/) von **Aspose.TeX für Python**.

## Die Idee hinter dem Ausgabeverzeichnis

Aspose.TeX definiert ein Verzeichnis als eine Zuordnung zwischen Namen und Datenmengen, wobei die Datenmengen Dateien, Streams, Arrays oder andere Datentypen sein können. Die API ermöglicht die Angabe separater Eingabe- und Ausgabearbeitsverzeichnisse. Für die Ausgabe stellt die API die allgemeine Schnittstelle [IOutputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/) zur Verfügung, die vom Benutzer für seine spezifischen Anforderungen implementiert werden kann. Darüber hinaus stellt die API gebrauchsfertige Implementierungen bereit, die im Folgenden erläutert werden. Die *IOutputWorkingDirectory*-Schnittstelle erweitert [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/), da die Engine zunächst eine Datei erstellen und schreiben und diese dann zurücklesen kann. Die Schnittstelle enthält die Methode [get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str), die den Stream zum Schreiben zurückgibt, im Gegensatz zur Methode [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), die den Stream zum Lesen zurückgibt.

### Speichern der Ausgabe als Datei im Festplattendateisystem

Wie [oben](/tex/{{lang.url-fragment}}net/latex-to-image/) erwähnt, wird das [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/) üblicherweise als Instanz der Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) festgelegt.

So würden wir es einstellen:

Setzen Sie `ASPOSE_TEX_OUTPUT_DIR` auf das Ausgabeverzeichnis (Standard: `output`). Wenden Sie zuerst eine Lizenz an. [Licensing](/tex/de/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

Der eingebettete plain-TeX-Stream erzeugt `texput.xps` und `texput.log` im Ausgabeverzeichnis.

### Speichern der Ausgabe als ZIP-Archivdatei.

Eine andere Möglichkeit besteht darin, eine Datei oder einen Stream zu erstellen und diese als ZIP-Archiv zum Speichern der Ausgabedateien zu verwenden. Hier ist ein Beispiel:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

`zip-xps-out.zip` wird im Binärmodus `wb` geöffnet. Rufen Sie `finish()` auf `OutputZipDirectory` auf, bevor der Stream geschlossen wird. Das Archiv enthält `texput.xps` und `texput.log`.

Zunächst erstellen wir einen Ausgabestream für die ZIP-Datei. Nachdem wir die Konvertierungsoptionen erstellt haben, legen wir dann die Option *output_working_directory* als Instanz der Klasse [OutputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/) fest.

## Die Idee hinter dem Ausgabeterminal

Die Terminalausgabe ist ein weiterer wichtiger Aspekt der Ausgabe. Zu diesem Zweck definiert **Aspose.TeX für Python** die allgemeine Schnittstelle [IOutputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/), die über eine einzelne Eigenschaft verfügt, die eine Instanz der [TerminalWriter](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/)-Implementierung zurückgibt. Die verfügbaren Implementierungen werden im Folgenden erläutert.

### Schreiben der Terminalausgabe in die Konsole

Um dies zu erreichen, müssen wir die Option [terminal_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/) als Instanz der Klasse [OutputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/) festlegen.

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

Auch hier handelt es sich um den Standardwert der Option, sodass keine wirkliche Notwendigkeit besteht, ihn anzugeben. Daher dient dieser Abschnitt ausschließlich zu Demonstrationszwecken.

### Terminalausgabe in eine Datei schreiben

Im Gegensatz zum Eingabeterminal enthält **Aspose.TeX für Python** eine Implementierung der *IOutputTerminal*-Schnittstelle, die es uns ermöglicht, die Terminalausgabe in eine Datei innerhalb eines angegebenen Ausgabeverzeichnisses zu schreiben.

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}}

`OutputFileTerminal` erhält das Ausgabearbeitsverzeichnis im Konstruktor und schreibt dort `texput.trm` neben `texput.xps` und `texput.log`.
