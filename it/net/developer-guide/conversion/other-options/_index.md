---
translation: true
template: /templates/_template-net.md
title: Altre opzioni di gestione Tex | .NET
linktitle: Altre opzioni
weight: 17
url: /net/other-options/
description: Funzionalità di conversione della soluzione API ASUP.Tex per .NET consente di impostare la modalità di interazione iniziale in cui inizia il motore. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Come impostare la modalità di interazione

Come abbiamo già detto [qui](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX per .NET** ci consente di impostare la modalità di interazione iniziale in cui si avvia il motore. Ecco come lo facciamo:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InteractionMode.cs" >}}

## Come impostare il nome del lavoro

Quando passiamo il file di input principale come nome di un file, otteniamo file di output con lo stesso nome, sebbene con altre estensioni. Il motore Tex chiama il nome del file di input il * nome del lavoro * e lo utilizza per i file di output, tranne nei casi in cui vengono scritti file ausiliari con altri nomi esplicitamente specificati. Quando passiamo il file di input principale come [stream](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), il motore Tex utilizza il nome del lavoro predefinito, che è *texput*.
In entrambi i casi, possiamo sovrascrivere il nome del lavoro assegnando l'opzione di conversione appropriata.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-JobName.cs" >}}

## Come "fermare il tempo"

LaTex ha una funzione per generare automaticamente un titolo da alcune definizioni nel preambolo. Questo titolo normalmente contiene la data corrente. Potremmo voler congelare la data in un valore desiderato. Ecco come può essere fatto:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-DateTime.cs" >}}

## Come ignorare i pacchetti mancanti

Potremmo voler convertire un file LaTeX che fa riferimento ad alcuni pacchetti che non sono supportati da Aspose.TeX per la libreria .NET. In questo caso, il motore TEX si fermerà con un errore quando si tenta di caricare tale pacchetto. Per evitare questo, possiamo usare la seguente opzione:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.cs" >}}

## Come evitare di costruire legature

Normalmente, il motore TEX crea ligati per determinate coppie di caratteri se il carattere fornisce i dati necessari per farlo. Possiamo istruire il motore a saltare l'edificio della legatura con il seguente codice:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-NoLigatures.cs" >}}

## Come ripetere il lavoro

Come abbiamo detto [sopra](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) per quanto riguarda etichette e riferimenti, ci sono casi in cui vorremmo eseguire lo stesso lavoro due volte. Ecco come può essere fatto:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-Repeat.cs" >}}

## Come trasformare le formule matematiche in immagini raster

A volte potremmo aver bisogno di formule di matematica come immagini raster piuttosto che digitate nei caratteri. La seguente opzione può servire a questo scopo:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.cs" >}}

## Come trasformare la grafica in immagini raster

Il motore ObjectTex ci consente di includere i file grafici in formati raster (PNG e JPG), nonché PS (EPS) e XPS (OXPS). Gli ultimi due formati di solito contengono elementi e testi vettoriali. Per averli rasterosi e inclusi come immagini solide, possiamo usare la seguente opzione:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.cs" >}}

## Come sottolineare caratteri

Nel caso in cui vogliamo ridurre le dimensioni del file di output, possiamo ricorrere al sottoinsieme di caratteri, il che significa che i caratteri nel documento di output conterranno solo dati sui glifi utilizzati nel documento. Ecco come possiamo risolvere questo:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-SubsetFonts.cs" >}}