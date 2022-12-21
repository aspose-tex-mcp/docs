---
translation: true
template: /_templates/_output-to-disk-net.md
title: TeX-Ausgabe auf Festplatte schreiben | .NET-API
url: /net/output-to-disk/
description: ".NET-API-Lösung für die Arbeit mit TeX. Erfahren Sie anhand des Beispiels, wie Sie mit C#-Code eine benutzerdefinierte Ausgabe für eine TeX-Datei erstellen"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX-Ausgabe auf Diskette schreiben
h2: "Speichern Sie das Ergebnis der TeX-Dateikonvertierung als Datenträger über C# .NET"
---

{{<section overview>}}
---
p1: "TeX ist als Schriftsatzsprache bekannt, was bedeutet, dass Sie Ihren Text nicht im Dokument formatieren, sondern den Klartext zusammen mit den Befehlen eingeben. Wie aus dem Artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) der Documentation bekannt ist, läuft der TeX-Job auf einer explizit angegebenen TeX-Datei. Dort finden Sie auch Informationen über TeX-Interaktionsmodi und Primitive im Zusammenhang mit TeX-Eingabe und -Ausgabe."
p2: "Die Hauptanwendung von TeX besteht darin, bei der Erstellung mathematischer oder technischer Texte zu helfen. Wenn die Datei jedoch bereits erstellt wurde und Sie keine weiteren Manipulationen daran wünschen, möchten Sie sie möglicherweise in ein anderes, gängigeres Format konvertieren."
p3: "Auf dieser Seite finden Sie ein Codebeispiel, das die Verwendung von Dateisystemverzeichnissen für die Eingabe und Ausgabe, die Ausgabe an ein XPS-Gerät, das Überschreiben des Auftragsnamens und das Schreiben der Terminalausgabe auf die Festplatte erläutert. In einfachen Worten, es ist eine Konvertierung mit dem Schreiben der Ausgabe auf die Festplatte. Um eine solche Operation durchzuführen, benötigen wir:"
p4: "Aspose.TeX für die .NET-API, eine funktionsreiche, leistungsstarke und benutzerfreundliche API zur Dokumentenbearbeitung und -konvertierung für die C#-Plattform."
p5: "Öffnen Sie den NuGet-Paket-Manager, suchen Sie nach Aspose.TeX und installieren Sie es. Sie können auch den folgenden Befehl in der Paket-Manager-Konsole verwenden."
---

{{<section feature1>}}
---
title: "Schritte zum Schreiben der Terminalausgabe auf die Festplatte C#:"
h3: "C#-Code zum Konvertieren von TeX und Schreiben der Ausgabe auf die Festplatte"
item1: "Erstellen Sie Konvertierungsoptionen für die ObjectTeX-Engine-Erweiterung mit [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode von [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse."
item2: "Geben Sie einen Jobnamen an, wenn das erste Argument des TeXJob-Konstruktors nicht als Jobname verwendet werden soll."
item3: "Geben Sie ein Dateisystem-Arbeitsverzeichnis für die Eingabe an. Verwenden Sie dafür die Klasse [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item4: "Geben Sie mithilfe der Entitäten der Klasse [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) ein Dateisystem-Arbeitsverzeichnis für die Ausgabe an."
item5: "Geben Sie an, dass die Terminalausgabe in eine Datei im Arbeitsverzeichnis der Ausgabe geschrieben werden muss."
item6: "Führen Sie den Job aus [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Methode für [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---