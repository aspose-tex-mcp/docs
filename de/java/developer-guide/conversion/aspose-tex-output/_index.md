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

Die Dateisystem-, ZIP- und Terminalbeispiele setzen `hello-world.tex` in XPS. Setzen Sie `inputDirectory` auf einen Ordner mit der TeX-Datei und `outputDirectory` auf einen vorhandenen Ausgabeordner. Für ZIP-Ausgaben muss `outputZip` ein `java.nio.file.Path` in einem vorhandenen Ordner sein. Importieren Sie die im gewählten Beispiel verwendeten Aspose.TeX-Klassen, `com.aspose.tex.rendering.XpsDevice` und die erforderlichen Klassen aus `java.io` und `java.nio.file`. Die aufrufende Methode muss Ausnahmen behandeln oder deklarieren. Wenden Sie eine Lizenz gemäß dem [Lizenzleitfaden](/tex/{{lang.url-fragment}}java/licensing/) an, um Einschränkungen der Evaluierung zu vermeiden.

## Das Konzept des Ausgabeverzeichnisses

Da I/O-Grundelemente der TeX-Sprache nur Dateinamen verarbeiten können, definiert Aspose.TeX ein Verzeichnis als Zuordnung zwischen Namen und Datenmengen. Die Datenmengen sollen Dateien, Streams, Arrays oder was auch immer sein. Mit der API können wir die Eingabe- und Ausgabearbeitsverzeichnisse separat angeben. Es stellt die allgemeine Schnittstelle [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) für die Ausgabe bereit, die der Benutzer für seine eigenen Zwecke implementieren kann. Es bietet auch eigene Implementierungen, die weiter unten besprochen werden. Die Schnittstelle erweitert [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), da die Engine zunächst eine Datei erstellen und schreiben und diese dann zurücklesen kann. Die eigene Methode der Schnittstelle [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) gibt den Stream zurück, in den geschrieben werden soll, im Gegensatz zu dem Stream zum Lesen, der von [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-) zurückgegeben wird.

### Schreiben der Dateiausgabe in das Festplattendateisystem

Wie wir [oben](/tex/{{lang.url-fragment}}/java/conversion/) erwähnt haben, wäre der häufigste Wert für [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) wahrscheinlich eine Instanz der Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

So würden wir es einstellen:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

Dieser Anwendungsfall ist recht einfach, daher werden wir uns nicht lange damit befassen.

### Dateiausgabe in ein ZIP-Archiv schreiben

Wir können auch eine Datei (oder einen Stream) erstellen und diese von der TeX-Engine als ZIP-Archiv zum Speichern der Ausgabedateien verwenden lassen. Hier ist es:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

Zuerst erstellen wir einen Ausgabestream für die ZIP-Datei. Nachdem wir die Konvertierungsoptionen erstellt haben, legen wir dann die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) als Instanz der Klasse [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/) fest. Das Beispiel speichert `hello-world.xps` und `hello-world.log` im Archiv. Rufen Sie nach dem Auftrag `finish()` für das Ausgabeverzeichnis auf, bevor Sie den zugrunde liegenden Stream schließen. Die Beispiele halten Streams und Arbeitsverzeichnisse bis zum Ende des Auftrags offen und schließen sie danach.

## Das Konzept des Ausgabeterminals

Es gibt noch einen weiteren wichtigen Teil der Ausgabe: die Terminalausgabe. In diesem Fall definiert **Aspose.TeX für Java** die allgemeine Schnittstelle [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) so, dass sie über zwei Methoden verfügt. Einer von ihnen gibt eine [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html)-Instanz zurück. Ein anderer gibt eine [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html)-Instanz als zugrunde liegenden Stream zurück. Die bereitgestellten Implementierungen der Schnittstelle werden im Folgenden erläutert.

### Schreiben der Terminalausgabe in die Konsole

Dazu müssen wir die Option [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) als Instanz der Klasse [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/) festlegen.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` ist der Standardwert dieser Option. Das Beispiel wählt ihn ausdrücklich aus und schreibt während der Konvertierung die Terminalausgabe in die Konsole. Alle vier Beispiele laufen ohne Benutzerinteraktion; die Dateisystem- und ZIP-Beispiele erfassen die Terminalausgabe im Speicher.

### Terminalausgabe in eine Datei schreiben

Im Gegensatz zum Eingabeterminal bietet **Aspose.TeX für Java** eine Implementierung von [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), die es uns ermöglicht, die Terminalausgabe in eine Datei in einem Ausgabeverzeichnis zu schreiben.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

Legen Sie das Ausgabearbeitsverzeichnis fest, bevor Sie `OutputFileTerminal` erstellen. Die Terminalausgabe wird dort in [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm geschrieben, hier `hello-world.trm`. Diese Terminaldatei ist vom TeX-Protokoll `hello-world.log` getrennt. Um die Terminalausgabe an einen anderen Ort zu schreiben, übergeben Sie dem Konstruktor eine andere [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/)-Implementierung.