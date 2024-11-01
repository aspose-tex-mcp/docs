---
translation: true
template: /templates/_template-java.md
title: LaTeX-Dateireparatur | API für Java
linktitle: Reparatur von LaTeX-Dateien
weight: 30
url: /java/latex-repair/
description: Die LaTeX-Dateireparaturfunktion innerhalb der Aspose.TeX-API für Java wird in diesem Artikel beschrieben. Erfahren Sie anhand der Codebeispiele, wie Sie die Funktionalität nutzen.
lastmod: "2024-09-26"
---

{{<section overview>}}

## So überprüfen und reparieren Sie eine LaTeX-Datei

Wenn Sie nicht sicher sind, ob es sich bei einer Textdatei um eine LaTeX-Datei handelt, und diese formatiert werden soll, können Sie die von der Aspose.TeX-API für Java angebotene LaTeX-Prüf- und Reparaturfunktion nutzen. Im folgenden Beispiel überprüfen und reparieren wir eine Beispieldatei, „invalid-latex.tex“, aus dem Aspose.TeX für Java-Beispielprojekt.

Zunächst ist es wichtig zu beachten, dass die Beispieldatei offenbar die TeX-Syntax verwendet, jedoch die für LaTeX erforderliche Struktur fehlt. Wie Sie vielleicht wissen, muss eine LaTeX-Datei eine Präambel enthalten, die mit dem Befehl \documentclass beginnt, sowie einen in der Dokumentumgebung eingeschlossenen Textkörper, insbesondere zwischen \begin{document} und \end{document}.

Schauen wir uns nun das Java-Codebeispiel an.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

Ähnlich wie bei einem regulären TeX-Job erstellen wir zunächst ein Objekt, das die Optionen für den Prozess enthält, den wir ausführen möchten. Die meisten dieser Optionen sind die gleichen wie bei einem regulären TeX-Job. Tatsächlich geben wir beim Aufruf der Methode [setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-) den Speicherplatz an, aus dem die Eingabedateien gelesen werden sollen. In diesem Beispiel verwenden wir es jedoch nicht, da wir den vollständigen Pfad zur Haupteingabedatei im Dateisystem bereitstellen und keine benutzerdefinierten Dateien in die Haupteingabedatei aufgenommen werden sollen. Als nächstes rufen wir die Methode [setOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-) auf, um den Speicherplatz anzugeben, in den die Ausgabedateien geschrieben werden sollen. Wenn die Methode [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) aufgerufen wird, verweisen Optionen auf den Bereich, in dem Sie LaTeX-Pakete speichern können, die nicht in die Aspose.TeX-Bibliothek eingebettet sind. Schließlich wird die Methode [setGuessPackageCallback()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) später besprochen.

Sobald die Optionen zugewiesen wurden, können wir mit der Ausführung des Prozesses fortfahren.

Wie sieht also der Prüf- und Reparaturprozess aus? Es beginnt damit, dass die API nach einem `\documentclass`-Vorkommen in der Eingabedatei sucht. Wenn es nicht gefunden wird, geht die API davon aus, dass `\documentclass{article}` am Anfang der Datei eingefügt werden sollte. Diese Informationen werden in der Reparaturberichtdatei (.log) aufgezeichnet.

Als nächstes beginnt der Prozess mit dem Scannen der angepassten Eingabedatei von Anfang an. Die mit dem LaTeX-Format ausgestattete TeX-Engine kann irgendwann einen Fehler auslösen, der darauf hinweist, dass `\begin{document}` noch nicht gefunden wurde, obwohl dies bereits der Fall sein sollte. Auf diese Weise wird die Position, an der `\begin{document}` eingefügt werden muss, definiert und im Bericht widergespiegelt.

Beim weiteren Scannen der Datei stößt die Engine möglicherweise auf undefinierte Befehle oder Umgebungen. In solchen Fällen kann die API für einige der häufigsten Befehle und Umgebungen Annahmen zu [eingebetteten erforderlichen Paketen](/tex/{{lang.url-fragment}}net/embedded-packages/) treffen (diejenigen, die die Befehle und Umgebungen definieren, die erst definiert werden, wenn diese Pakete enthalten sind). Es ist jedoch möglich, solche Annahmen extern durch eine Klasse zu treffen, die die Schnittstelle [IGuessPackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/) implementiert. Sobald Sie eine solche Klasse entwickelt haben, sollte eine Instanz davon durch Aufruf der Methode „setGuessPackageCallback()“ an den Prozess übergeben werden.

Hier ist ein einfaches Beispiel, das einfach den Befehl „\head“ dem Paket „fancyhdr“ zuordnet:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}

Was die Beispieldatei betrifft, stößt die Engine zunächst auf den Befehl `\chapter`, der nicht in der Dokumentklasse „article“, sondern in der Dokumentklasse „book“ definiert ist. Die API passt die Dokumentklasse an, sodass die endgültige Version der reparierten Datei mit `\documentclass{book}` beginnt. Dann findet die Engine den oben genannten `\lhead`-Befehl und stellt fest, dass `\usepackage{fancyhdr}` in die Präambel eingefügt werden muss. Die Befehle `\href` und `\includegraphics`, die später in der Datei auftreten, veranlassen den Repairer, `\usepackage{hyperref}` bzw. `\usepackage{graphics}` in die Präambel einzufügen. Diese Entscheidungen werden auf Grundlage der internen Zuordnungen der API getroffen. Alle diese Reparaturen werden wie bisher in der Protokolldatei protokolliert.

Schließlich wird die Engine abnormal beendet, weil der richtige Abschluss eines LaTeX-Dokuments fehlt. Infolgedessen hängt der Reparaturbetrieb `\end{document}` an das Ende der Datei an und fügt diese Informationen in den Bericht ein.

Nachdem die korrigierte Version der Originaldatei erstellt wurde, führt der Reparierer zur endgültigen Überprüfung einen TeX-Job darauf aus. In unserem Beispiel erkennt dieser Lauf keine kritischen Fehler, sodass die korrigierte Version mehr oder weniger wie erwartet gesetzt werden kann.

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