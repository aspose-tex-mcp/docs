---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX-Konverter für .NET – FAQ
linktitle: FAQ
type: docs
weight: 90
url: /net/conversion/faq/
description: Häufig gestellte Fragen zur Konvertierung von TeX- und LaTeX-Dateien mit Aspose.TeX für .NET, darunter unterstützte Formate, Konvertierungscode, Ausgabe in Streams, Bildoptionen, Pakete, Evaluierungsmodus und Laufzeitanforderungen.
keywords: Aspose.TeX, .NET, FAQ, LaTeX-Konvertierung, LaTeX in PDF, LaTeX in XPS, LaTeX in SVG, LaTeX in PNG, TeXJob, Lizenzierung, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**F: Welche Eingabe- und Ausgabeformate unterstützt Aspose.TeX für .NET?**

**A:** Aspose.TeX setzt TeX- und LaTeX-Dokumente. Die Haupteingabedatei kann aus einer Datei, einem Stream oder einem Terminal stammen; Dateien, die sie einbindet, können aus einem Ordner oder einem ZIP-Archiv stammen. Separate APIs rendern eine einzelne mathematische LaTeX-Formel oder ein LaTeX-Fragment. Die Ausgabeformate sind PDF, XPS, SVG, PNG, JPEG, BMP und TIFF. Siehe [Unterstützte Dateiformate](/tex/{{lang.url-fragment}}net/supported-file-formats/).
<br><br>

**F: Kann Aspose.TeX LaTeX in Word (DOCX) oder HTML konvertieren?**

**A:** Nein. Aspose.TeX erzeugt nur PDF, XPS, SVG und Rasterbilder. Wenn Sie ein anderes Format benötigen, konvertieren Sie die PDF-Ausgabe mit einer Bibliothek, die dieses Format unterstützt.
<br><br>

**F: Wie konvertiere ich eine LaTeX-Datei in C# in PDF?**

**A:** Erstellen Sie `TeXOptions` für das Format ObjectLaTeX, legen Sie das Ausgabeverzeichnis und `PdfSaveOptions` fest und führen Sie einen `TeXJob` mit einem `PdfDevice` aus:

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

Das Ergebnis wird unter dem Jobnamen in das Ausgabearbeitsverzeichnis geschrieben. Siehe [LaTeX in PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/).
<br><br>

**F: Wie wähle ich das Ausgabeformat?**

**A:** Legen Sie `TeXOptions.SaveOptions` fest und übergeben Sie das passende Gerät an `TeXJob`:

| Format | Speicheroptionen | Gerät |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG, JPEG, BMP, TIFF | `PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions` | `ImageDevice` |

