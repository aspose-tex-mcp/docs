---
translation: true
template: /templates/_template-net.md
title: Convertitori Aspose.TeX per .NET – Domande frequenti
linktitle: Domande frequenti
type: docs
weight: 90
url: /net/conversion/faq/
description: Domande frequenti sulla conversione di file TeX e LaTeX con Aspose.TeX per .NET, inclusi formati supportati, codice di conversione, output su flussi, opzioni delle immagini, pacchetti, modalità di valutazione e requisiti di runtime.
keywords: Aspose.TeX, .NET, FAQ, conversione LaTeX, LaTeX in PDF, LaTeX in XPS, LaTeX in SVG, LaTeX in PNG, TeXJob, licenze, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**D: Quali formati di input e di output supporta Aspose.TeX per .NET?**

**R:** Aspose.TeX compone documenti TeX e LaTeX. Il file di input principale può provenire da un file, da un flusso o da un terminale; i file che include possono provenire da una cartella o da un archivio ZIP. API separate eseguono il rendering di una singola formula matematica LaTeX o di un frammento LaTeX. I formati di output sono PDF, XPS, SVG, PNG, JPEG, BMP e TIFF. Vedere [Formati di file supportati](/tex/{{lang.url-fragment}}net/supported-file-formats/).
<br><br>

**D: Aspose.TeX può convertire LaTeX in Word (DOCX) o HTML?**

**R:** No. Aspose.TeX produce solo PDF, XPS, SVG e immagini raster. Se serve un altro formato, convertire l'output PDF con una libreria che lo supporti.
<br><br>

**D: Come si converte un file LaTeX in PDF in C#?**

**R:** Creare `TeXOptions` per il formato ObjectLaTeX, impostare la directory di output e `PdfSaveOptions` ed eseguire un `TeXJob` con un `PdfDevice`:

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

Il risultato viene scritto nella directory di lavoro di output con il nome del job. Vedere [LaTeX a PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/).
<br><br>

**D: Come si sceglie il formato di output?**

**R:** Impostare `TeXOptions.SaveOptions` e passare a `TeXJob` il dispositivo corrispondente:

| Formato | Opzioni di salvataggio | Dispositivo |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG, JPEG, BMP, TIFF | `PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions` | `ImageDevice` |

Vedere [LaTeX a XPS](/tex/{{lang.url-fragment}}net/latex-to-xps/) e [LaTeX all'immagine](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**D: È possibile ottenere il risultato in memoria anziché in un file?**

**R:** Sì. `PdfDevice` e `XpsDevice` hanno costruttori che accettano uno `Stream` in cui viene scritto il documento. `ImageDevice` conserva le pagine sottoposte a rendering nella proprietà `Result` come array di array di byte, uno per pagina. Per leggere l'input principale da un flusso, passare il flusso al costruttore di `TeXJob`. Vedere [LaTeX a PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) e [Altri modi per fornire il principale file di input TeX](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/).
<br><br>

**D: Come si controllano la risoluzione e la qualità delle immagini?**

**R:** Usare le proprietà delle opzioni di salvataggio delle immagini:

- `Resolution` — risoluzione dell'immagine in DPI.
- `SmoothingMode` e `InterpolationMode` — qualità del rendering.
- `TiffSaveOptions.Compression` e `TiffSaveOptions.Multipage` — compressione TIFF e salvataggio di tutte le pagine in un unico file (il TIFF multipagina non è ancora supportato dal pacchetto `Aspose.TeX.Drawing`).

Ad esempio, `new PngSaveOptions { Resolution = 300 }` produce immagini PNG a 300 DPI. Vedere [LaTeX all'immagine](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**D: Come si verifica se la conversione è riuscita?**

**R:** `TeXJob.Run()` restituisce un valore `TeXJobResult`: `Spotless`, `WarningIssued`, `ErrorMessageIssued` o `FatalErrorStop`. I dettagli vengono scritti nel file di trascrizione (`.log`) nella directory di output e nel terminale di output. Vedere [L'interfaccia di output di Aspose.TeX](/tex/{{lang.url-fragment}}net/aspose-tex-output/).
<br><br>

**D: Serve un'installazione di LaTeX (ad esempio MiKTeX) sul server?**

**R:** No. Aspose.TeX è una libreria .NET autonoma con un proprio motore TeX, un proprio formato LaTeX e propri font. Non richiede alcuna distribuzione TeX esterna.
<br><br>

**D: Quali pacchetti LaTeX si possono usare?**

**R:** Aspose.TeX include un insieme di pacchetti LaTeX incorporati; vedere [Pacchetti in LaTeX incorporati](/tex/{{lang.url-fragment}}net/embedded-packages/). Per usare altri pacchetti, inserire i loro file in una cartella o in un archivio ZIP e specificarlo come `TeXOptions.RequiredInputDirectory`; vedere [Pacchetti di LaTeX esterni](/tex/{{lang.url-fragment}}net/external-latex-packages/).
<br><br>

**D: È possibile eseguire il rendering di una singola formula o di un frammento LaTeX anziché di un intero documento?**

**R:** Sì. Usare `PngMathRenderer` o `SvgMathRenderer` per le formule matematiche e `PngFigureRenderer` o `SvgFigureRenderer` per frammenti LaTeX arbitrari. Restituiscono le dimensioni dell'immagine ottenuta. Vedere [Rendering di formule matematiche LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) e [Rendering di figure LaTeX](/tex/{{lang.url-fragment}}net/latex-figure-rendering/).
<br><br>

**D: Quali sono i requisiti di runtime?**

**R:**

- Pacchetto `Aspose.TeX`: Windows (x64/x86); .NET Framework 4.0 o successivo, .NET Standard 2.0, .NET 6 o successivo.
- Pacchetto `Aspose.TeX.Drawing`: Windows, Linux e macOS (x64/Arm64); .NET Framework 4.7.2 o successivo, .NET 7 o successivo.
- Non sono necessarie librerie native aggiuntive. Su Linux, l'output in XPS e SVG richiede ICU. Vedere [Requisiti di sistema](/tex/{{lang.url-fragment}}net/system-requirements/) e [Linux, macOS e Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).
<br><br>

**D: Quali sono le limitazioni della versione di valutazione?**

**R:** Senza licenza, Aspose.TeX funziona in modalità di valutazione: produce al massimo quattro pagine di un documento e le pagine riportano una filigrana di valutazione. La versione di valutazione è lo stesso pacchetto; per valutarlo senza limitazioni, richiedere una [licenza temporanea di 30 giorni](https://purchase.aspose.com/temporary-license/). Vedere [Licenze](/tex/{{lang.url-fragment}}net/licensing/).
<br><br>

**D: Come si applica una licenza nel codice?**

**R:** Applicare la licenza una sola volta, prima della prima conversione:

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

È anche possibile caricare la licenza da un flusso o usare una licenza a consumo (metered). Vedere [Licenze](/tex/{{lang.url-fragment}}net/licensing/). Per i prezzi, consultare la [pagina dei prezzi di Aspose.TeX](https://purchase.aspose.com/pricing/tex/).
<br><br>

**D: Dove si trovano documentazione dell'API, esempi e supporto?**

**R:**

- [Guida per sviluppatori](https://docs.aspose.com/tex/net/)
- [Riferimento API](https://reference.aspose.com/tex/net/)
- [Forum della community](https://forum.aspose.com/c/tex/)
<br><br>
