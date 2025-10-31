---
translation: true
template: /templates/_template-net.md
title: LaTeX-Dateireparatur | Aspose.TeX für .NET
linktitle: Reparatur von LaTeX-Dateien
weight: 30
url: /net/latex-repair/
description: Im Artikel wird die Aspose.TeX-Lösung für die .NET LaTeX-Reparatur beschrieben. Erfahren Sie anhand der Codebeispiele, wie Sie die Funktionalität nutzen.
lastmod: "2024-09-26"
---

{{<section overview>}}

## So überprüfen und reparieren Sie eine LaTeX-Datei

Wenn Sie eine Textdatei haben, von der Sie denken, dass sie eine LaTeX-Datei ist, und diese formatiert werden sollen, aber nicht sicher sind, ob es sich wirklich um eine LaTeX-Datei handelt (vielleicht sind Sie neu in der LaTeX-Welt), können Sie es mit der Überprüfung versuchen und Reparieren der LaTeX-Funktion, die von der Aspose.TeX-API für .NET bereitgestellt wird. Im folgenden Beispiel überprüfen und reparieren wir eine Beispieldatei „invalid-latex.tex“ aus dem Aspose.TeX für .NET-Beispielprojekt.

Zunächst ist zu erwähnen, dass die Beispieldatei zwar die TeX-Syntax zu verwenden scheint, jedoch nicht die von LaTeX geforderte Struktur aufweist. Wie Sie vielleicht wissen, muss eine LaTeX-Datei eine Präambel haben, die mit dem Befehl `\documentclass` beginnt, und einen Text innerhalb der „document“-Umgebung, d. h. zwischen `\begin{document}` und `\end{document}`.

Schauen wir uns nun das C#-Codebeispiel an.

{{< gist "aspose-com-gists" "7f54d335270200ebf5987d071bad028a" "Examples_LaTeXRepairerExample" >}}

Wie bei einem regulären TeX-Job erstellen wir zunächst ein Objekt, das die Optionen des Prozesses enthält, den wir ausführen möchten. Die meisten davon entsprechen den Optionen eines regulären TeX-Jobs. Tatsächlich ist das [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/) der Bereich, aus dem die Eingabedateien gelesen werden sollen. Wir verwenden es hier nicht, da wir den vollständigen Pfad zur Haupteingabedatei im Dateisystem bereitstellen und keine benutzerdefinierten Dateien in die Haupteingabedatei aufgenommen werden sollen. Dann ist [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/) der Bereich, in den die Ausgabedateien geschrieben werden sollen. [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/) verweist, falls zugewiesen, auf den Bereich, in dem Sie LaTeX-Pakete speichern können, die nicht in die Aspose.TeX-Bibliothek eingebettet sind. Die Eigenschaft [GuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/) wird später besprochen.

Nachdem wir die Optionen zugewiesen haben, führen wir den Prozess einfach aus!

Wie sieht also der Prüf- und Reparaturprozess aus? Zunächst durchsucht die API die Eingabedatei nach einem `\documentclass`-Vorkommen. Wenn dies fehlschlägt, wird davon ausgegangen, dass `\documentclass{article}` ganz am Anfang der Datei eingefügt werden muss. Diese Tatsache spiegelt sich in der Reparaturberichtdatei („.log“) wider.

Anschließend wird die angepasste Eingabedatei von Anfang an gescannt. Die mit dem LaTeX-Format geladene TeX-Engine kann irgendwann einen Fehler auslösen, der darauf hinweist, dass bisher kein `\begin{document}` gefunden wurde, obwohl dies bereits geschehen sollte. Dadurch wird die Position, an der `\begin{document}` eingefügt werden muss, definiert und im Bericht widergespiegelt.

Während die Engine die Datei weiter durchsucht, findet sie möglicherweise undefinierte Befehle oder Umgebungen. Die API kann für einige der häufigsten Befehle und Umgebungen Annahmen zu [eingebetteten erforderlichen Paketen](/tex/{{lang.url-fragment}}net/embedded-packages/) treffen (solche, die die Befehle und Umgebungen definieren, die erst definiert werden, wenn diese Pakete enthalten sind). Es gibt jedoch eine Möglichkeit, solche Annahmen extern zu treffen, indem die Schnittstelle [IGuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/) implementiert wird. Eine Instanz einer solchen Klasse sollte der Option „GuessPackageCallback“ zugewiesen werden.

Hier ist ein sehr einfaches Beispiel, das lediglich den Befehl „\head“ dem Paket „fancyhdr“ zuordnet:


{{< gist "aspose-com-gists" "7f54d335270200ebf5987d071bad028a" "Examples_PackageGuessingCallback" >}}

Was die Beispieldatei betrifft, stößt die Engine zunächst auf den Befehl `\chapter`, der nicht in der Dokumentklasse „article“, sondern in der Dokumentklasse „book“ definiert ist. Die API passt die Dokumentklasse so an, dass die endgültige Version der korrigierten Datei mit `\documentclass{book}` beginnt. Dann findet die Engine den oben genannten `\lhead`-Befehl und entscheidet, dass `\usepackage{fancyhdr}` in die Präambel eingefügt werden muss. Die Befehle `\href` und `\includegraphics`, die später auftreten, veranlassen den Repairer, `\usepackage{hyperref}` bzw. `\usepackage{graphics}` in die Präambel einzufügen. Diese Entscheidungen basieren auf den internen Zuordnungen der API. Auch hier werden alle derartigen Korrekturen in der Berichtsdatei protokolliert.

Schließlich wird die Engine abnormal beendet, da die normale Endung eines LaTeX-Dokuments fehlt. Dadurch hängt der Reparateur `\end{document}` an das Ende der Datei an und spiegelt diese Tatsache im Bericht wider.

Sobald die korrigierte Version der Originaldatei erstellt ist, führt der Repairer den TeX-Job zur abschließenden Prüfung aus. In unserem Beispiel werden bei diesem Lauf keine kritischen Fehler gefunden, sodass die korrigierte Version möglicherweise mehr oder weniger wie erwartet gesetzt ist.

Hier ist der vollständige Bericht:


```
Trying to repair the original file...
--------------------------------------------------------------------------------
\documentclass is missing in the original file. Inserted at the beginning.
\begin{document} is missing in the original file. Inserted at line 3, pos. 0.
The command \chapter at line 3, pos. 0 is undefined. Consider using \usepackage{package_name} in the preamble,
    where 'package_name' is the name of the package which defines this command.
The command \lhead at line 5, pos. 0 is undefined. \usepackage{fancyhdr} is inserted in the preamble
    since the 'fancyhdr' package supposedly defines the command.
The command \href at line 8, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 17, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 20, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 27, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 32, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \includegraphics at line 54, pos. 2 is undefined. \usepackage{graphicx} is inserted in the preamble
    since the 'graphicx' package supposedly defines the command.
The command \href at line 67, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 95, pos. 57 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 96, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 98, pos. 100 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
\end{document} is missing in the original file. Inserted at the end.

Checking the repaired file...
--------------------------------------------------------------------------------
There are no critical errors in the fixed file.
```

**Sie können sich auch unsere kostenlose Web-App [**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer) ansehen, die auf der in [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) implementierten Funktion basiert und eine erweiterte Version beinhaltet Implementierung der Schnittstelle „IGuessPackageCallback“.**
