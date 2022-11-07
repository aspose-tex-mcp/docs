---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: TeX-Satzfunktionalität | .NET-API
url: /net/typeset-tex-files/
description: ".NET-API-Lösung für die Arbeit mit TeX. Erfahren Sie am Beispiel, wie Sie TeX-Schriftsätze mit ein paar Zeilen C#-Code erstellen."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX-Dateien setzen
h2: "Setzen Sie eine TeX-Datei mit einem benutzerdefinierten TeX-Format C# .NET"
---

{{<section overview>}}
---
p1: "TeX ist gleichzeitig als eine der Datenauszeichnungssprachen und/oder als Schriftsatzsprache bekannt. Das bedeutet, dass Sie Ihren Text nicht im Dokument formatieren, sondern den Klartext zusammen mit den Befehlen eingeben. Als Ausgabe erhalten Sie die formatierte Datei des benötigten (angegebenen) Formats. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) ist der zentrale Kern des Publikationssatzsystems (Computersatz)."
p2: "Um mehr über den TeX-Schriftsatz zu erfahren, lesen Sie die [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) der Dokumentation. Und auf dieser Seite finden Sie Codeschnipsel, die erklären, wie man eine TeX-Datei mit einem benutzerdefinierten TeX-Format setzt."
p3: "Um die Beispiele auszuführen, benötigen wir:"
p4: "Aspose.TeX für die .NET-API, eine funktionsreiche, leistungsstarke und benutzerfreundliche API zur Dokumentenbearbeitung und -konvertierung für die C#-Plattform."
p5: "Öffnen Sie den NuGet-Paket-Manager, suchen Sie nach Aspose.TeX und installieren Sie es. Sie können auch den folgenden Befehl in der Paket-Manager-Konsole verwenden."
---

{{<section feature1>}}
---
title: Schritte zum Setzen von TeX mit C#.
h3: "C#-Code zum Setzen von TeX"
item1: "Erstellen Sie den Formatanbieter mithilfe der Klasse [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Erstellen Sie Konvertierungsoptionen für ein benutzerdefiniertes Format bei der Erweiterung der ObjectTeX-Engine mit [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Method of [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse."
item3: "Geben Sie das Arbeitsverzeichnis der Eingabe an, wenn die Haupteingabe nicht als Stream bereitgestellt wird. Verwenden Sie dafür die Klasse [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item4: "Geben Sie ein Dateisystem-Arbeitsverzeichnis für die Ausgabe an. Verwenden Sie dafür die Klasse [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Führen Sie den Job aus [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Methode für [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Verfeinern Sie die Ausgabe.
---