---
translation: true
template: /templates/_template-python-net.md
title: Eingabeschnittstelle von Aspose.TeX | Python
linktitle: Die Eingabeschnittstelle von Aspose.TeX
weight: 15
url: /python-net/aspose-tex-input/
description: Die Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für Python mit TeX als Eingabeformat wird hier anhand der Codebeispiele erläutert.
lastmod: "2024-09-26"
---

{{<section overview>}}

> Formale Definitionen der I/O-Implementierung in **Aspose.TeX für Python** finden Sie in der [API-Referenz](https://reference.aspose.com/tex/python-net/aspose.tex.io/).

## Die Idee hinter dem Eingabeverzeichnis

Da die I/O-Primitive der TeX-Sprache nur Dateinamen verarbeiten können, definiert **Aspose.TeX für Python** ein Verzeichnis als Zuordnung zwischen Namen und Datensammlungen. Diese Datensammlungen können Dateien, Streams, Arrays oder jeder andere Typ sein. Die API ermöglicht die separate Angabe von Eingabe- und Ausgabearbeitsverzeichnissen. Es stellt die allgemeine Klasse [InputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/) bereit, die Benutzer für ihre spezifischen Anforderungen implementieren können. Darüber hinaus bietet die API integrierte Implementierungen, die später erläutert werden. Die Schnittstelle enthält die Methode [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), die den Datenstrom abruft und den vollständigen Dateinamen basierend auf einem vorgegebenen Namen ermittelt, der als Zuordnungsschlüssel dient.

### Dateieingaben aus dem Festplattendateisystem abrufen

Hier ist der Ansatz, den wir wählen würden:

Setzen Sie `ASPOSE_TEX_OUTPUT_DIR` auf das Ausgabeverzeichnis (Standard: `output`). Wenden Sie zuerst eine Lizenz an. [Licensing](/tex/de/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Setzen Sie `ASPOSE_TEX_INPUT_DIR` auf den Ordner mit `hello-world.tex` (Standard: `input`). Das Beispiel verwendet plain TeX mit `TeXConfig.object_tex()` und erzeugt `hello-world.xps` sowie `hello-world.log`. Eingabe:

```tex
Hello, World!
\end
```

### Dateieingaben aus einem ZIP-Archiv abrufen

Eine andere Möglichkeit besteht darin, die Eingabedateien in einem ZIP-Archiv zu speichern und es als Eingabeverzeichnis zu behandeln. In einem solchen Szenario sollten die folgenden Schritte befolgt werden:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

`ASPOSE_TEX_INPUT_ZIP` bezeichnet ein Archiv mit `in/hello-world.tex` (Standard: `zip-in.zip`). Öffnen Sie es im Binärmodus `rb` und halten Sie den Stream bis zum Auftragsende offen.

Zunächst erstellen wir den Stream, der die ZIP-Datei enthält. Anschließend weisen wir nach dem Erstellen der Konvertierungsoptionen eine Instanz der Klasse [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) der Eigenschaft [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) zu. Der zweite Parameter des Konstruktors stellt den Basispfad innerhalb des Archivs dar. Wenn wir möchten, dass das gesamte Archiv als Eingabeverzeichnis fungiert, sollten wir als Argument eine leere Zeichenfolge angeben.

## Die Idee hinter dem Eingabeterminal

Betrachten wir nun das Konzept der Terminaleingabe. **Aspose.TeX für Python** definiert speziell für diesen Zweck die allgemeine Schnittstelle [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/), die eine einzelne Eigenschaft enthält, die eine Instanz der Implementierung von [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/) zurückgibt. Die verfügbaren Implementierungen werden später besprochen.

### Terminaleingabe von der Konsole abrufen

Um dies zu erreichen, müssen wir der Option [terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/) eine Instanz der Klasse [InputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) zuweisen.

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

Das Beispiel liest mit `\read` eine Zeile und schreibt sie nach `texput.xps`. Geben Sie im Terminal etwa `Terminal input works!` ein oder leiten Sie die Zeile über die Standardeingabe ein. `SCROLL_MODE` erlaubt diese Eingabeanforderung.
