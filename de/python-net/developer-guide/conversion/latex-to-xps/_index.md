---
translation: true
template: /templates/_template-python-net.md
title: LaTeX zu XPS | Aspose.TeX für Python
linktitle: LaTeX zu XPS
weight: 12
url: /python-net/latex-to-xps/
aliases: /python-net/other-target-formats/
description: Aspose.TeX-API-Lösung für Python bietet Konvertierungsfunktionen zum Konvertieren von LaTeX-Dateien in das XPS-Format. Hier sind ein paar Codebeispiele.
lastmod: "2024-09-26"
---

{{<section overview>}}

Ein weiteres Zielformat ist [**XPS**](https://docs.aspose.com/page/net/what-is-xps-file/). Eine [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)-Datei ist im Wesentlichen ein ZIP-Paket, das den paginierten Inhalt eines Dokuments sowie die notwendigen Metadaten für die ordnungsgemäße Anzeige durch bestimmte Viewer (z. B. Windows XPS Viewer) und das Drucken enthält. Das Paket besteht aus verschiedenen Dateien, von denen einige binär sind und Ressourcen wie Bilder, Schriftarten und ICC-Profile enthalten. Andere sind XML-Dateien in bestimmten Schemata, einschließlich Dateien, die die Dokumentdaten selbst enthalten. Die Dokumentdaten sind in mehrere Dateien unterteilt, wobei jede Datei eine einzelne Seite des Dokuments darstellt. Diese Dateien bestehen aus einem einzelnen Seitenelement und einem Baum aus untergeordneten Elementen, einschließlich *Canvas*, *Path* und *Glyphs*. Das *Canvas*-Element ist ein Gruppierungselement, das andere *Canvases*, *Pfade* und *Glyphen* enthalten kann und das Erscheinungsbild aller untergeordneten Elemente als Gruppe steuert. *Path*-Elemente werden zum Definieren von Vektorgrafikpfaden verwendet, während *Glyphs*-Elemente zum Definieren von Textinhalten verwendet werden. Alle drei Elemente verfügen über Eigenschaften, die verschiedene Aspekte des Erscheinungsbilds definieren.

Es gibt die Bibliothek [**Aspose.Page**](https://products.aspose.com/page/), die eine API zur Bearbeitung von XPS-Dokumenten bietet und auch die Konvertierung dieser Dokumente in PDF- und Rasterbildformate ermöglicht.

## Konvertieren von LaTeX in XPS

Der Prozess der Konvertierung von LaTeX in XPS ist ebenso unkompliziert, ähnlich der [Konvertierung in Rasterbildformate](/tex/{{lang.url-fragment}}python-net/latex-to-image/). Allerdings ist es erforderlich, [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) auf eine Instanz der Klasse [XpsSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/) zu setzen (entweder standardmäßig oder explizit) und das Gerät in eine Instanz der Klasse [XpsDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/) zu ändern.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### Eine alternative Möglichkeit, die XPS-Hauptausgabedatei zu schreiben

Für die Klasse *XpsDevice* steht ein alternativer Konstruktor zur Verfügung, der es ermöglicht, die resultierende XPS-Datei auf andere Weise abzurufen.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

Der Effekt ist derselbe, den wir [hier](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file) erhalten.

**Sie können auch die kostenlose [Web-App für die Konvertierung von LaTeX in XPS](https://products.aspose.app/tex/conversion/latex-to-xps) erkunden, die mit der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) entwickelt wurde.**