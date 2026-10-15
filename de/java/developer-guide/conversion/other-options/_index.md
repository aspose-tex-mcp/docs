---
translation: true
template: /templates/_template-java.md
title: Andere TeX-Verwaltungsoptionen | Java
linktitle: Andere Optionen
weight: 17
url: /java/other-options/
description: Mit der Konvertierungsfunktion der Aspose.TeX-API-Lösung für Java können Sie den anfänglichen Interaktionsmodus festlegen, in dem die Engine startet. 
lastmod: "2024-09-26"
---

{{<section overview>}}


Jedes Beispiel erstellt LaTeX-`TeXOptions` und konfiguriert eine Option. Übergeben Sie diese Optionen an einen `TeXJob`, stellen Sie geeignete LaTeX-Eingaben bereit und legen Sie vor der Ausführung ein Ausgabearbeitsverzeichnis fest. Importieren Sie `com.aspose.tex.TeXOptions`, `TeXConfig` und die Klassen aus dem gewählten Beispiel: `Interaction`, `com.aspose.tex.rendering.XpsSaveOptions` oder `PdfSaveOptions` sowie `java.util.Calendar`/`GregorianCalendar` für das Datumsbeispiel. Behandeln oder deklarieren Sie Ausnahmen in der aufrufenden Methode. Die Beispiele zur Rasterisierung und zu Schriftteilmengen verwenden `PdfSaveOptions`; rendern Sie mit einem kompatiblen `PdfDevice`. Wenden Sie eine Lizenz gemäß dem [Lizenzleitfaden](/tex/{{lang.url-fragment}}java/licensing/) an.

## So legen Sie den Interaktionsmodus fest

Wie wir [hier](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes) erwähnt haben, können wir mit **Aspose.TeX für Java** den anfänglichen Interaktionsmodus festlegen, in dem die Engine startet. So machen wir es:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-InteractionMode.java" >}}

## So legen Sie den Jobnamen fest

Wenn wir die Haupteingabedatei als Dateinamen übergeben, erhalten wir Ausgabedateien mit demselben Namen, allerdings mit anderen Erweiterungen. Die TeX-Engine nennt den Namen der Eingabedatei den *Jobnamen* und verwendet ihn für Ausgabedateien, außer in Fällen, in denen Hilfsdateien mit explizit angegebenen anderen Namen geschrieben werden. Wenn wir die Haupteingabedatei als [stream](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream) übergeben, verwendet die TeX-Engine den Standard-Jobnamen, der *texput* ist.
In beiden Fällen können wir den Jobnamen überschreiben, indem wir die entsprechende Konvertierungsoption zuweisen.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-JobName.java" >}}

## Wie man „die Zeit anhält“

LaTeX verfügt über eine Funktion zum automatischen Generieren eines Titels aus einigen Definitionen in der Präambel. Dieser Titel enthält normalerweise das aktuelle Datum. Möglicherweise möchten wir das Datum auf einen gewünschten Wert einfrieren. So geht's:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-DateTime.java" >}}

## So ignorieren Sie fehlende Pakete

Eine LaTeX-Datei kann auf Pakete verweisen, die in der Bibliothek Aspose.TeX für Java nicht verfügbar sind. Die Engine stoppt normalerweise mit einem Fehler, wenn sie versucht, ein solches Paket zu laden. Verwenden Sie `ignoreMissingPackages(true)`, um nicht verfügbare Pakete zu überspringen. Dadurch werden die Befehle dieser Pakete nicht bereitgestellt; die Eingabe darf nicht von ihnen abhängen.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-IgnoreMissingPackages.java" >}}

## So vermeiden Sie die Bildung von Ligaturen

Normalerweise erstellt die TeX-Engine Ligaturen für bestimmte Zeichenpaare, wenn die Schriftart die dafür erforderlichen Daten bereitstellt. Mit dem folgenden Code können wir die Engine anweisen, die Ligaturbildung zu überspringen:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-NoLigatures.java" >}}

## So wiederholen Sie den Job

Wie wir [oben](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) in Bezug auf Etiketten und Referenzen erwähnt haben, gibt es Fälle, in denen wir denselben Job möglicherweise zweimal ausführen möchten. So kann es gemacht werden:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-Repeat.java" >}}

## So wandeln Sie mathematische Formeln in Rasterbilder um

Manchmal benötigen wir möglicherweise mathematische Formeln als Rasterbilder, anstatt sie in Schriftarten einzugeben. Hierzu kann folgende Möglichkeit dienen:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeFormulas.java" >}}

## So wandeln Sie Grafiken in Rasterbilder um

Mit der ObjectTeX-Engine können wir Grafikdateien in Rasterformaten (PNG und JPG) sowie in den Formaten PS (EPS) und XPS (OXPS) einbinden. Die letzten beiden Formate enthalten normalerweise Vektorelemente und Texte. Um sie zu gerastern und als Vollbilder einzubinden, können wir die folgende Option verwenden:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeIncludedGraphics.java" >}}

## So unterteilen Sie Schriftarten

Schriftteilmengen begrenzen eingebettete Schriftarten auf die im Dokument verwendeten Glyphen. Die Auswirkung auf die Ausgabegröße hängt von der Schriftart und ihrer Einbettung durch das Ausgabegerät ab. Weisen Sie Speicheroptionen zu, bevor Sie `subsetFonts(true)` aktivieren, wie unten gezeigt:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-SubsetFonts.java" >}}