---
translation: true
template: /templates/_template-java.md
title: LaTeX zu XPS | Java
linktitle: LaTeX zu XPS
weight: 12
url: /java/latex-to-xps/
description: Mit der Konvertierungsfunktion der Aspose.TeX-Lösung für Java können Sie LaTeX-Dateien in das XPS-Format konvertieren. Lernen Sie die Codebeispiele kennen.
lastmod: "2024-09-26"
---

{{<section overview>}}


Ein weiteres Zielformat ist [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Eine **XPS**-Datei ist physisch ein ZIP-Paket, das den paginierten Inhalt eines Dokuments sowie die Metadaten enthält, die für die ordnungsgemäße Anzeige durch bestimmte Viewer (z. B. Windows XPS Viewer) und das Drucken erforderlich sind. Alle Daten in einem Paket werden als Dateien in Verzeichnissen organisiert. Einige davon enthalten Ressourcen wie Bilder, Schriftarten und ICC-Profile. Andere sind XML-Dateien in verschiedenen spezifischen Schemata. Zu letzteren zählen Dateien, die die Dokumentdaten selbst enthalten. Dokumentdaten sind eine Reihe von Dateien – jede Datei enthält Daten für eine einzelne Seite des Dokuments. Solche Dateien bestehen aus einem einzelnen Seitenelement und einem Baum aus untergeordneten Elementen – *Canvas*, *Path* und *Glyphs*. *Canvas* ist ein Gruppierungselement, das andere *Canvases*, *Pfade* und *Glyphen* enthalten kann. Sein Zweck ist die Kontrolle über das Erscheinungsbild aller untergeordneten Elemente als Gruppe. *Path*-Elemente werden zum Definieren von Vektorgrafikpfaden verwendet. Und *Glyphen*-Elemente werden verwendet, um Textinhalte zu definieren. Alle drei Elemente verfügen über Eigenschaften, um verschiedene Aspekte des Erscheinungsbilds zu definieren.

Es gibt die Bibliothek [**Aspose.Page**](https://products.aspose.com/page/), die eine API zum Bearbeiten von XPS-Dokumenten sowie zum Konvertieren dieser in PDF- und Rasterbildformate bereitstellt.

## So konvertieren Sie LaTeX in XPS

Die Konvertierung in XPS ist genauso einfach wie die [Konvertierung in Rasterbildformate](/tex/{{lang.url-fragment}}java/latex-to-image/), außer dass wir zusätzlich zu den [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--) eine Instanz der Klasse [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice) verwenden müssen.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.java" >}}

### Eine alternative Möglichkeit, die XPS-Hauptausgabedatei zu schreiben

Es gibt einen weiteren Konstruktor der Klasse [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice#XpsDevice-java.io.OutputStream-), der es uns ermöglicht, die resultierende XPS-Datei auf alternative Weise abzurufen.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.java" >}}

Der Effekt ist derselbe, den wir [hier](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file) erhalten.

**Sie können sich auch die kostenlose LaTeX-zu-XPS-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-xps) ansehen, die auf der [Aspose.TeX for .NET](https://products.aspose.com/tex/net/)-API basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**