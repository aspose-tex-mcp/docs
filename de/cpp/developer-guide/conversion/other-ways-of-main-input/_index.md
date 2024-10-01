---
translation: true
template: /templates/_template-cpp.md
title: Andere Möglichkeiten zur Bereitstellung der Haupt-TeX-Eingabedatei | C++
linktitle: Andere Möglichkeiten, die Haupt-TeX-Eingabedatei bereitzustellen
weight: 14
url: /cpp/other-ways-of-main-input/
description: Die Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für C++ verfügt über einen Konstruktor, der einen Stream als erstes Argument akzeptiert. Hier sind einige Codebeispiele.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Bereitstellung der Haupteingabedatei als Stream für die TeX-Engine

Bisher wussten wir nur, wie man die [Haupteingabedatei](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) als Dateinamen an die TeX-Engine übergibt, egal ob vollständig angegeben oder in Kurzform, ob mit oder ohne Erweiterung. Aber es gibt noch einen anderen [Konstruktor](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/) der Klasse „TeXJob“, der einen Stream als erstes Argument akzeptiert. Dies ist praktisch, wenn wir aus irgendeinem Grund die Haupteingabedatei in einer anderen Form als einer Datei im Dateisystem der Festplatte haben. So lässt es sich umsetzen:

```C++
// Create conversion options instance.
...
// Create some device.
...
// Run LaTeX to XPS conversion.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(
    u"\\documentclass{article} \\begin{document} Hello, World! \\end{document}")), device, options)->Run();
```

Beachten Sie, dass alle Ausgabedateien den Namen *texput* haben. Das liegt daran, dass die Engine nirgendwo einen anderen Namen bekommen kann. *texput* ist der Standard-Jobname. [Hier](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) und [hier](/tex/{{lang.url-fragment}}cpp/other-options/#how-to-set-the-job-name) finden Sie Details zu Jobnamen.

## Eingabe der Haupt-TeX-Eingabedatei über das Terminal

Es gibt noch einen weiteren [Konstruktor](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job/main) der Klasse „TeXJob“, mit dem wir die Eingabe überhaupt nicht angeben können. Sie fragen sich vielleicht, was ein solcher TeX-Job verarbeiten wird? Dieses Mal benötigen wir ein Eingabeterminal. Die TeX-Engine fordert uns auf, den Dateinamen vom Terminal einzugeben.

Hier ist der Code:

```C++
// Create conversion options instance.
...
// Run LaTeX to XPS conversion.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<XpsDevice>(), options)->Run();
```

Sobald es ausgeführt wird, bleibt die Engine hängen und wartet darauf, dass wir den Dateinamen eingeben (mit oder ohne Pfad, mit oder ohne Erweiterung):


![Terminalfenster](/tex/images/cpp/Conversion-MainInputTerminal.png)

Und so würde es auf dem Ausgabeterminal, der Konsole, aussehen:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```