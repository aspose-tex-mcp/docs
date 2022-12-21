---
translation: true
template: /_templates/_create-custom-tex-net.md
title: Maßgeschneiderte TeX-Dateien | .NET-API-Lösung
url: /net/create-custom-tex/
description: ".NET-API für die Arbeit mit TeX. Beinhaltet die Funktionalität zum Erstellen benutzerdefinierter TeX. C#-Beispiele für Funktionen zum Anpassen von TeX."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Erstellen Sie ein benutzerdefiniertes TeX-Format
h2: "Erstellen Sie eine Datei im benutzerdefinierten TeX-Format über C# .NET"
---

{{<section overview>}}
---
p1: "TeX ist als eine der Datenauszeichnungssprachen bekannt. Es ist der Hauptkern des Publikationssatzsystems (Computersatz). Es ist fragwürdig, [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) als Dateiformat zu betrachten, da es sich um eine Programmiersprache handelt. Und andererseits ist es eine Dolmetscher-Engine, die diese Sprache versteht. Wie auch immer, kurz gesagt, sein Hauptzweck ist es, bei der Erstellung mathematischer oder technischer Texte zu helfen. Auf der Grundlage von ΤeΧ wurden viele verschiedene Pakete erstellt. Sie sollen die Verarbeitung der Dokumente erleichtern, insbesondere wenn sie Formeln oder mathematische Gleichungen enthalten."
p2: "Die Aspose.TeX-API-Lösung ermöglicht neben den verschiedenen anderen Funktionen das Erstellen Ihrer eigenen vorgestellten TeX-Dateien. Hier finden Sie Informationen, die erklären, wie Sie Dateien in einem solchen benutzerdefinierten Format erstellen. Eine solche Datei enthält die angepassten Engine-Optionen. Dazu benötigen wir:"
p3: "Aspose.TeX für die .NET-API, eine funktionsreiche, leistungsstarke und benutzerfreundliche API zur Dokumentenbearbeitung und -konvertierung für die C#-Plattform."
p4: "Öffnen Sie den NuGet-Paket-Manager, suchen Sie nach Aspose.TeX und installieren Sie es. Sie können auch den folgenden Befehl in der Paket-Manager-Konsole verwenden."
---

{{<section feature1>}}
---
title: Schritte zum Erstellen einer benutzerdefinierten TeX-Datei C#.
h3: "C#-Code zum Anpassen von TeX-Dateien"
item1: "Unter Verwendung von [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode von [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse, erstellt TeX-Engine-Optionen für kein Format bei Erweiterung der ObjectTeX-Engine."
item2: "Geben Sie mithilfe der Klasse [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) ein Dateisystem-Arbeitsverzeichnis für die Eingabe an."
item3: "Verwenden Sie die Klasse [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), um ein Dateisystem-Arbeitsverzeichnis für die Ausgabe anzugeben."
item4: "Erstellen Sie das Format mit der Methode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Verfeinern Sie die Ausgabe.
---