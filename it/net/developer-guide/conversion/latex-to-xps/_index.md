---
translation: true
template: /templates/_template-net.md
title: LaTeX a XPS | Aspose.TeX per .NET
linktitle: LaTeX a XPS
weight: 12
url: /net/latex-to-xps/
description: Funzionalità di conversione della soluzione API ASUP.TEX per .NET consente di convertire i file in LaTeX in formato XPS. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}


Un altro formato target è [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un file **XPS** è fisicamente un pacchetto zip che contiene contenuto paginato di un documento, insieme ai metadati richiesti per la visualizzazione corretta da specifici telespettatori (come Windows XPS Viewer) e la stampa. Tutti i dati in un pacchetto sono rappresentati dai file. Alcuni di essi sono binari e contengono risorse come immagini, caratteri e profili ICC. Altri sono file XML in vari schemi specifici. Quest'ultimo include file che contengono i dati del documento stesso. I dati del documento sono costituiti da un set di file: ogni file contiene dati per una singola pagina del documento. Tali file sono costituiti da un singolo elemento di pagina e un albero di elementi figlio - *tela*, *percorso* e *glicfi*. *Canvas*è un elemento di raggruppamento che può contenere altre*tele*,*percorsi* e *glicfi*. Serve a controllare l'aspetto di tutti gli elementi figlio come gruppo. *Path* Gli elementi vengono utilizzati per definire percorsi grafici vettoriali. E gli elementi *glifi* vengono utilizzati per definire il contenuto testuale. Tutti e tre gli elementi hanno proprietà per definire vari aspetti dell'apparenza.

Esiste la libreria [**Aspose.Page**](https://products.aspose.com/page/) che fornisce un'API per manipolare i documenti XPS, oltre a convertirli in formati di immagini PDF e raster.

## Come convertire il LaTeX in XPS

La conversione da LaTeX a XPS è semplice quanto la [conversione in formati di immagini raster](/tex/{{lang.url-fragment}}net/latex-to-image/), tranne per il fatto che i [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) devono essere impostati su un'istanza di classe [XPSSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (per impostazione predefinita o esplicitamente) e il dispositivo deve essere modificato in un'istanza della classe [XPSDEVICE](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.cs" >}}

### Un modo alternativo per scrivere il file XPS di output principale

C'è un altro costruttore della classe [XPSDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), che ci consente di ottenere il file XPS risultante in modo alternativo.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.cs" >}}

L'effetto è lo stesso che otteniamo [qui](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**È inoltre possibile controllare la conversione gratuita Latex-to-XPS [app Web](https://products.aspose.app/tex/conversion/latex-to-xps) basata su [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**