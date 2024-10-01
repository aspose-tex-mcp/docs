---
translation: true
template: /templates/_template-java.md
title: Andere TeX-Verwaltungsoptionen | Java
linktitle: Andere Optionen
weight: 17
url: /java/other-options/
description: Mit der Konvertierungsfunktion der Aspose.TeX-API-Lösung für Java können Sie den anfänglichen Interaktionsmodus festlegen, in dem die Engine startet. Hier sind einige Codebeispiele.
lastmod: "2024-09-26"
---

{{<section overview>}}


## So legen Sie den Interaktionsmodus fest

Wie wir [hier](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes) erwähnt haben, können wir mit **Aspose.TeX für Java** den anfänglichen Interaktionsmodus festlegen, in dem die Engine startet. So machen wir es:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-InteractionMode.java" >}}

## So legen Sie den Jobnamen fest

Wenn wir die Haupteingabedatei als Dateinamen übergeben, erhalten wir Ausgabedateien mit demselben Namen, allerdings mit anderen Erweiterungen. Die TeX-Engine nennt den Namen der Eingabedatei den *Jobnamen* und verwendet ihn für Ausgabedateien, außer in Fällen, in denen Hilfsdateien mit explizit angegebenen anderen Namen geschrieben werden. Wenn wir die Haupteingabedatei als [stream](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream) übergeben, verwendet die TeX-Engine den Standard-Jobnamen, der *texput* ist.
In beiden Fällen können wir den Jobnamen überschreiben, indem wir die entsprechende Konvertierungsoption zuweisen.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-JobName.java" >}}

## Wie man „die Zeit anhält“

LaTeX verfügt über eine Funktion zum automatischen Generieren eines Titels aus einigen Definitionen in der Präambel. Dieser Titel enthält normalerweise das aktuelle Datum. Möglicherweise möchten wir das Datum auf einen gewünschten Wert einfrieren. So geht's:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-DateTime.java" >}}

## So ignorieren Sie fehlende Pakete

Möglicherweise möchten wir eine LaTeX-Datei konvertieren, die auf einige Pakete verweist, die von der Aspose.TeX für .NET-Bibliothek nicht unterstützt werden. In diesem Fall stoppt die TeX-Engine mit einem Fehler, wenn sie versucht, ein solches Paket zu laden. Um dies zu vermeiden, können wir die folgende Option verwenden:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.java" >}}

## So vermeiden Sie die Bildung von Ligaturen

Normalerweise erstellt die TeX-Engine Ligaturen für bestimmte Zeichenpaare, wenn die Schriftart die dafür erforderlichen Daten bereitstellt. Mit dem folgenden Code können wir die Engine anweisen, die Ligaturbildung zu überspringen:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-NoLigatures.java" >}}

## So wiederholen Sie den Job

Wie wir [oben](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) in Bezug auf Etiketten und Referenzen erwähnt haben, gibt es Fälle, in denen wir denselben Job möglicherweise zweimal ausführen möchten. So kann es gemacht werden:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-Repeat.java" >}}

## So wandeln Sie mathematische Formeln in Rasterbilder um

Manchmal benötigen wir möglicherweise mathematische Formeln als Rasterbilder, anstatt sie in Schriftarten einzugeben. Hierzu kann folgende Möglichkeit dienen:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RasterizeFormulas.java" >}}

## So wandeln Sie Grafiken in Rasterbilder um

Mit der ObjectTeX-Engine können wir Grafikdateien in Rasterformaten (PNG und JPG) sowie in den Formaten PS (EPS) und XPS (OXPS) einbinden. Die letzten beiden Formate enthalten normalerweise Vektorelemente und Texte. Um sie zu gerastern und als Vollbilder einzubinden, können wir die folgende Option verwenden:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.java" >}}

## So unterteilen Sie Schriftarten

Wenn wir die Größe der Ausgabedatei reduzieren möchten, können wir auf die Unterteilung von Schriftarten zurückgreifen, was bedeutet, dass die Schriftarten im Ausgabedokument nur Daten über die Glyphen enthalten, die im Dokument verwendet werden. So können wir das Problem lösen:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-SubsetFonts.java" >}}