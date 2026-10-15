---
translation: true
template: /templates/_template-java.md
title: LaTeX a XPS | Java
linktitle: LaTeX a XPS
weight: 12
url: /java/latex-to-xps/
description: Funzionalità di conversione della soluzione API ASPUS.TEX per Java consente di convertire i file in LaTeX nel formato XPS. Impara gli esempi di codice.
lastmod: "2026-04-21"
---

{{<section overview>}}


Un altro formato target è [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un file **XPS** è fisicamente un pacchetto zip che contiene contenuto paginato di un documento, nonché i metadati richiesti per la visualizzazione corretta da parte di specifici telespettatori (come Windows XPS Viewer) e la stampa. Tutti i dati in un pacchetto sono organizzati come file nelle directory. Alcuni di essi contengono risorse come immagini, caratteri e profili ICC. Altri sono file XML in vari schemi specifici. Quest'ultimo include file che contengono i dati del documento stesso. I dati del documento sono un set di file: ogni file contiene dati per una singola pagina del documento. Tali file sono costituiti da un singolo elemento di pagina e un albero di elementi figlio - *tela*, *percorso* e *glicfi*. *Canvas*è un elemento di raggruppamento che può contenere altre*tele*,*percorsi* e *glicfi*. Il suo scopo è il controllo sull'aspetto di tutti gli elementi figlio come gruppo. *Path* Gli elementi vengono utilizzati per definire percorsi grafici vettoriali. E gli elementi *glifi* vengono utilizzati per definire il contenuto di testo. Tutti e tre gli elementi hanno proprietà per definire vari aspetti dell'apparenza.

Esiste la libreria [**Aspose.Page**](https://products.aspose.com/page/) che fornisce un'API per manipolare i documenti XPS, oltre a convertirli in formati di immagini PDF e raster.

## Come convertire il LaTeX in XPS

La conversione in XPS è semplice quanto la [conversione in formati di immagini raster](/tex/{{lang.url-fragment}}java/latex-to-image/), tranne che oltre ai [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), dobbiamo usare un'istanza della classe [XPSDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) .

Impostare `inputFile` sul percorso completo del file LaTeX, ad esempio `hello-world.ltx`, e `outputDirectory` su una cartella di output esistente. Importare le classi di `com.aspose.tex` e `com.aspose.tex.rendering` utilizzate nel frammento. Il metodo chiamante deve gestire o dichiarare le eccezioni. Applicare una licenza come descritto nella [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/) per evitare le limitazioni della versione di valutazione. L'esempio utilizza l'elaborazione non interattiva e chiude le risorse di output. Per il file di input autonomo `hello-world.ltx`, l'output predefinito è `hello-world.xps`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### Un modo alternativo per scrivere il file XPS di output principale

C'è un altro costruttore della classe [XPSDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-), che ci consente di ottenere il file XPS risultante in modo alternativo.

Utilizzare gli stessi valori di `inputFile` e `outputDirectory` indicati sopra. Impostare `xpsFile` su un `java.nio.file.Path`, ad esempio `Paths.get(outputDirectory, "any-name.xps")`. Oltre alle classi Aspose.TeX, importare `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path` e `java.nio.file.Paths`. Il flusso determina la destinazione del file XPS; i file ausiliari vengono comunque scritti in `outputDirectory`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

L'effetto è lo stesso che otteniamo [qui](/tex/{{lang.url-fragment}}java/latex-to-pdf/#un-modo-alternativo-per-scrivere-il-file-pdf-di-output-principale).

**È inoltre possibile controllare la conversione da lattoce a XPS gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-xps) basata in base all'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**