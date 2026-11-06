---
translation: true
template: /templates/_template-python-net.md
title: Altre opzioni di gestione Tex | Python tramite .NET
linktitle: Altre opzioni
weight: 17
url: /python-net/other-options/
description: Aspose.TeX Soluzione API per Python include funzionalità di conversione che consente di impostare la modalità di interazione iniziale in cui si avvia il motore.
lastmod: "2025-06-13"
---

{{<section overview>}}

Gli esempi generano file XPS. Applicare prima una [licenza](/tex/{{lang.url-fragment}}python-net/licensing/) e impostare `ASPOSE_TEX_OUTPUT_DIR` sulla cartella di output (predefinita: `output`). Usare una cartella distinta per ogni esempio per conservare tutti i risultati.

## Impostazione della modalità di interazione

Come accennato [in Tex Interaction Parapraph](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX per Python** fornisce la capacità di impostare la modalità di interazione iniziale in cui si avvia il motore. Ecco un esempio di come può essere fatto:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-InteractionMode.py" >}}

## Impostazione del nome del lavoro

Quando il file di input principale viene fornito come nome di file, i file di output risultanti avranno lo stesso nome ma con estensioni diverse. Il motore TEX si riferisce al nome del file di input come * nome del lavoro * e lo utilizza per i file di output. L'eccezione sono file ausiliari con nomi di file esplicitamente specificati. Tuttavia, quando il file di input principale viene passato come [stream](/tex/{{lang.url-fragment}}python-net/other-ways-of-main-input/#supplying-the-main-input-file-as-a-stream), il motore TEX utilizza il nome del lavoro predefinito, che è *texput*. In entrambi gli scenari, è possibile annullare il nome del lavoro assegnando l'opzione di conversione appropriata.

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-JobName.py" >}}

## "Tempo di fermo"

Per generare automaticamente un titolo da determinate definizioni nel preambolo, il LaTeX offre una funzione che in genere include la data corrente. Tuttavia, potrebbero esserci casi in cui vogliamo fissare la data su un valore specifico. Ecco un metodo per raggiungere questo:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-DateTime.py" >}}

## Ignorando i pacchetti mancanti

Se abbiamo un file LaTeX che include riferimenti a pacchetti che non sono supportati dalla libreria **aspy.tex per la libreria Python**, il motore TEX incontrerà un errore e si fermerà quando si tenta di caricare questi pacchetti. Per evitare questo, possiamo utilizzare la seguente opzione:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.py" >}}

## Come evitare di costruire legature

Per impostazione predefinita, il motore TEX costruisce ligature per coppie di caratteri specifiche se il carattere contiene i dati necessari. Tuttavia, possiamo istruire il motore a bypassare la costruzione della legatura usando il seguente codice:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-NoLigatures.py" >}}

## Ripetendo il lavoro

Come accennato [nel paragrafo del file di input in LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-input-file), etichette e riferimenti, ci sono situazioni in cui potremmo dover eseguire due volte lo stesso lavoro. Ecco un metodo per farlo:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-Repeat.py" >}}

## Trasformare le formule di matematica in immagini raster

Se è necessario convertire le formule di matematica in immagini raster invece di renderle con i caratteri, la seguente opzione può essere utilizzata a questo scopo:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.py" >}}

## Trasformare la grafica in immagini raster

Il motore ObjectTex fornisce la capacità di includere i file grafici in formati raster come PNG e JPG, nonché formati PS (EPS) e XPS (OXPS). Questi ultimi due formati contengono in genere elementi vettoriali e testo. Se vogliamo rasterosi e includerli come immagini solide, possiamo utilizzare la seguente opzione:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.py" >}}

L’esempio grafico legge `Typesetting/triangle.eps` in `ASPOSE_TEX_INPUT_DIR` (predefinita: `input`). Conservare questa sottocartella quando si preparano le risorse.

## Caratteri di sottolineare
Se desideriamo ridurre le dimensioni del file di output, possiamo impiegare il sottoinsieme dei caratteri, il che implica che i caratteri nel documento risultante non includeranno dati per quei glifi che non sono presenti nel documento. Ecco una soluzione per raggiungere questo obiettivo:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-SubsetFonts.py" >}}