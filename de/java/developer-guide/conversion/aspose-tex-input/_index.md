---
translation: true
template: /templates/_template-java.md
title: Eingabeschnittstelle von Aspose.TeX | Java
linktitle: Die Eingabeschnittstelle von Aspose.TeX
weight: 15
url: /java/aspose-tex-input/
description: Die Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für Java mit TeX als Eingabeformat wird hier anhand der Codebeispiele erläutert.
lastmod: "2026-04-21"
---

{{<section overview>}}

Formale Definitionen der I/O-Implementierung finden Sie unter **Aspose.TeX für Java** [API-Referenz](https://reference.aspose.com/tex/java/com.aspose.tex/).

## Das Konzept des Eingabeverzeichnisses

Da I/O-Grundelemente der TeX-Sprache nur Dateinamen verarbeiten können, definiert **Aspose.TeX für Java** ein Verzeichnis als Zuordnung zwischen Namen und Datenmengen. Die Datenmengen sollen Dateien, Streams, Arrays oder was auch immer sein. Mit der API können wir die Eingabe- und Ausgabearbeitsverzeichnisse separat angeben. Es stellt die allgemeine Schnittstelle [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) bereit, die der Benutzer für seine eigenen Zwecke implementieren kann. Es bietet auch eigene Implementierungen, die weiter unten besprochen werden. Die Schnittstelle definiert die Methode [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), die den Datenstrom zurückgibt und den vollständigen Namen der Datei ermittelt, wobei als erstes Argument ein hypothetisch anderer Name verwendet wird, der tatsächlich der Zuordnungsschlüssel ist .

### Dateieingabe vom Festplattendateisystem abrufen

So würden wir es machen:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.java" >}}

Dieser Anwendungsfall ist recht einfach, daher werden wir uns nicht lange damit befassen.

### Dateieingabe aus einem ZIP-Archiv abrufen

Wir können die Eingabedateien auch in ein ZIP-Archiv legen und es als Eingabeverzeichnis betrachten. In diesem Fall sollten wir wie folgt vorgehen:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputZipDirectory.java" >}}

Zuerst erstellen wir den Stream, der die ZIP-Datei enthält. Nachdem wir die Konvertierungsoptionen erstellt haben, legen wir dann die Option [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) als Instanz der Klasse [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/) fest. Das zweite Argument des Konstruktors ist der Basispfad innerhalb des Archivs. Wenn wir möchten, dass das gesamte Archiv ein Eingabeverzeichnis ist, sollten wir die leere Zeichenfolge übergeben. 

## Das Konzept des Eingabeterminals

Denken wir nun daran, dass es auch den Terminaleingang gibt. In diesem Fall definiert **Aspose.TeX für Java** die allgemeine Schnittstelle [IInputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/) so, dass sie über zwei Methoden verfügt. Einer von ihnen gibt eine [BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html)-Instanz zurück. Eine andere Methode gibt einen [InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) als zugrunde liegenden Stream zurück. Die bereitgestellten Implementierungen der Schnittstelle werden im Folgenden erläutert.

### Terminaleingabe von der Konsole abrufen

Dazu müssen wir die Option [TerminalIn](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--) als Instanz der Klasse [InputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/) festlegen.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.java" >}}

Aber ehrlich gesagt ist dies der Standardwert der Option, es besteht also keine wirkliche Notwendigkeit, ihn anzugeben. Aus diesem Grund und solange es keine anderen Implementierungen gibt, dient dieser Abschnitt nur Demonstrationszwecken.

Wenn wir eine interaktive TeX-Datei (oder ein interaktives Skript) mit vorhersehbarem Verhalten haben, möchten wir theoretisch möglicherweise eine Version des Eingabeterminals implementieren, die ein ergänzendes Skript zur Beantwortung der Anforderungen der TeX-Engine enthält. Versuchen Sie es, wenn Sie Zeit haben!