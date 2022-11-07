---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Laden von TeX aus ZIP | .NET-API-Lösung
url: /net/load-tex-from-zip/
description: ".NET-API-Lösung für die Arbeit mit TeX. Erfahren Sie am Beispiel, wie Sie mit ein paar Zeilen C#-Code eine TeX-Datei aus ZIP laden."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Laden Sie TeX-Quelldateien aus ZIP
h2: ".NET-API-Lösung zum Laden von TeX-Dateien aus ZIP-Archiven"
---

{{<section overview>}}
---
p1: "TeX ist als Schriftsatzsprache bekannt. Das bedeutet, dass Sie Ihren Text nicht im Dokument formatieren, sondern den Klartext zusammen mit den Befehlen eingeben. Als Ausgabe erhalten Sie die formatierte Datei des benötigten (angegebenen) Formats. Um mehr über die TeX-Eingabe und -Ausgabe zu erfahren, lesen Sie die [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) der Dokumentation."
p2: "Wie bekannt ist, besteht der Hauptzweck von TeX darin, bei der Erstellung mathematischer oder technischer Texte zu helfen. Aber vor irgendwelchen Manipulationen sollte die Datei zuerst geladen werden. Hier finden Sie Codeschnipsel, die erklären, wie man TeX-Quelldateien aus ZIP lädt, indem man ZIP-Verzeichnisse für die Eingabe und Ausgabe verwendet, auf ein PDF-Gerät ausgibt und die Terminalausgabe auf die Konsole schreibt."
p3: "Um .tex-Dateien zu laden, benötigen wir:"
p4: "Aspose.TeX für die .NET-API, eine funktionsreiche, leistungsstarke und benutzerfreundliche API zur Dokumentenbearbeitung und -konvertierung für die C#-Plattform."
p5: "Öffnen Sie den NuGet-Paket-Manager, suchen Sie nach Aspose.TeX und installieren Sie es. Sie können auch den folgenden Befehl in der Paket-Manager-Konsole verwenden."
---

{{<section feature1>}}
---
title: "Schritte zum Laden von TeX aus einem ZIP-Archiv C#:"
h3: "C#-Code zum Laden von TeX"
item1: "Öffnen Sie den Stream im ZIP-Archiv, um ihn als Eingabe-Arbeitsverzeichnis zu verwenden."
item2: "Öffnen Sie den Stream im ZIP-Archiv, um ihn als Ausgabe-Arbeitsverzeichnis zu verwenden."
item3: "Erstellen Sie Konvertierungsoptionen für das standardmäßige ObjectTeX-Format bei der Erweiterung der ObjectTeX-Engine mit [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode von [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse."
item4: "Geben Sie ein ZIP-Archiv-Arbeitsverzeichnis für die Eingabe an oder/und geben Sie einen Pfad innerhalb des Archivs an. Verwenden Sie dafür Konstruktoren der Klasse [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/)."
item5: "Geben Sie ein ZIP-Archiv-Arbeitsverzeichnis für die Ausgabe an oder/und geben Sie einen Pfad innerhalb des Archivs an. Verwenden Sie dafür Konstruktoren der Klasse [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
item6: "Geben Sie die Konsole mithilfe der Klasse [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) als Ausgabeterminal an."
item7: "Definieren Sie die Speicheroptionen mithilfe der Klasse [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Führen Sie den Job aus [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Methode für [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Verfeinern Sie die Ausgabe.
---