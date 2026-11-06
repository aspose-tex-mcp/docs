---
translation: true
template: /templates/_template-python-net.md
title: LaTeX a XPS | Python tramite .NET
linktitle: LaTeX a XPS
weight: 12
url: /python-net/latex-to-xps/
description: La soluzione API Aspose.TeX per Python fornisce funzionalità di conversione per convertire i file in LaTeX in formato XPS. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

Un altro formato target è [**xps**](https://docs.aspose.com/page/net/what-is-xps-file/). Un file [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) è essenzialmente un pacchetto zip che contiene un contenuto paginato di un documento, insieme ai metadati necessari per la visualizzazione corretta da parte di specifici telespettatori (come Windows XPS Viewer) e la stampa. Il pacchetto è composto da vari file, alcuni dei quali sono binari e contengono risorse come immagini, caratteri e profili ICC. Altri sono file XML in schemi specifici, inclusi file che contengono i dati del documento stessi. I dati del documento sono divisi in più file, con ciascun file che rappresenta una singola pagina del documento. Questi file sono costituiti da un elemento di singola pagina e un albero di elementi figlio, tra cui *tela*, *percorso* e *glicfi*. L'elemento *tela*è un elemento di raggruppamento che può contenere altri *tele*, *percorsi* e *glifi *e controlla l'aspetto di tutti gli elementi figlio come gruppo. *Path* Gli elementi vengono utilizzati per definire i percorsi grafici vettoriali, mentre gli elementi* Glifi* vengono utilizzati per definire il contenuto testuale. Tutti e tre gli elementi hanno proprietà che definiscono vari aspetti dell'apparenza.

Esiste la libreria [**Aspose.Page**](https://products.aspose.com/page/), che offre un'API per manipolare i documenti XPS e consente anche la conversione di questi documenti in formati di immagini PDF e raster.

## Convertire il LaTeX in XPS

Il processo di conversione del LaTeX in XPS è ugualmente semplice, simile alla [conversione in formati di immagini raster](/tex/{{lang.url-fragment}}python-net/latex-to-image/). Tuttavia, richiede l'impostazione di [Save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) su un'istanza della classe [XPSSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/) (per impostazione predefinita o esplicitamente) e cambiando il dispositivo in un'istanza della classe [XPSDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/).

Impostare `ASPOSE_TEX_INPUT_FILE` sul file LaTeX e `ASPOSE_TEX_OUTPUT_DIR` sulla directory di output, oppure modificare i percorsi nell’esempio. I valori predefiniti sono `hello-world.ltx` e `output`. Applicare prima una licenza. I file di input aggiuntivi vengono cercati accanto al documento principale; l’elaborazione non è interattiva. [Licenze](/tex/it/python-net/licensing/)

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### Un modo alternativo per scrivere il file XPS di output principale

È disponibile un costruttore alternativo per la classe * XPSDevice *, che consente di ottenere il file XPS risultante in modo diverso.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

Il flusso binario scrive `any-name.xps` nella directory di output configurata. Non viene creato un altro file XPS con il nome predefinito; i file ausiliari e il registro vengono comunque salvati in `output_working_directory`.

**È anche possibile esplorare la conversione gratuita [app Web per la latex-xps](https://products.aspose.app/tex/conversion/latex-to-xps), che viene sviluppata utilizzando [Aspose.TeX per .NET API](https://products.aspose.com/tex/net/).**