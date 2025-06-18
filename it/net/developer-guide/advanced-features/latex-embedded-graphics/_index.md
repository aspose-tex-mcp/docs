---
translation: true
template: /templates/_template-net.md
title: Grafica incorporata in LaTeX | Includi la grafica nel codice LaTeX
linktitle: Grafica incorporata in LaTeX
weight: 18
url: /net/latex-embedded-graphics/
keywords: Includegraphics Latex, LaTeX incorporato grafico Base64, LaTeX base64 grafica codificata, write18, shell-escape, comando shell latex
description: Questo articolo copre come includere le immagini codificate da Base64 nel codice sorgente in LaTeX, nonché la funzione \ write18 che lo rende possibile.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Un altro modo per includere le immagini

Alcuni sistemi TEX/LaTex consentono di includere immagini che non sono archiviate esternamente rispetto al file in LaTeX stesso, ma piuttosto inclusi direttamente all'interno del file LaTeX. Tuttavia, poiché i file tex/latex sono file di testo semplice e quindi non possono contenere dati binari, abbiamo bisogno di un modo per rappresentare i dati binari in forma di testo. In altre parole, i dati binari devono essere codificati in una rappresentazione di testo. Il problema è che un motore TEX non può interpretare direttamente tali immagini codificate. In effetti, inclusa un'immagine viene realizzata usando il buon vecchio comando `\include` dal pacchetto`Graphicx`. Tuttavia, questo comando può gestire solo file di immagini esterni. Sì, un file di immagine esterno (insieme a un altro file intermedio) verrà comunque creato al di fuori del file Latex. Il punto chiave è che devi solo distribuire il file LaTeX da solo.

Ok, diciamo che in qualche modo abbiamo posizionato un'immagine codificata nel file LaTex. Ma come possiamo decodificare l'immagine? Sfortunatamente, non possiamo decodificare il file leggendolo dal file LaTeX e scrivendolo al file di immagine esterno. La stringa di testo che rappresenta l'immagine codificata deve prima essere scritta su un file di testo esterno, che può quindi essere decodificato per produrre un file di immagine.

Ormai, possiamo delineare i seguenti passaggi per ottenere il risultato desiderato:

1. Codificare l'immagine.
2. Iniettare la stringa di testo che rappresenta i dati dell'immagine nel file latex.
3. Uscita la stringa di testo che rappresenta i dati dell'immagine in un file esterno.
4. Decodifica il file esterno dal passaggio 3.
5. Includi l'immagine decodificata.

I primi due passaggi sono completati dall'autore del file latex. Un motore Tex si occuperà dei passaggi rimanenti, a condizione che sia correttamente istruito, ovviamente.

Cominciamo dall'inizio. Come possiamo codificare la nostra immagine per ottenere una stringa di caratteri? Uno dei metodi per farlo (e probabilmente il più popolare) è **Base64**.

## Codifica dati binari utilizzando Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) è un gruppo di schemi di codifica binaria-te-text che trasformano i dati binari in una sequenza di caratteri stampabili, limitato a un set di 64 caratteri unici. Più specificamente, i dati binari di origine vengono presi 6 bit alla volta, quindi questo gruppo di 6 bit viene mappato su uno dei 64 caratteri unici. Come per tutti gli schemi di codifica binaria-text, **Base64** è progettato per trasportare dati memorizzati in formati binari su canali che supportano solo il contenuto di testo in modo affidabile.

Da questa breve spiegazione possiamo vedere che **Base64** è ciò di cui abbiamo bisogno. Per codificare un file di immagine su **Base64**, è possibile utilizzare un'utilità della riga di comando (se disponibile sul sistema operativo), funzionalità standard o di terze parti di quasi tutti i linguaggi di programmazione o strumenti online come [Base64.guru](https://base64.guru/converter/encode/file) o simili.

## Posizionando l'immagine codificata nel file LaTeX

La stringa di caratteri che si ottiene a seguito della codifica deve essere inserita nell'ambiente standard di LaTeX "FileContents" nel preambolo di un file in LaTeX come segue:


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Ecco qui. Il passaggio 2 è realizzato. Abbiamo l'immagine all'interno del file LaTeX! Ma cosa succederà quando eseguirà la composizione di questo file con LaTeX?

