---
translation: true
template: /templates/_template-net.md
title: LaTeX zu XPS | .NET
linktitle: LaTeX zu XPS
weight: 12
url: /net/latex-to-xps/
description: Mit der Konvertierungsfunktion der Aspose.TeX-API-Lösung für .NET können Sie LaTeX-Dateien in das XPS-Format konvertieren.
lastmod: "2026-04-22"
---

{{<section overview>}}


Ein weiteres Zielformat ist [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Eine **XPS**-Datei ist physisch ein ZIP-Paket, das den paginierten Inhalt eines Dokuments sowie die Metadaten enthält, die für die ordnungsgemäße Anzeige durch bestimmte Viewer (z. B. Windows XPS Viewer) und das Drucken erforderlich sind. Alle Daten in einem Paket werden durch Dateien repräsentiert. Einige davon sind binär und enthalten Ressourcen wie Bilder, Schriftarten und ICC-Profile. Andere sind XML-Dateien in verschiedenen spezifischen Schemata. Zu letzteren zählen Dateien, die die Dokumentdaten selbst enthalten. Dokumentdaten bestehen aus einer Reihe von Dateien – jede Datei enthält Daten für eine einzelne Seite des Dokuments. Solche Dateien bestehen aus einem einzelnen Seitenelement und einem Baum aus untergeordneten Elementen – *Canvas*, *Path* und *Glyphs*. *Canvas* ist ein Gruppierungselement, das andere *Canvases*, *Pfade* und *Glyphen* enthalten kann. Es dient dazu, das Erscheinungsbild aller untergeordneten Elemente als Gruppe zu steuern. *Path*-Elemente werden zum Definieren von Vektorgrafikpfaden verwendet. Und *Glyphen*-Elemente werden verwendet, um Textinhalte zu definieren. Alle drei Elemente verfügen über Eigenschaften, um verschiedene Aspekte des Erscheinungsbilds zu definieren.

Es gibt die Bibliothek [**Aspose.Page**](https://products.aspose.com/page/), die eine API zum Bearbeiten von XPS-Dokumenten sowie zum Konvertieren dieser in PDF- und Rasterbildformate bereitstellt.

## So konvertieren Sie LaTeX in XPS

Die Konvertierung von LaTeX in XPS ist genauso einfach wie die [Konvertierung in Rasterbildformate](/tex/{{lang.url-fragment}}net/latex-to-image/), außer dass [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) auf eine [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/)-Klasseninstanz gesetzt werden MUSS (standardmäßig oder explizit). und das Gerät MUSS in eine Instanz der Klasse [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/) geändert werden.

**Einfachstes Konvertierungsbeispiel**

Das folgende Beispiel zeigt, wie Sie eine LaTeX-Datei in wenigen Schritten in XPS konvertieren:

1. Erstellen Sie eine `TexDocument`-Instanz.
2. Laden Sie die `.tex`-Quelldatei mit T`exDocument.Load`.
3. (Optional) Konfigurieren Sie `XpsSaveOptions`, z. B. Komprimierungseinstellungen.
4. Speichern Sie das Dokument in XPS, indem Sie document.Save mit einem `XpsDevice` aufrufen.

Dieser Code demonstriert den direktesten Weg, eine XPS-Datei aus LaTeX zu erstellen.

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Eine alternative Möglichkeit, die XPS-Hauptausgabedatei zu schreiben

Es gibt einen weiteren Konstruktor der Klasse [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), mit dem wir die resultierende XPS-Datei auf alternative Weise erhalten können.

**Alternatives Konvertierungsbeispiel**

Dieser Codeausschnitt demonstriert die Verwendung des Konstruktors `XpsDevice`, der einen `Stream` akzeptiert. Die Schritte sind:

1. Erstellen Sie ein `TexDocument` und laden Sie die LaTeX-Quelle.
2. Erstellen Sie einen `MemoryStream` für die XPS-Ausgabe.
3. Instanziieren Sie `XpsDevice` mit dem Stream.
4. Speichern Sie das Dokument auf dem Gerät. Anschließend können Sie den Stream verwenden (z. B. über ein Netzwerk senden oder in einer Datenbank speichern).

Dieser Ansatz ist nützlich, wenn Sie die XPS-Daten im Speicher und nicht als Datei auf der Festplatte benötigen.

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

Der Effekt ist derselbe, den wir [hier](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file) erhalten.

**Sie können sich auch die kostenlose LaTeX-zu-XPS-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-xps) ansehen, die auf der Grundlage von [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) erstellt wurde.**
