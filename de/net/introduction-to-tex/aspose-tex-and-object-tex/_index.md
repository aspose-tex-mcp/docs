---
translation: true
template: /templates/_template-net.md
linktitle: Object TeX
title: Aspose.TeX und Object TeX 
weight: 11
url: /net/aspose-tex-and-object-tex/
description: TeX ist ein Eingabe- und Ausgabeformat dieser API-Lösung. Daher erklären wir hier das Object TeX und wie es in ein Zielformat umgewandelt wird.
lastmod: "2026-11-04"
---

{{<section overview>}}

## Object TeX

Betrachten wir nun das Ausgabeformat.

Das ursprüngliche TeX konnte Dateien nur im *DVI*-Format (DeVice Independent) ausgeben. Es kam vor, dass das DVI-Format keine Metriken eines Mediums definiert, auf dem eine Datei gedruckt werden soll – die Seitengröße und die Position der oberen linken Ecke des gesamten Seiteninhalts. Sobald wir uns entscheiden, die TeX-Engine in die Lage zu versetzen, Dateien beispielsweise im PDF-Format auszugeben, müssen wir solche Metriken definieren. Daher müssen wir neue Grundelemente in den Satz der ursprünglichen TeX-Engine aufnehmen. Und dies wäre eine Erweiterung des Motors selbst.

Das ist *Object* TeX. Auch hier gilt: **Einerseits handelt es sich um eine Programmiersprache mit dem Satz von VirTeX-Grundelementen, die durch neue Grundelemente erweitert werden, die durch neue Ausgabeanforderungen auferlegt werden. Andererseits handelt es sich um eine erweiterte TeX-Engine, die auch neue Grundelemente versteht. Und drittens ist Object TeX ein insgesamt neues Satzsystem.**

Da ist die vierte Hand. Das Object TeX-Format ist ebenfalls ein auf Plain TeX basierendes Format, das Definitionen enthält, die neue Grundelemente beinhalten, z. B. die Zuweisung von Standardwerten zu Medienmetriken.

## Aspose.TeX

Und Aspose.TeX ist nur eine API zum Object TeX-System.

## Warum ist das neue TeX Object? {#why-the-new-tex-is-object}

Warum haben wir also „Object“ im Namen des Systems verwendet? Der Grund dafür ist, dass die eigentliche Ausgabe der Object TeX-Engine keine Datei im Ausgabeformat ist, sondern ein Zwischenmodell *Objekt*, das dann in ein Zielformat umgewandelt wird.

## Einschränkungen nativer Engines vs. Flexibilität in einer Managed-Umgebung

Beim Übergang von traditionellen, über die Befehlszeile gesteuerten TeX-Distributionen (wie TeX Live oder MiKTeX) zu einer .NET-basierten Bibliothek wie Aspose.TeX vollzieht sich für Entwickler ein grundlegender Wandel: von einer an das Dateisystem gebundenen, prozessorientierten Ausführung hin zu einer flexiblen, objektorientierten Architektur.

Im Folgenden werden die Einschränkungen nativer TeX-Engines der Flexibilität einer Managed-Umgebung (wie sie Aspose.TeX bietet) gegenübergestellt – aufbereitet für technische Dokumentationen und Entwicklerhandbücher.

1. Dateisystem- und I/O-Architektur

**Einschränkungen nativer TeX-Engines:**

- Traditionelle TeX-Engines (wie pdfTeX oder XeTeX) sind fest an das lokale Dateisystem gebunden. Sie setzen voraus, dass Dateipfade auf physische Verzeichnisse auf dem Datenträger verweisen.
- Die Ausführung nativer Prozesse auf einem Server erfordert häufig die Vergabe von Lese- und Schreibrechten für verschiedene Systempfade. Dies birgt Sicherheitsrisiken, falls nicht vertrauenswürdige `.tex`-Eingabedaten versuchen, auf andere Verzeichnisse zuzugreifen oder geschützte Systemdateien zu öffnen.
- Um dynamische oder in einer Datenbank gespeicherte LaTeX-Inhalte mit einer nativen TeX-Engine zu verarbeiten, müssen diese zunächst als temporäre Dateien auf den Datenträger geschrieben werden. Dies verursacht unnötigen I/O-Aufwand und erschwert die anschließende Bereinigung.

**Flexibilität durch Aspose.TeX:**

- Aspose.TeX entkoppelt die Engine von physischen Dateipfaden auf dem Datenträger, indem es die Schnittstellen `IInputWorkingDirectory` und `IOutputWorkingDirectory` verwendet.
- Entwickler können Daten nahtlos aus Memory-Streams, ZIP-Archiven oder benutzerdefinierten Datenquellen lesen und in diese schreiben, ohne auf den lokalen Datenträger zugreifen zu müssen.

2. Fehlerbehandlung und Ausführung auf Servern

**Einschränkungen nativer TeX-Engines:**

- Stößt ein herkömmlicher TeX-Compiler auf eine fehlende Schriftart, ein undefiniertes Makro oder einen Syntaxfehler, stürzt er nicht einfach ab – er unterbricht oft die Ausführung und wechselt in einen interaktiven Eingabemodus. Dies führt dazu, dass Webanwendungen oder Hintergrunddienste (Worker Services) dauerhaft blockiert werden.

**Flexibilität durch Aspose.TeX:**

- Da Aspose.TeX vollständig innerhalb der .NET-Laufzeitumgebung läuft, meldet es Kompilierungsprobleme und fehlende Abhängigkeiten über den von `TeXJob.Run()` zurückgegebenen Wert `TeXJobResult`. Die Details werden in das Protokoll (`.log`) und das Ausgabeterminal geschrieben.
- Wenn die Option `Interaction` auf `NonstopMode` oder `BatchMode` gesetzt ist, wartet ein Job nicht auf Benutzereingaben. So können Cloud-Funktionen, Microservices und Hintergrund-Warteschlangen fehlerhafte Dokumente sauber behandeln, Fehler protokollieren und passende HTTP-Statuscodes oder Fehlermeldungen zurückgeben, ohne Server-Threads zu blockieren.

3. Nebenläufigkeit und Threadsicherheit

**Einschränkungen von nativem TeX:**

- Herkömmliche CLI-Tools sind für eine sequentielle Ausführung in einer einzelnen Instanz konzipiert. Um mehrere Instanzen gleichzeitig auszuführen, müssen separate Prozesse auf Betriebssystemebene gestartet werden – was rechenintensiv ist und bei hoher Last nur schwer skaliert werden kann.

**Flexibilität durch Aspose.TeX:**

- Da Aspose.TeX Satzaufträge in isolierten `TeXJob`- und `TeXOptions`-Objektinstanzen kapselt, können Entwickler mehrere Dokumente gleichzeitig in einer .NET-Umgebung mit Multithreading verarbeiten (unter Einhaltung der üblichen Regeln zur Threadsicherheit bei Objektinstanzen).