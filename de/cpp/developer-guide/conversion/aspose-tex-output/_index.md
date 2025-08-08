---
translation: true
template: /templates/_template-cpp.md
title: Die Ausgabeschnittstelle von Aspose.TeX | C++
linktitle: Die Ausgabeschnittstelle von Aspose.TeX
weight: 16
url: /cpp/aspose-tex-output/
description: Die Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für C++ mit TeX als Ausgabeformat wird hier anhand der Codebeispiele erläutert.
lastmod: "2024-09-26"
---

{{<section overview>}}

Formale Definitionen der I/O-Implementierung finden Sie in **Aspose.TeX für C++** [API-Referenz](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.i_o).

## Das Konzept des Ausgabeverzeichnisses

Da I/O-Grundelemente der TeX-Sprache nur Dateinamen verarbeiten können, definiert Aspose.TeX ein Verzeichnis als Zuordnung zwischen Namen und Datenmengen. Die Datenmengen sollen Dateien, Streams, Arrays oder was auch immer sein. Mit der API können wir die Eingabe- und Ausgabearbeitsverzeichnisse separat angeben. Es stellt die allgemeine Schnittstelle [IOutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory) für die Ausgabe bereit, die der Benutzer für seine eigenen Zwecke implementieren kann. Es bietet auch eigene Implementierungen, die weiter unten besprochen werden. Die Schnittstelle erweitert [IInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory), da die Engine zunächst eine Datei erstellen und schreiben und diese dann zurücklesen kann. Die eigene Methode der Schnittstelle [GetOutputFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory/getoutputfile) gibt den Stream zurück, in den geschrieben werden soll, im Gegensatz zu dem Stream zum Lesen, der von [GetFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory#adc0d6f35f9a0c426ba010779d90b5cd6) zurückgegeben wird.

### Schreiben der Dateiausgabe in das Festplattendateisystem

Wie wir [oben](/tex/{{lang.url-fragment}}cpp/latex-to-image/) erwähnt haben, wäre der häufigste Wert für [OutputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) wahrscheinlich eine Instanz der Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory).

So würden wir es einstellen:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for the output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
```
Dieser Anwendungsfall ist recht einfach, sodass Sie sich nicht mehr darauf konzentrieren müssen.

### Dateiausgabe in ein ZIP-Archiv schreiben

Wir können auch eine Datei (oder einen Stream) erstellen und diese von der TeX-Engine als ZIP-Archiv zum Speichern der Ausgabedateien verwenden lassen. Hier ist es:

```C++
    // Open the stream for the ZIP archive that will serve as the output working directory.
    System::SharedPtr<System::IO::Stream> outZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"zip-pdf-out.zip"), System::IO::FileMode::Create);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputZipDirectory>(outZipStream));
```

Zuerst erstellen wir einen Ausgabestream für die ZIP-Datei. Nachdem wir die Konvertierungsoptionen erstellt haben, legen wir dann die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) als Instanz der Klasse [OutputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputzipdirectory) fest.

## Das Konzept des Ausgabeterminals

Es gibt noch einen weiteren wichtigen Teil der Ausgabe: die Terminalausgabe. In diesem Fall definiert **Aspose.TeX für C++** die allgemeine Schnittstelle [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal) mit nur einer Eigenschaft, die eine [TextWriter](https://reference.aspose.com/tex/cpp/system.io/textwriter)-Implementierungsinstanz zurückgibt. Die bereitgestellten Implementierungen werden im Folgenden erläutert.

### Schreiben der Terminalausgabe in die Konsole

Dazu müssen wir die Option [TerminalOut](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalout) als Instanz der Klasse [OutputConsoleTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputconsoleterminal) festlegen.


```C++
// Create conversion options instance.
...
// Specify the console as the output terminal.
options->set_TerminalOut(System::MakeObject<OutputConsoleTerminal>()); // Default. No need to specify.

```

Auch hier handelt es sich um den Standardwert der Option, sodass keine wirkliche Notwendigkeit besteht, ihn anzugeben. Aus diesem Grund dient dieser Abschnitt nur zu Demonstrationszwecken.

### Terminalausgabe in eine Datei schreiben

Im Gegensatz zum Eingabeterminal bietet **Aspose.TeX für C++** eine Implementierung von [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal), die es uns ermöglicht, die Terminalausgabe in eine Datei in einem Ausgabeverzeichnis zu schreiben.

```C++
// Create conversion options instance.
...
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options->set_TerminalOut(System::MakeObject<OutputFileTerminal>(options->get_OutputWorkingDirectory()));
```

Hier bitten wir die TeX-Engine, die Terminalausgabe in die Datei mit dem Namen [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm zu schreiben, die im selben Ausgabeverzeichnis gespeichert wird, das wir für den Rest der Ausgabe angegeben haben. Dies ist jedoch nicht notwendig. Wir könnten genauso gut jede andere Instanz einer beliebigen Implementierung von [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal) an den Konstruktor übergeben.