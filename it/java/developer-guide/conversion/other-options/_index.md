---
translation: true
template: /templates/_template-java.md
title: Altre opzioni di gestione Tex | Java
linktitle: Altre opzioni
weight: 17
url: /java/other-options/
description: Funzionalità di conversione della soluzione API ASUP.TEX per Java consente di impostare la modalità di interazione iniziale in cui inizia il motore. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}


Ogni esempio crea `TeXOptions` per LaTeX e configura un’opzione. Passare queste opzioni a un `TeXJob`, fornire input LaTeX appropriato e impostare una directory di lavoro di output prima dell’esecuzione. Importare `com.aspose.tex.TeXOptions`, `TeXConfig` e le classi utilizzate nell’esempio scelto: `Interaction`, `com.aspose.tex.rendering.XpsSaveOptions` o `PdfSaveOptions`, e `java.util.Calendar`/`GregorianCalendar` per l’esempio della data. Gestire o dichiarare le eccezioni nel metodo chiamante. Gli esempi di rasterizzazione e sottoinsiemi di caratteri utilizzano `PdfSaveOptions`; eseguire il rendering con un `PdfDevice` compatibile. Applicare una licenza secondo la [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/).

## Come impostare la modalità di interazione

Come abbiamo detto [qui](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX per Java** ci consente di impostare la modalità di interazione iniziale in cui si avvia il motore. Ecco come lo facciamo:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-InteractionMode.java" >}}

## Come impostare il nome del lavoro

Quando passiamo il file di input principale come nome di un file, otteniamo file di output con lo stesso nome, sebbene con altre estensioni. Il motore Tex chiama il nome del file di input il * nome del lavoro * e lo utilizza per i file di output, tranne nei casi in cui vengono scritti file ausiliari con altri nomi esplicitamente specificati. Quando passiamo il file di input principale come [stream](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream), il motore Tex utilizza il nome del lavoro predefinito, che è *texput*.
In entrambi i casi, possiamo sovrascrivere il nome del lavoro assegnando l'opzione di conversione appropriata.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-JobName.java" >}}

## Come "fermare il tempo"

LaTex ha una funzione per generare automaticamente un titolo da alcune definizioni nel preambolo. Questo titolo normalmente contiene la data corrente. Potremmo voler congelare la data in un valore desiderato. Ecco come può essere fatto:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-DateTime.java" >}}

## Come ignorare i pacchetti mancanti

Un file LaTeX può fare riferimento a pacchetti non disponibili nella libreria Aspose.TeX per Java. Il motore normalmente si arresta con un errore quando tenta di caricare un pacchetto di questo tipo. Usare `ignoreMissingPackages(true)` per ignorare i pacchetti non disponibili. Questo non fornisce i comandi che tali pacchetti definirebbero; l’input non deve dipendere da essi.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-IgnoreMissingPackages.java" >}}

## Come evitare di costruire legature

Normalmente, il motore TEX crea ligati per determinate coppie di caratteri se il carattere fornisce i dati necessari per farlo. Possiamo istruire il motore a saltare l'edificio della legatura con il seguente codice:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-NoLigatures.java" >}}

## Come ripetere il lavoro

Come abbiamo detto [sopra](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) per quanto riguarda etichette e riferimenti, ci sono casi in cui potremmo voler svolgere lo stesso lavoro due volte. Ecco come può essere fatto:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-Repeat.java" >}}

## Come trasformare le formule matematiche in immagini raster

A volte potremmo aver bisogno di formule di matematica come immagini raster piuttosto che digitate nei caratteri. La seguente opzione può servire a questo scopo:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeFormulas.java" >}}

## Come trasformare la grafica in immagini raster

Il motore ObjectTex ci consente di includere i file grafici in formati raster (PNG e JPG), nonché PS (EPS) e XPS (OXPS). Gli ultimi due formati di solito contengono elementi e testi vettoriali. Per averli rasterosi e inclusi come immagini solide, possiamo usare la seguente opzione:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeIncludedGraphics.java" >}}

## Come sottolineare caratteri

I sottoinsiemi di caratteri limitano i font incorporati ai glifi utilizzati nel documento. L’effetto sulle dimensioni dell’output dipende dal font e da come il dispositivo di output lo incorpora. Assegnare le opzioni di salvataggio prima di abilitare `subsetFonts(true)`, come mostrato di seguito:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-SubsetFonts.java" >}}