Un processore in LaTeX scriverà la stringa di caratteri nell'ambiente in un file esterno chiamato `campione-image.64`. A causa dell'uso dell'opzione `overwrite`, il file verrà sovrascritto se esiste già (ad esempio, se è stato prodotto da una corsa precedente). Ed è quello che realizza anche il passaggio 3!
## Decodifica una stringa di base64

Il passaggio 4 del nostro piano è dove entrano in gioco le differenze nelle implementazioni di Tex. La decodifica di una stringa di caratteri Base64 viene eseguita per mezzo di una cosa più comune nota come funzione `\write18`.

### `\write18`

Nei motori Classic Tex, `\write <number> (<token list>)` è la primitiva che scrive un *elenco di token *. Se usato, questo primitivo è seguito da un numero intero. Se questo numero è negativo, i token vengono scritti nel file Transcript (log). Se il numero è maggiore di `15`, i token vengono scritti nel terminale. Se il numero è nell'intervallo `0..15`, i token sono scritti in un file il cui nome è specificato da un precedente verificarsi della primitiva`\Openout`. `\Open <integer a 4 bit> = <nome file>` primitivo mappa un nome file a un numero.

Le nuove implementazioni Tex (come PDF Tex) consentono l'uso di `\write18`. In questo caso, interpretano l'elenco `<token>` come riga di comando da eseguire nella shell del sistema operativo. Poiché questa funzione è ovviamente un potenziale backdoor, potresti percepire un tocco di mistero ogni volta che viene menzionato nella documentazione legata a Tex o su Internet. Per questo motivo, gli esecutibili PDF Tex/Latex hanno opzioni di comando per gestire l'accessibilità di questa funzione.

In generale, esistono tre livelli di accessibilità: disabili, abilitati con restrizioni e completamente abilitato.

In **aspose.tex**, esiste un'opzione di lavoro tex chiamata `shellmode`, ma ci sono solo due valori adatti:` noshellescape` e `shellrestricted`. Il valore "NoshelleScape" significa che la funzione è disabilitata. Il secondo valore indica che qualsiasi comando che deve essere eseguito deve essere implementato dall'utente come estensione della classe `eseguibile` . Qui, non approfondiremo i dettagli di tali implementazioni, ma menzioneremo che l'emulazione del comando `Base64` è già implementata in Aspose.TeX. Per impostazione predefinita, è possibile trovare la sua istanza prototipo nella proprietà della raccolta `Executables` dell'istanza di classe` Texoptions`.

### Decodifica dati codificati da base64

Per decodificare il contenuto di un file che dovrebbe essere alcuni dati codificati da Base64, normalmente useremo la seguente riga di comando:


```
base64 -d  FILE1 > FILE2
```

dove file1 è il file "codificato" e `> file2` significa che l'output deve essere reindirizzato al file` file2`.

Pertanto, nel corpo del nostro file in LaTeX, dovremmo aggiungere la seguente riga:


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> The `\immediate` prefix is required to ensure that the `\write` operation is performed as soon as the primitive command is encountered by the TeX scanner. Otherwise, it will be processed at the time of page ship-out.

Se eseguiamo ora la composizione del file, vedremo che viene creato il file di immagine `Sample-Image.png`. Dai, aprilo in uno spettatore per controllare!

## Compresa l'immagine decodificata

Come abbiamo detto all'inizio dell'articolo, per includere l'immagine decodificata, utilizziamo il noto comando in LaTeX `\includegraphics`:


```tex
\includegraphics[options]{sample-image.png}
```

Quindi, il file completo (quasi) in LaTeX potrebbe sembrare come segue:


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \write18{base64 -d  sample-image.64 > sample-image.png}
  \includegraphics[options]{sample-image.png}
\end{document}
```

E il codice C# usando l'API **aspose.tex** è simile a quello in altri articoli, ad eccezione della specifica dell'opzione `shellmode`:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.cs" >}}

E ora abbiamo finito con il **passaggio 5**. Per esempi davvero completi, esplora il nostro [Progetto Esempio](https://github.com/aspose-tex/Aspose.TeX-for-.NET).

**Puoi anche controllare la conversione gratuita [app Web](https://products.aspose.app/tex/conversion/latex/) in base a [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**