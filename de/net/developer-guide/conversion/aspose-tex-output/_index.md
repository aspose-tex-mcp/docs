---
translation: true
template: /templates/_template-net.md
title: Die Ausgabeschnittstelle von Aspose.TeX | .NET
linktitle: Die Ausgabeschnittstelle von Aspose.TeX
weight: 16
url: /net/aspose-tex-output/
description: Die Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für .NET mit TeX als Ausgabeformat wird hier anhand der Codebeispiele erläutert.
keywords: Aspose Tex-Ausgabe, .net Tex, Ausgabeverzeichnis, Ausgabe-Zip, Ausgabekonsole, Ausgabeterminal, Tex-Optionen, Ausgabedateiverzeichnis, Ausgabe-Zip-Verzeichnis, Tex-Konvertierung
lastmod: "2024-09-26"
---

{{<section overview>}}

Formale Definitionen der I/O-Implementierung finden Sie in **Aspose.TeX für .NET** [API-Referenz](https://reference.aspose.com/tex/net/aspose.tex.io/).

## Das Konzept des Ausgabeverzeichnisses

Da I/O-Grundelemente der TeX-Sprache nur Dateinamen verarbeiten können, definiert Aspose.TeX ein Verzeichnis als Zuordnung zwischen Namen und Datenmengen. Die Datenmengen sollen Dateien, Streams, Arrays oder was auch immer sein. Mit der API können wir die Eingabe- und Ausgabearbeitsverzeichnisse separat angeben. Es stellt die allgemeine Schnittstelle [IOutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) für die Ausgabe bereit, die der Benutzer für seine eigenen Zwecke implementieren kann. Es bietet auch eigene Implementierungen, die weiter unten besprochen werden. Die Schnittstelle erweitert [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), da die Engine zunächst eine Datei erstellen und schreiben und diese dann zurücklesen kann. Die eigene Methode der Schnittstelle [GetOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) gibt den Stream zurück, in den geschrieben werden soll, im Gegensatz zu dem Stream zum Lesen, der von [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/) zurückgegeben wird.

### Schreiben der Dateiausgabe in das Festplattendateisystem

Wie wir [oben](/tex/{{lang.url-fragment}}net/latex-to-image/) erwähnt haben, wäre der häufigste Wert für [OutputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) wahrscheinlich eine Instanz der Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

So würden wir es einstellen:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.cs" >}}

Dieser Anwendungsfall ist recht einfach, sodass Sie sich nicht mehr darauf konzentrieren müssen.

### Dateiausgabe in ein ZIP-Archiv schreiben

Wir können auch eine Datei (oder einen Stream) erstellen und diese von der TeX-Engine als ZIP-Archiv zum Speichern der Ausgabedateien verwenden lassen. Hier ist es:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputZipDirectory.cs" >}}

Zuerst erstellen wir einen Ausgabestream für die ZIP-Datei. Nachdem wir die Konvertierungsoptionen erstellt haben, legen wir dann die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) als Instanz der Klasse [OutputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) fest.

## Das Konzept des Ausgabeterminals

Es gibt noch einen weiteren wichtigen Teil der Ausgabe: die Terminalausgabe. In diesem Fall definiert **Aspose.TeX für .NET** die allgemeine Schnittstelle [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) mit nur einer Eigenschaft, die eine [TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter)-Implementierungsinstanz zurückgibt. Die bereitgestellten Implementierungen werden im Folgenden erläutert.

### Schreiben der Terminalausgabe in die Konsole

Dazu müssen wir die Option [TerminalOut](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) als Instanz der Klasse [OutputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) festlegen.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.cs" >}}

Auch hier handelt es sich um den Standardwert der Option, sodass keine wirkliche Notwendigkeit besteht, ihn anzugeben. Aus diesem Grund dient dieser Abschnitt nur zu Demonstrationszwecken.

### Terminalausgabe in eine Datei schreiben

Im Gegensatz zum Eingabeterminal bietet **Aspose.TeX für .NET** eine Implementierung von [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), die es uns ermöglicht, die Terminalausgabe in eine Datei in einem Ausgabeverzeichnis zu schreiben.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputFileTerminal.cs" >}} 

Hier bitten wir die TeX-Engine, die Terminalausgabe in die Datei mit dem Namen [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm zu schreiben, die im selben Ausgabeverzeichnis gespeichert wird, das wir für den Rest der Ausgabe angegeben haben. Dies ist jedoch nicht notwendig. Wir könnten genauso gut jede andere Instanz einer beliebigen Implementierung von [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) an den Konstruktor übergeben.