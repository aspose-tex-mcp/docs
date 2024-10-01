---
translation: true
template: /templates/_template-net.md
title: Eingabeschnittstelle von Aspose.TeX | .NETTO
linktitle: Die Eingabeschnittstelle von Aspose.TeX
weight: 15
url: /net/aspose-tex-input/
description: Die Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für .NET mit TeX als Eingabeformat wird hier anhand der Codebeispiele erläutert.
lastmod: "2024-09-26"
---

{{<section overview>}}

Formale Definitionen der I/O-Implementierung finden Sie in **Aspose.TeX für .NET** [API-Referenz](https://reference.aspose.com/tex/net/aspose.tex.io/).

## Das Konzept des Eingabeverzeichnisses

Da E/A-Grundelemente der TeX-Sprache nur Dateinamen verarbeiten können, definiert **Aspose.TeX für .NET** ein Verzeichnis als Zuordnung zwischen Namen und Datenmengen. Die Datenmengen sollen Dateien, Streams, Arrays oder was auch immer sein. Mit der API können wir die Eingabe- und Ausgabearbeitsverzeichnisse separat angeben. Es stellt die allgemeine Schnittstelle [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) bereit, die der Benutzer für seine eigenen Zwecke implementieren kann. Es bietet auch eigene Implementierungen, die weiter unten besprochen werden. Die Schnittstelle definiert die Methode [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/), die den Datenstrom zurückgibt und den vollständigen Namen der Datei ermittelt, wobei als erstes Argument ein hypothetisch anderer Name verwendet wird, der tatsächlich der Zuordnungsschlüssel ist .

### Dateieingabe vom Festplattendateisystem abrufen

So würden wir es machen:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.cs" >}}

Dieser Anwendungsfall ist recht einfach, sodass Sie sich nicht mehr darauf konzentrieren müssen.

### Dateieingabe aus einem ZIP-Archiv abrufen

Wir können die Eingabedateien auch in ein ZIP-Archiv legen und es als Eingabeverzeichnis betrachten. In diesem Fall sollten wir wie folgt vorgehen:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputZipDirectory.cs" >}}

Zuerst erstellen wir den Stream, der die ZIP-Datei enthält. Nachdem wir die Konvertierungsoptionen erstellt haben, legen wir dann die Option [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) als Instanz der Klasse [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) fest. Das zweite Argument des Konstruktors ist der Basispfad innerhalb des Archivs. Wenn wir möchten, dass das gesamte Archiv ein Eingabeverzeichnis ist, sollten wir die leere Zeichenfolge übergeben. 

## Das Konzept des Eingabeterminals

Jetzt ist es an der Zeit, sich daran zu erinnern, dass es auch die Terminaleingabe gibt. In diesem Fall definiert **Aspose.TeX für .NET** die allgemeine [IInputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/)-Schnittstelle mit nur einer Eigenschaft, die eine [TextReader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader)-Implementierungsinstanz zurückgibt. Die bereitgestellten Implementierungen werden im Folgenden erläutert.

### Terminaleingabe von der Konsole abrufen

Dazu müssen wir die Option [TerminalIn](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) als Instanz der Klasse [InputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/) festlegen.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputConsoleTerminal.cs" >}}

Aber ehrlich gesagt ist dies der Standardwert der Option, es besteht also keine wirkliche Notwendigkeit, ihn anzugeben. Aus diesem Grund und solange es keine anderen Implementierungen gibt, dient dieser Abschnitt nur Demonstrationszwecken.

Wenn wir eine interaktive TeX-Datei (oder ein interaktives Skript) mit vorhersehbarem Verhalten haben, möchten wir theoretisch möglicherweise eine Version des Eingabeterminals implementieren, die ein ergänzendes Skript zur Beantwortung der Anforderungen der TeX-Engine enthält. Versuchen Sie es, wenn Sie Zeit haben!