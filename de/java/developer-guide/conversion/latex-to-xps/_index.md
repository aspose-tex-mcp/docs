---
translation: true
template: /templates/_template-java.md
title: LaTeX zu XPS | Java
linktitle: LaTeX zu XPS
weight: 12
url: /java/latex-to-xps/
description: Mit der Konvertierungsfunktion der Aspose.TeX-Lösung für Java können Sie LaTeX-Dateien in das XPS-Format konvertieren. Lernen Sie die Codebeispiele kennen.
lastmod: "2026-04-21"
---

{{<section overview>}}


Ein weiteres Zielformat ist [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Eine **XPS**-Datei ist physisch ein ZIP-Paket, das den paginierten Inhalt eines Dokuments sowie die Metadaten enthält, die für die ordnungsgemäße Anzeige durch bestimmte Viewer (z. B. Windows XPS Viewer) und das Drucken erforderlich sind. Alle Daten in einem Paket werden als Dateien in Verzeichnissen organisiert. Einige davon enthalten Ressourcen wie Bilder, Schriftarten und ICC-Profile. Andere sind XML-Dateien in verschiedenen spezifischen Schemata. Zu letzteren zählen Dateien, die die Dokumentdaten selbst enthalten. Dokumentdaten sind eine Reihe von Dateien – jede Datei enthält Daten für eine einzelne Seite des Dokuments. Solche Dateien bestehen aus einem einzelnen Seitenelement und einem Baum aus untergeordneten Elementen – *Canvas*, *Path* und *Glyphs*. *Canvas* ist ein Gruppierungselement, das andere *Canvases*, *Pfade* und *Glyphen* enthalten kann. Sein Zweck ist die Kontrolle über das Erscheinungsbild aller untergeordneten Elemente als Gruppe. *Path*-Elemente werden zum Definieren von Vektorgrafikpfaden verwendet. Und *Glyphen*-Elemente werden verwendet, um Textinhalte zu definieren. Alle drei Elemente verfügen über Eigenschaften, um verschiedene Aspekte des Erscheinungsbilds zu definieren.

Es gibt die Bibliothek [**Aspose.Page**](https://products.aspose.com/page/), die eine API zum Bearbeiten von XPS-Dokumenten sowie zum Konvertieren dieser in PDF- und Rasterbildformate bereitstellt.

## So konvertieren Sie LaTeX in XPS

Die Konvertierung in XPS ist genauso einfach wie die [Konvertierung in Rasterbildformate](/tex/{{lang.url-fragment}}java/latex-to-image/), außer dass wir zusätzlich zu den [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) eine Instanz der Klasse [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) verwenden müssen.

Setzen Sie `inputFile` auf den vollständigen Pfad Ihrer LaTeX-Datei, beispielsweise `hello-world.ltx`, und `outputDirectory` auf einen vorhandenen Ausgabeordner. Importieren Sie die im Beispiel verwendeten Klassen aus `com.aspose.tex` und `com.aspose.tex.rendering`. Die aufrufende Methode muss Ausnahmen behandeln oder deklarieren. Wenden Sie eine Lizenz gemäß der [Lizenzierungsanleitung](/tex/{{lang.url-fragment}}java/licensing/) an, um Evaluierungseinschränkungen zu vermeiden. Das Beispiel verwendet einen nichtinteraktiven Modus und schließt seine Ausgaberessourcen. Für die eigenständige Eingabedatei `hello-world.ltx` lautet die Standardausgabe `hello-world.xps`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### Eine alternative Möglichkeit, die XPS-Hauptausgabedatei zu schreiben

Es gibt einen weiteren Konstruktor der Klasse [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-), der es uns ermöglicht, die resultierende XPS-Datei auf alternative Weise abzurufen.

Verwenden Sie dieselben Werte für `inputFile` und `outputDirectory` wie oben. Setzen Sie `xpsFile` auf einen `java.nio.file.Path`, beispielsweise `Paths.get(outputDirectory, "any-name.xps")`. Importieren Sie zusätzlich zu den Aspose.TeX-Klassen `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path` und `java.nio.file.Paths`. Der Stream bestimmt das Ziel der XPS-Datei; Hilfsdateien werden weiterhin in `outputDirectory` geschrieben.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

Der Effekt ist derselbe, den wir [hier](/tex/{{lang.url-fragment}}java/latex-to-pdf/#eine-alternative-möglichkeit-die-hauptausgabe-pdf-datei-zu-schreiben) erhalten.

**Sie können sich auch die kostenlose LaTeX-zu-XPS-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-xps) ansehen, die auf der [Aspose.TeX for .NET](https://products.aspose.com/tex/net/)-API basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**