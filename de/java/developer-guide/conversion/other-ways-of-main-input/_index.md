---
translation: true
template: /templates/_template-java.md
title: Bereitstellung der Haupt-TeX-Eingabedatei | Java
linktitle: Andere Möglichkeiten, die Haupt-TeX-Eingabedatei bereitzustellen
weight: 14
url: /java/other-ways-of-main-input/
description: Die Konvertierungsfunktionalität der Aspose.TeX-API-Lösung für Java verfügt über einen Konstruktor, der einen Stream als erstes Argument akzeptiert.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Bereitstellung der Haupteingabedatei als Stream für die TeX-Engine

Bisher wussten wir nur, wie man die [Haupteingabedatei](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) als Dateinamen an die TeX-Engine übergibt, egal ob vollständig angegeben oder in Kurzform, ob mit oder ohne Erweiterung. Aber es gibt noch einen anderen [Konstruktor](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) der Klasse „TeXJob“, der einen Stream als erstes Argument akzeptiert. Dies ist praktisch, wenn wir aus irgendeinem Grund die Haupteingabedatei in einer anderen Form als einer Datei im Dateisystem der Festplatte haben. So können wir damit umgehen:

Setzen Sie `outputDirectory` auf einen vorhandenen Ausgabeordner. Importieren Sie die in den Beispielen verwendeten Aspose.TeX-Klassen, `com.aspose.tex.rendering.XpsDevice`, `com.aspose.tex.rendering.XpsSaveOptions` und für Streameingaben `java.io.ByteArrayInputStream` und `java.nio.charset.StandardCharsets`. Die aufrufende Methode muss Ausnahmen behandeln oder deklarieren. Wenden Sie eine Lizenz gemäß dem [Lizenzleitfaden](/tex/{{lang.url-fragment}}java/licensing/) an, um Einschränkungen der Evaluierung zu vermeiden. Das Streambeispiel enthält ein vollständiges LaTeX-Dokument und benötigt daher kein Eingabearbeitsverzeichnis. Streams und Geräte bleiben bis zum Ende des Auftrags offen und werden danach geschlossen oder freigegeben.

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-StreamInput-LaTeX.java" >}}

Wenn für die Streameingabe kein Jobname ausdrücklich festgelegt wurde, verwendet die Engine den Standardnamen *texput*. Dieses Beispiel erstellt `texput.xps` und `texput.log`. Verwenden Sie `options.setJobName(...)`, um einen anderen Jobnamen auszuwählen. Einzelheiten zu Jobnamen finden Sie unter [hier](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) und [hier](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name).

## Eingabe der Haupt-TeX-Eingabedatei über das Terminal

Es gibt noch einen weiteren [Konstruktor](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)  der Klasse „TeXJob“, der es uns überhaupt nicht erlaubt, die Eingabe anzugeben. Sie fragen sich vielleicht, was ein solcher TeX-Job verarbeiten wird? Dieses Mal benötigen wir ein Eingabeterminal. Die TeX-Engine fordert uns auf, den Dateinamen vom Terminal einzugeben.

Setzen Sie `inputDirectory` auf einen Ordner mit einem vollständigen LaTeX-Dokument namens `hello-world.ltx` und `outputDirectory` auf einen vorhandenen Ausgabeordner. Führen Sie das Beispiel in einer Konsole aus, geben Sie am `**`-Prompt `hello-world.ltx` ein und drücken Sie die Eingabetaste. Es erstellt `hello-world.xps` und schreibt die Terminalausgabe in die Konsole. Beide Beispiele verwenden `NonstopMode` zur Verarbeitung, aber der Terminalkonstruktor benötigt weiterhin den anfänglichen Dateinamen. Stellen Sie für unbeaufsichtigte Ausführung eine `IInputTerminal`-Implementierung bereit oder verwenden Sie Datei-/Streameingaben.

Hier ist der Code:

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-MainInputTerminal.java" >}}

Sobald es ausgeführt wird, bleibt die Engine hängen und wartet darauf, dass wir den Dateinamen eingeben (mit oder ohne Pfad, mit oder ohne Erweiterung):


![Terminalfenster](/tex/images/java/Conversion-MainInputTerminal.png)

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