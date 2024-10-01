---
translation: true
template: /templates/_template-net.md
title: LaTeX zu XPS | Aspose.TeX für .NET
linktitle: LaTeX zu XPS
weight: 12
url: /net/latex-to-xps/
aliases: /net/other-target-formats/
description: Mit der Konvertierungsfunktion der Aspose.TeX-API-Lösung für .NET können Sie LaTeX-Dateien in das XPS-Format konvertieren. Hier sind einige Codebeispiele.
lastmod: "2024-09-26"
---

{{<section overview>}}


Ein weiteres Zielformat ist [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Eine **XPS**-Datei ist physisch ein ZIP-Paket, das den paginierten Inhalt eines Dokuments sowie die Metadaten enthält, die für die ordnungsgemäße Anzeige durch bestimmte Viewer (z. B. Windows XPS Viewer) und das Drucken erforderlich sind. Alle Daten in einem Paket werden durch Dateien repräsentiert. Einige davon sind binär und enthalten Ressourcen wie Bilder, Schriftarten und ICC-Profile. Andere sind XML-Dateien in verschiedenen spezifischen Schemata. Zu letzteren zählen Dateien, die die Dokumentdaten selbst enthalten. Dokumentdaten bestehen aus einer Reihe von Dateien – jede Datei enthält Daten für eine einzelne Seite des Dokuments. Solche Dateien bestehen aus einem einzelnen Seitenelement und einem Baum aus untergeordneten Elementen – *Canvas*, *Path* und *Glyphs*. *Canvas* ist ein Gruppierungselement, das andere *Canvases*, *Pfade* und *Glyphen* enthalten kann. Es dient dazu, das Erscheinungsbild aller untergeordneten Elemente als Gruppe zu steuern. *Path*-Elemente werden zum Definieren von Vektorgrafikpfaden verwendet. Und *Glyphen*-Elemente werden verwendet, um Textinhalte zu definieren. Alle drei Elemente verfügen über Eigenschaften, um verschiedene Aspekte des Erscheinungsbilds zu definieren.

Es gibt die Bibliothek [**Aspose.Page**](https://products.aspose.com/page/), die eine API zum Bearbeiten von XPS-Dokumenten sowie zum Konvertieren dieser in PDF- und Rasterbildformate bereitstellt.

## So konvertieren Sie LaTeX in XPS

Die Konvertierung von LaTeX in XPS ist genauso einfach wie die [Konvertierung in Rasterbildformate](/tex/{{lang.url-fragment}}net/latex-to-image/), außer dass [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) auf eine [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/)-Klasseninstanz gesetzt werden MUSS (standardmäßig oder explizit). und das Gerät MUSS in eine Instanz der Klasse [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/) geändert werden.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.cs" >}}

### Eine alternative Möglichkeit, die XPS-Hauptausgabedatei zu schreiben

Es gibt einen weiteren Konstruktor der Klasse [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), mit dem wir die resultierende XPS-Datei auf alternative Weise erhalten können.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.cs" >}}

Der Effekt ist derselbe, den wir [hier](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file) erhalten.

**Sie können sich auch die kostenlose LaTeX-zu-XPS-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-xps) ansehen, die auf der Grundlage von [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) erstellt wurde.**