Siehe [LaTeX zu XPS](/tex/{{lang.url-fragment}}net/latex-to-xps/) und [LaTeX zum Bild](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**F: Kann ich das Ergebnis im Speicher statt in einer Datei erhalten?**

**A:** Ja. `PdfDevice` und `XpsDevice` haben Konstruktoren, die einen `Stream` akzeptieren, in den das Dokument geschrieben wird. `ImageDevice` hält die gerenderten Seiten in seiner Eigenschaft `Result` als Array von Byte-Arrays, eines pro Seite. Um die Haupteingabe aus einem Stream zu lesen, übergeben Sie den Stream an den Konstruktor von `TeXJob`. Siehe [LaTeX in PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) und [Andere Möglichkeiten, die Haupt-TeX-Eingabedatei bereitzustellen](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/).
<br><br>

**F: Wie steuere ich Auflösung und Qualität der Bilder?**

**A:** Verwenden Sie die Eigenschaften der Bildspeicheroptionen:

- `Resolution` – Bildauflösung in DPI.
- `SmoothingMode` und `InterpolationMode` – Render-Qualität.
- `TiffSaveOptions.Compression` und `TiffSaveOptions.Multipage` – TIFF-Komprimierung und ob alle Seiten in eine Datei geschrieben werden (mehrseitiges TIFF wird vom Paket `Aspose.TeX.Drawing` noch nicht unterstützt).

Zum Beispiel erzeugt `new PngSaveOptions { Resolution = 300 }` PNG-Bilder mit 300 DPI. Siehe [LaTeX zum Bild](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**F: Wie erkenne ich, ob die Konvertierung erfolgreich war?**

**A:** `TeXJob.Run()` gibt einen `TeXJobResult`-Wert zurück: `Spotless`, `WarningIssued`, `ErrorMessageIssued` oder `FatalErrorStop`. Details werden in die Protokolldatei (`.log`) im Ausgabeverzeichnis und in das Ausgabeterminal geschrieben. Siehe [Die Ausgabeschnittstelle von Aspose.TeX](/tex/{{lang.url-fragment}}net/aspose-tex-output/).
<br><br>

**F: Benötige ich eine LaTeX-Installation (z. B. MiKTeX) auf dem Server?**

**A:** Nein. Aspose.TeX ist eine eigenständige .NET-Bibliothek mit eigener TeX-Engine, eigenem LaTeX-Format und eigenen Schriftarten. Eine externe TeX-Distribution ist nicht erforderlich.
<br><br>

**F: Welche LaTeX-Pakete kann ich verwenden?**

**A:** Aspose.TeX enthält eine Reihe eingebetteter LaTeX-Pakete, siehe [Eingebettete LaTeX-Pakete](/tex/{{lang.url-fragment}}net/embedded-packages/). Um andere Pakete zu verwenden, legen Sie deren Dateien in einen Ordner oder ein ZIP-Archiv und geben Sie es als `TeXOptions.RequiredInputDirectory` an, siehe [Externe LaTeX-Pakete](/tex/{{lang.url-fragment}}net/external-latex-packages/).
<br><br>

**F: Kann ich statt eines ganzen Dokuments eine einzelne Formel oder ein LaTeX-Fragment rendern?**

**A:** Ja. Verwenden Sie `PngMathRenderer` oder `SvgMathRenderer` für mathematische Formeln und `PngFigureRenderer` oder `SvgFigureRenderer` für beliebige LaTeX-Fragmente. Sie geben die Größe des gerenderten Bildes zurück. Siehe [Rendern von LaTeX-Matheformeln](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) und [Rendern von LaTeX-Abbildungen](/tex/{{lang.url-fragment}}net/latex-figure-rendering/).
<br><br>

**F: Welche Laufzeitanforderungen gibt es?**

**A:**

- Paket `Aspose.TeX`: Windows (x64/x86); .NET Framework 4.0 oder neuer, .NET Standard 2.0, .NET 6 oder neuer.
- Paket `Aspose.TeX.Drawing`: Windows, Linux und macOS (x64/Arm64); .NET Framework 4.7.2 oder neuer, .NET 7 oder neuer.
- Zusätzliche native Bibliotheken sind nicht erforderlich. Unter Linux erfordert die Ausgabe in XPS und SVG ICU. Siehe [Systemanforderungen](/tex/{{lang.url-fragment}}net/system-requirements/) und [Linux, macOS und Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).
<br><br>

**F: Welche Einschränkungen hat die Evaluierungsversion?**

**A:** Ohne Lizenz arbeitet Aspose.TeX im Evaluierungsmodus: Es gibt höchstens vier Seiten eines Dokuments aus, und die Seiten tragen ein Evaluierungswasserzeichen. Die Evaluierungsversion ist dasselbe Paket; um ohne Einschränkungen zu testen, fordern Sie eine [temporäre 30-Tage-Lizenz](https://purchase.aspose.com/temporary-license/) an. Siehe [Lizenzierung](/tex/{{lang.url-fragment}}net/licensing/).
<br><br>

**F: Wie wende ich eine Lizenz im Code an?**

**A:** Wenden Sie die Lizenz einmal vor der ersten Konvertierung an:

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

Sie können die Lizenz auch aus einem Stream laden oder eine getaktete (metered) Lizenz verwenden. Siehe [Lizenzierung](/tex/{{lang.url-fragment}}net/licensing/). Preise finden Sie auf der [Preisseite von Aspose.TeX](https://purchase.aspose.com/pricing/tex/).
<br><br>

**F: Wo finde ich API-Dokumentation, Beispiele und Support?**

**A:**

- [Entwicklerhandbuch](https://docs.aspose.com/tex/net/)
- [API-Referenz](https://reference.aspose.com/tex/net/)
- [Community-Forum](https://forum.aspose.com/c/tex/)
<br><br>
