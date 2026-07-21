---
translation: true
template: /templates/_template-java.md
title: Die Ausgabeschnittstelle von Aspose.TeX | Java
linktitle: Die Ausgabeschnittstelle von Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: Die Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für Java mit TeX als Ausgabeformat wird hier anhand der Codebeispiele erläutert.
lastmod: "2026-04-21"
---

{{<section overview>}}

Formale Definitionen der I/O-Implementierung finden Sie unter **Aspose.TeX für Java** [API-Referenz](https://reference.aspose.com/tex/java/com.aspose.tex/).

## Das Konzept des Ausgabeverzeichnisses

Da I/O-Grundelemente der TeX-Sprache nur Dateinamen verarbeiten können, definiert Aspose.TeX ein Verzeichnis als Zuordnung zwischen Namen und Datenmengen. Die Datenmengen sollen Dateien, Streams, Arrays oder was auch immer sein. Mit der API können wir die Eingabe- und Ausgabearbeitsverzeichnisse separat angeben. Es stellt die allgemeine Schnittstelle [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) für die Ausgabe bereit, die der Benutzer für seine eigenen Zwecke implementieren kann. Es bietet auch eigene Implementierungen, die weiter unten besprochen werden. Die Schnittstelle erweitert [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), da die Engine zunächst eine Datei erstellen und schreiben und diese dann zurücklesen kann. Die eigene Methode der Schnittstelle [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) gibt den Stream zurück, in den geschrieben werden soll, im Gegensatz zu dem Stream zum Lesen, der von [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-) zurückgegeben wird.

### Schreiben der Dateiausgabe in das Festplattendateisystem

Wie wir [oben](/tex/{{lang.url-fragment}}/java/conversion/) erwähnt haben, wäre der häufigste Wert für [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) wahrscheinlich eine Instanz der Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

So würden wir es einstellen:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

Dieser Anwendungsfall ist recht einfach, daher werden wir uns nicht lange damit befassen.

### Dateiausgabe in ein ZIP-Archiv schreiben

Wir können auch eine Datei (oder einen Stream) erstellen und diese von der TeX-Engine als ZIP-Archiv zum Speichern der Ausgabedateien verwenden lassen. Hier ist es:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

Zuerst erstellen wir einen Ausgabestream für die ZIP-Datei. Nachdem wir die Konvertierungsoptionen erstellt haben, legen wir dann die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) als Instanz der Klasse [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/) fest.

## Das Konzept des Ausgabeterminals

Es gibt noch einen weiteren wichtigen Teil der Ausgabe: die Terminalausgabe. In diesem Fall definiert **Aspose.TeX für Java** die allgemeine Schnittstelle [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) so, dass sie über zwei Methoden verfügt. Einer von ihnen gibt eine [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html)-Instanz zurück. Ein anderer gibt eine [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html)-Instanz als zugrunde liegenden Stream zurück. Die bereitgestellten Implementierungen der Schnittstelle werden im Folgenden erläutert.

### Schreiben der Terminalausgabe in die Konsole

Dazu müssen wir die Option [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) als Instanz der Klasse [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/) festlegen.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

Auch hier handelt es sich um den Standardwert der Option, sodass keine wirkliche Notwendigkeit besteht, ihn anzugeben. Aus diesem Grund dient dieser Abschnitt nur zu Demonstrationszwecken.

### Terminalausgabe in eine Datei schreiben

Im Gegensatz zum Eingabeterminal bietet **Aspose.TeX für Java** eine Implementierung von [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), die es uns ermöglicht, die Terminalausgabe in eine Datei in einem Ausgabeverzeichnis zu schreiben.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}} 

Hier bitten wir die TeX-Engine, die Terminalausgabe in die Datei mit dem Namen [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm zu schreiben, die im selben Ausgabeverzeichnis gespeichert wird, das wir für den Rest der Ausgabe angegeben haben. Dies ist jedoch nicht notwendig. Wir könnten genauso gut jede andere Instanz einer beliebigen Implementierung von [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) an den Konstruktor übergeben.