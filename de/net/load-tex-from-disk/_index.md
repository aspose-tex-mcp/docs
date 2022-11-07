---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Laden von TeX von einer Diskette | .NET-API
url: /net/load-tex-from-disk/
description: ".NET-API-Lösung für die Arbeit mit TeX. Erfahren Sie anhand des Beispiels, wie Sie eine TeX-Datei mit ein paar Zeilen C#-Code von der Festplatte laden."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Laden Sie TeX-Quelldateien von der Festplatte
h2: ".NET-API-Lösung zum Laden von TeX/LaTeX-Dateien von der Festplatte"
---

{{<section overview>}}
---
p1: "TeX ist als Schriftsatzsprache bekannt. Das bedeutet, dass Sie Ihren Text nicht im Dokument formatieren, sondern den Klartext zusammen mit den Befehlen eingeben. Als Ausgabe erhalten Sie die formatierte Datei des benötigten (angegebenen) Formats. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) ist der zentrale Kern des Publikationssatzsystems (Computersatz). Ein TeX-Job läuft auf einer explizit angegebenen TeX-Datei. Um mehr über die TeX-Eingabe und -Ausgabe zu erfahren, lesen Sie die [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) der Dokumentation."
p2: "Wie bekannt ist, besteht der Hauptzweck von TeX darin, bei der Erstellung mathematischer oder technischer Texte zu helfen. Aber vor irgendwelchen Manipulationen sollte die Datei zuerst geladen werden. Hier finden Sie Code-Snippets, die erklären, wie TeX-Quelldateien von der Festplatte geladen werden, indem Dateisystemverzeichnisse für die Eingabe und Ausgabe verwendet, auf XPS-Gerät ausgegeben und Terminalausgaben auf die Konsole geschrieben werden."
p3: "Um die Beispiele auszuführen, benötigen wir:"
p4: "Aspose.TeX für die .NET-API, eine funktionsreiche, leistungsstarke und benutzerfreundliche API zur Dokumentenbearbeitung und -konvertierung für die C#-Plattform."
p5: "Öffnen Sie den NuGet-Paket-Manager, suchen Sie nach Aspose.TeX und installieren Sie es. Sie können auch den folgenden Befehl in der Paket-Manager-Konsole verwenden."
---

{{<section feature1>}}
---
title: Schritte zum Laden von TeX von einer Festplatte C#.
h3: "C#-Code zum Laden von TeX"
item1: "Erstellen Sie Konvertierungsoptionen für ein benutzerdefiniertes Format bei der Erweiterung der ObjectTeX-Engine mit [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Method of [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse."
item2: "Geben Sie ein Dateisystem-Arbeitsverzeichnis für die Eingabe an. Verwenden Sie dafür die Klasse [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item3: "Geben Sie mithilfe der Klasse [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) ein Dateisystem-Arbeitsverzeichnis für die Ausgabe an."
item4: "Geben Sie die Konsole mithilfe der Klasse [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) als Ausgabeterminal an."
item5: "Geben Sie bei Bedarf einen Speicheranschluss als Ausgangsanschluss an. Verwenden Sie dazu die Klasse [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Führen Sie den Job aus [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Methode für [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Verfeinern Sie die Ausgabe.
---