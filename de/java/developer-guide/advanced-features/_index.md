---
translation: true
template: /templates/_template-java.md
title: Erweiterte Funktionen | Aspose.TeX für Java
linktitle: Erweiterte Funktionen
weight: 20
url: /java/advanced-features/
description: Die Funktionen der Aspose.TeX-API-Lösung für Java zusammengestellt, die auf der Grundlage der Object TeX/LaTeX-Implementierung erstellt wurde.
lastmod: "2026-05-28"
---

{{<section overview>}}


Willkommen im erweiterten Entwicklerhandbuch für Aspose.TeX für Java. Neben der Standard-Dokumentenkompilierung bietet die Aspose.TeX-Engine Low-Level-Hooks für die Dateisystemabstraktion, benutzerdefinierte Makropakete, Speicherstream-Verfolgung und Headless-Server-Optimierung. In diesem Teil werden die Funktionen von Aspose.TeX besprochen, die auf der Grundlage der Object TeX/LaTeX-Implementierung basieren.

**LaTeX-Figuren-Rendering** in Aspose.TeX für Java erklärt, wie isolierte LaTeX-Fragmente (wie Zeichnungen, Plots oder Strukturdiagramme) als eigenständige Bilder extrahiert und gerrendert werden, die völlig unabhängig vom Layout der gesamten Dokumentenseite sind. Die API enthält diese Funktion als strukturelle Verallgemeinerung der Engine für das Rendern mathematischer Formeln.

Die Seite **LaTeX-Grafikeinbettung** erklärt, wie externe Bild-Assets (wie Diagramme, Grafiken oder Fotos) während der Kompilierung mit der Aspose.TeX für Java-API in ein TeX-Dokument importiert und eingebettet werden.

Die Seite hebt zwei Möglichkeiten hervor, dies über die Schnittstelle `IInputWorkingDirectory` zu handhaben:

- Dateisystem-Ansatz: Verwendung von `PhysicalFileSystemInputWorkingDirectory`, um die Engine auf ein physisches Verzeichnis auf einer lokalen Festplatte zu verweisen, in dem sich die Bilder befinden.

- Stream-/Speicher-Ansatz: Implementierung eines benutzerdefinierten Stream-Anbieters, um Bilder direkt aus dem Speicher, Cloud-Speicher oder Datenbanken unter Verwendung des Dateinamens als Suchschlüssel abzurufen.

Die Seite **LaTeX-Formel-Rendering** erklärt, wie isolierte mathematische LaTeX-Formeln in eigenständige Grafiken (PNG oder SVG) gerendert werden, die völlig unabhängig von einem vollständigen Dokument sind, was ideal für das Einbetten von Formeln in Webanwendungen, Desktop-Benutzeroberflächen oder Datenbankspeicher ist.

Die Seite **LaTeX-Dateireparatur** führt die Funktion `LaTeXRepairer` ein, die fehlerhafte oder unvollständige Textdateien, denen obligatorische LaTeX-Komponenten fehlen, programmgesteuert validiert, strukturiert und repariert. Dadurch können beschädigte oder schlecht strukturierte TeX-Dateien ohne manuelles Eingreifen erfolgreich kompiliert werden.