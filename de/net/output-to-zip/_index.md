---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX zu ZIP | .NET-API-Lösung
url: /net/output-to-zip/
description: ".NET-API-Lösung für die Arbeit mit TeX. Mit der TeX-zu-ZIP-Konvertierungsfunktion können Sie Ihre TeX-Datei als beliebtestes Archiv speichern. C#-Beispiele für diese Funktionalität."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Ausgabe in ZIP schreiben
h2: "Speichern Sie das Ergebnis der TeX-Dateikonvertierung als ZIP über C# .NET"
---

{{<section overview>}}
---
p1: "TeX ist als eine der Datenauszeichnungssprachen bekannt. Es ist der Hauptkern des Publikationssatzsystems (Computersatz). Es ist fragwürdig, [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) als Dateiformat zu betrachten, da es sich um eine Programmiersprache handelt. Und andererseits ist es eine Dolmetscher-Engine, die diese Sprache versteht. Wie auch immer, kurz gesagt, sein Hauptzweck ist es, bei der Erstellung mathematischer oder technischer Texte zu helfen. Wenn die Datei jedoch bereits erstellt wurde und Sie keine weiteren Manipulationen daran wünschen, möchten Sie sie möglicherweise in ein anderes, gängigeres Format konvertieren."
p2: "Die Aspose.TeX-API-Lösung ermöglicht neben den verschiedenen anderen Funktionen die Konvertierung von TeX-Dateien und das anschließende Speichern des Ergebnisses als ZIP-Archiv. Hier finden Sie ein Code-Snippet zum Konvertieren von TeX in PDF und zum Speichern der Ausgabe des Ergebnisses als ZIP-Datei. Der API-Konverter transformiert TeX unter Verwendung einer beliebigen Sprache, die von C# unterstützt wird. Die API, die Sie hier sehen, kann auch verwendet werden, um Ihre eigene plattformübergreifende Anwendung zu erstellen oder in Ihr .NET-Projekt integriert zu werden. Solche [*plattformübergreifenden Konverter*](https://products.aspose.app/tex/conversion/tex) sind auch im Aspose-Ökosystem vorhanden. Aber um die Beispiele auszuführen, brauchen wir:"
p3: "Aspose.TeX für die .NET-API, eine funktionsreiche, leistungsstarke und benutzerfreundliche API zur Dokumentenbearbeitung und -konvertierung für die C#-Plattform."
p4: "Öffnen Sie den NuGet-Paket-Manager, suchen Sie nach Aspose.TeX und installieren Sie es. Sie können auch den folgenden Befehl in der Paket-Manager-Konsole verwenden."
---

{{<section feature1>}}
---
title: Schritte zur Verwendung von ZIP-Verzeichnissen für die TeX-Ausgabedatei C#.
h3: "C#-Code zur Verwendung von ZIP-Verzeichnissen für die Ausgabe"
item1: "Erstellen Sie die Instanz der [*TeXOptions-Klasse*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "Geben Sie mithilfe der Eigenschaft [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) ein ZIP-Archiv-Arbeitsverzeichnis für die Ausgabe an."
item3: "Geben Sie die Konsole mithilfe der Klasse [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) als Ausgabeterminal an."
item4: "Definieren Sie die Optionen zum Speichern mit der Klasse [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item5: "Konvertierung mit [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) ausführen Methode für [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: Verfeinern Sie die Ausgabe.
item7: "Um das Ausgabe-ZIP-Archiv abzuschließen, verwenden Sie die Klasse [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
---