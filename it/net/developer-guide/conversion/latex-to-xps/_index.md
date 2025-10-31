---
translation: true
template: /templates/_template-net.md
title: LaTeX a XPS | .NET
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


929 / 5,000
**Esempio di conversione più semplice**

L'esempio seguente mostra come convertire un file LaTeX in XPS in pochi passaggi:

1. Creare un'istanza di `TexDocument`.
2. Caricare il file sorgente `.tex` utilizzando `TexDocument.Load`.
3. (Facoltativo) Configurare `XpsSaveOptions`, ad esempio le impostazioni di compressione.
4. Salvare il documento in XPS chiamando `document.Save` con un `XpsDevice`.

Questo codice illustra il modo più diretto per produrre un file XPS da LaTeX.

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Un modo alternativo per scrivere il file XPS di output principale

C'è un altro costruttore della classe [XPSDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), che ci consente di ottenere il file XPS risultante in modo alternativo.

**Esempio di conversione alternativo**

Questo frammento di codice illustra l'utilizzo del costruttore `XpsDevice` che accetta un `Stream`. I passaggi sono:

1. Creare un `TexDocument` e caricare il sorgente LaTeX.
2. Creare un `MemoryStream` per contenere l'output XPS. 3. Istanziare `XpsDevice` con il flusso.
4. Salvare il documento sul dispositivo, quindi utilizzare il flusso (ad esempio, inviarlo tramite una rete o memorizzarlo in un database).

Questo approccio è utile quando si necessitano i dati XPS in memoria anziché come file su disco.

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

L'effetto è lo stesso che otteniamo [qui](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**È inoltre possibile controllare la conversione gratuita Latex-to-XPS [app Web](https://products.aspose.app/tex/conversion/latex-to-xps) basata su [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**
