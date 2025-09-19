---
translation: true
template: /templates/_template-net.md
title: LaTeX-Eingabe/Ausgabe
linktitle: LaTeX-E/A
weight: 17
url: /net/latex-io/
description: Hier werden die Besonderheiten der Arbeit mit LaTeX als Ausgabe- bzw. Eingabeformat und der *.aux*-Datei als zwingender Bestandteil von LaTeX beschrieben.
keywords: Latex io, Latex i, Latex o, Latex-Eingabedatei, Eingabe in Latex
lastmod: "2024-09-26"
---

{{<section overview>}}

## LaTeX-Datei

Wenn wir eine [TeX-Datei](/tex/{{lang.url-fragment}}net/tex-io/#tex-file) haben, die die folgende Struktur hat, dann nennen wir diese Datei eine *LaTeX-Datei*:


```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

Dabei ist „<eine Dokumentklasse>“ der Name einer [Dokumentklasse](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes), bei der es sich um eine Eingabe-TeX-Datei handelt, die das Erscheinungsbild der Seiten und Makros des Ausgabedokuments definiert, die für einen bestimmten Dokumenttyp am besten geeignet sind.

Um ehrlich zu sein, können Sie vor `\documentclass{}` primitive Kontrollsequenzen einfügen, wie `\nonstopmode` usw. Aber jedes LaTeX-Makro prüft, ob es sich in einem richtigen Teil einer Datei befindet.

Im Zusammenhang mit der Arbeit mit LaTeX-Dateien gibt es einige erwähnenswerte Dinge zu TeX [input](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) und [output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).

## LaTeX-Ausgabedatei

Ein typischer LaTeX-Job erstellt eine Hilfsausgabedatei mit dem Namen [Jobname](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) und der Erweiterung *.aux*. Diese Datei enthält normalerweise Referenzdaten, die die Engine während der Jobausführung sammelt, wenn Sie beispielsweise Beschriftungen für mathematische Formeln (Gleichungen) festlegen und dann irgendwo im Text darauf verweisen. Falls Sie nichts dergleichen verwenden, enthält diese Datei nur die Steuersequenz `\relax` (eines der TeX-Grundelemente). Seien Sie also nicht überrascht.

Obwohl die Grundelemente `\openout`, `\write` und `\closeout` nicht verboten sind, sind Pakete der am besten geeignete Ort dafür. Daher sollten Sie sie besser in Ihren eigenen benutzerdefinierten Paketen verwenden, wenn Sie sie entwickeln.

Andere Teile der Ausgabe sind willkürlich, folgen ebenfalls dem allgemeinen [TeX-Ausgabe](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)-Konzept und hängen davon ab, was genau Ihre TeX-Datei (Programm) tun soll, welche Pakete (siehe unten) Sie verwenden usw.

## LaTeX-Eingabedatei

Die oben genannte *.aux*-Datei ist gleichzeitig zwingender Bestandteil der Eingabe in LaTeX. Algorithmisch kann LaTeX diese referenzbezogenen Aufgaben nicht in einem einzigen Lauf erledigen, daher muss derselbe Job zweimal ausgeführt werden – das erste Mal, um Daten zu sammeln, das zweite Mal, um diese Daten zu verwenden. Viele LaTeX-basierte Softwaresysteme führen LaTeX-Jobs automatisch zweimal aus. Spoiler: Es gibt eine [Option](/tex/{{lang.url-fragment}}net/other-options/#how-to-repeat-the-job) in der Aspose.TeX-API, mit der wir dieses Verhalten steuern können.

Ein weiterer obligatorischer Teil ist eine [Dokumentklasse](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Die Dokumentklassendatei wiederum kann implizit von anderen Dateien abhängen, die somit ebenfalls in die LaTeX-Eingabe einbezogen werden.

Wenn Sie Funktionen verwenden möchten, die über den Umfang des grundlegenden LaTeX und seiner Dokumentklassen hinausgehen, aber von einer bestimmten TeX-Engine-Implementierung unterstützt werden, verwenden Sie normalerweise ein Paket, über das Sie die Engine in der Präambel informieren müssen. Ein *LaTeX-Paket* ist eine Datei oder eine Gruppe von Dateien, die unter einem Namen zusammengefasst sind und solche Funktionen bereitstellen. Um die Engine zu benachrichtigen, müssen Sie den Befehl `\usepackage` mit dem Paketnamen und wegzulassenden Optionen verwenden, sofern das Paket welche definiert.

Zum Beispiel,


```tex
\usepackage[a6paper,landscape]{geometry}
```

Obwohl die Primitive `\closeout`, `\openin`, `\read` und `\closein` nicht verboten sind, sind Pakete der am besten geeignete Ort für sie. Daher sollten Sie sie besser in Ihren eigenen benutzerdefinierten Paketen verwenden, wenn Sie sie entwickeln.

Andere Teile der Eingabe sind willkürlich, folgen ebenfalls dem allgemeinen [TeX-Eingabe](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)-Konzept und hängen davon ab, was genau Ihre TeX-Datei (Programm) tun soll, welche Pakete Sie verwenden usw.