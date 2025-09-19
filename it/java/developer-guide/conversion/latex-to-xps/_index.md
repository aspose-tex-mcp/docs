---
translation: true
template: /templates/_template-java.md
title: LaTeX a XPS | Java
linktitle: LaTeX a XPS
weight: 12
url: /java/latex-to-xps/
description: Funzionalità di conversione della soluzione API ASPUS.TEX per Java consente di convertire i file in LaTeX nel formato XPS. Impara gli esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}


Un altro formato target è [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un file **XPS** è fisicamente un pacchetto zip che contiene contenuto paginato di un documento, nonché i metadati richiesti per la visualizzazione corretta da parte di specifici telespettatori (come Windows XPS Viewer) e la stampa. Tutti i dati in un pacchetto sono organizzati come file nelle directory. Alcuni di essi contengono risorse come immagini, caratteri e profili ICC. Altri sono file XML in vari schemi specifici. Quest'ultimo include file che contengono i dati del documento stesso. I dati del documento sono un set di file: ogni file contiene dati per una singola pagina del documento. Tali file sono costituiti da un singolo elemento di pagina e un albero di elementi figlio - *tela*, *percorso* e *glicfi*. *Canvas*è un elemento di raggruppamento che può contenere altre*tele*,*percorsi* e *glicfi*. Il suo scopo è il controllo sull'aspetto di tutti gli elementi figlio come gruppo. *Path* Gli elementi vengono utilizzati per definire percorsi grafici vettoriali. E gli elementi *glifi* vengono utilizzati per definire il contenuto di testo. Tutti e tre gli elementi hanno proprietà per definire vari aspetti dell'apparenza.

Esiste la libreria [**Aspose.Page**](https://products.aspose.com/page/) che fornisce un'API per manipolare i documenti XPS, oltre a convertirli in formati di immagini PDF e raster.

## Come convertire il LaTeX in XPS

La conversione in XPS è semplice quanto la [conversione in formati di immagini raster](/tex/{{lang.url-fragment}}java/latex-to-image/), tranne che oltre ai [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--), dobbiamo usare un'istanza della classe [XPSDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice).

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.java" >}}

### Un modo alternativo per scrivere il file XPS di output principale

C'è un altro costruttore della classe [XPSDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice#XpsDevice-java.io.OutputStream-), che ci consente di ottenere il file XPS risultante in modo alternativo.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.java" >}}

L'effetto è lo stesso che otteniamo [qui](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**È inoltre possibile controllare la conversione da lattoce a XPS gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-xps) basata in base all'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**