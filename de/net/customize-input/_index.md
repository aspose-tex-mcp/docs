---
translation: true
template: /_templates/_customize-input-net.md
title: Erstell eine benutzerdefinierte TeXTEingabe
url: /net/customize-input/
description: ".NET-API für die Arbeit mit TeX. Erfahren Sie anhand des Beispiels, wie Sie mit C#-Code eine benutzerdefinierte Eingabe für eine TeX erstellen."
keywords: benutzerdefinierte Eingabe-Tex-Net-API, C#-API zum Anpassen von Tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Eingabe anpassen
h2: ".NET-API-Lösung zum Anpassen der Eingabe von TeX-Dateien"
---

{{<section overview>}}
---
p1: "TeX ist als Schriftsatzsprache bekannt. Das bedeutet, dass Sie Ihren Text nicht im Dokument formatieren, sondern den Klartext zusammen mit den Befehlen eingeben. Wie im Artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) der Dokumentation beschrieben, läuft der TeX-Job auf einer explizit angegebenen TeX-Datei. Also schließen wir diese Datei in die Eingabe eines bestimmten TeX-Jobs ein."
p2: "Auf dieser Seite finden Sie ein Codebeispiel, das erklärt, wie Sie die Eingabe von TeX-Quelldateien anpassen können, wobei zu berücksichtigen ist, dass die Eingabe der TeX-Syntax folgen und im Idealfall nur Befehle enthalten sollte, die der Engine bekannt sind."
p3: "Um die Eingabe von .tex-Dateien anzupassen, benötigen wir:"
p4: "Aspose.TeX für die .NET-API, eine funktionsreiche, leistungsstarke und benutzerfreundliche API zur Dokumentenbearbeitung und -konvertierung für die C#-Plattform."
p5: "Öffnen Sie den NuGet-Paket-Manager, suchen Sie nach Aspose.TeX und installieren Sie es. Sie können auch den folgenden Befehl in der Paket-Manager-Konsole verwenden."
---

{{<section feature1>}}
---
title: "Schritte zum Anpassen der TeX-Eingabe C#:"
h3: "C#-Code für die Anpassung der TeX-Eingabe"
item1: "Unter Verwendung von [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode von [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse, erstellt TeX-Engine-Optionen für kein Format bei Erweiterung der ObjectTeX-Engine."
item2: "Geben Sie mithilfe der Klasse [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) ein Dateisystem-Arbeitsverzeichnis für die Eingabe an."
item3: "Erstellen Sie mit Hilfe der Methode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) das benutzerdefinierte Format."
---