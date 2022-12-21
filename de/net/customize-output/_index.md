---
translation: true
template: /_templates/_customize-output-net.md
title: Benutzerdefinierte Ausgabe erstellen TeX | .NET-API
url: /net/customize-output/
description: ".NET-API für die Arbeit mit TeX. Lesen Sie das Beispiel, wie Sie mit ein paar Zeilen C#-Code eine benutzerdefinierte Ausgabe für eine TeX-Datei erstellen."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Ausgabe anpassen
h2: ".NET-API-Lösung zum Anpassen der Ausgabe von TeX-Dateien"
---

{{<section overview>}}
---
p1: "TeX ist als Schriftsatzsprache bekannt. Das bedeutet, dass Sie Ihren Text nicht im Dokument formatieren, sondern den Klartext zusammen mit den Befehlen eingeben."
p2: "Der Artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) der Dokumentation lehrt uns, dass eine TeX-Datei keine zu setzenden Daten enthalten darf, sondern nur Steuersequenzen . Allerdings enthält es in der Regel solche Daten, und eine Datei im Zielformat hat den gesetzten Text. Die Datei hat auch denselben Namen wie die als Eingabe angegebene Datei und ist die Hauptausgabedatei. Für das ursprüngliche TeX ist dies eine Datei im DVI-Format. Wir nennen den Namen sowohl der Eingabe- als auch der Ausgabedatei, ohne den Jobnamen zu erweitern."
p3: "Auf dieser Seite finden Sie ein Codebeispiel, das das Erstellen einer benutzerdefinierten Datei im TeX-Format erläutert, in dem Sie sehen können, wie Sie die Ausgabe von TeX-Dateien anpassen können. Um die Ausgabe von .tex-Dateien anzupassen, benötigen wir:"
p4: "Aspose.TeX für die .NET-API, eine funktionsreiche, leistungsstarke und benutzerfreundliche API zur Dokumentenbearbeitung und -konvertierung für die C#-Plattform."
p5: "Öffnen Sie den NuGet-Paket-Manager, suchen Sie nach Aspose.TeX und installieren Sie es. Sie können auch den folgenden Befehl in der Paket-Manager-Konsole verwenden."
---

{{<section feature1>}}
---
title: "Schritte zum Anpassen der TeX-Ausgabe C#:"
h3: "C#-Code für die Anpassung der TeX-Ausgabe"
item1: "Mit Hilfe der Methode [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) von [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse, erstellt TeX-Engine-Optionen für kein Format bei Erweiterung der ObjectTeX-Engine."
item2: "Verwenden Sie die Klasse [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), um ein Dateisystem-Arbeitsverzeichnis für die Eingabe anzugeben."
item3: "Verwenden Sie die Klasse [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), um ein Dateisystem-Arbeitsverzeichnis für die Ausgabe anzugeben."
item4: "Verwenden Sie zum Erstellen des neuen Formats die Methode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Verfeinern Sie die Ausgabe.
---