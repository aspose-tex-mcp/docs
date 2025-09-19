---
translation: true
template: /templates/_template-java.md
title: Grafica incorporata in LaTeX | Java
linktitle: Grafica incorporata in LaTeX
weight: 18
url: /java/latex-graphics-embedding/
keywords: Includegraphics Latex, LaTeX incorporato grafico Base64, LaTeX base64 grafica codificata, write18, shell-escape, comando shell latex
description: In questo articolo, esplorerai come iniettare immagini codificate da Base64 nel codice sorgente in LaTeX e imparerai la funzione \ write18 che lo rende possibile.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Un modo alternativo per includere immagini

Alcuni sistemi TEX/LaTex consentono l'inclusione di immagini che non sono archiviate esternamente rispetto al file in LaTeX stesso; Invece, queste immagini sono incorporate direttamente all'interno del file LaTeX. Tuttavia, poiché i file TEX/Latex sono un testo semplice e non possono contenere dati binari, abbiamo bisogno di un metodo per rappresentare i dati binari in un formato di testo. Ciò significa che i dati binari devono essere codificati in una rappresentazione testuale. La sfida è che un motore TEX non può interpretare direttamente queste immagini codificate. Alla fine, le immagini sono incluse utilizzando il noto comando `\includegraphics` 'dal pacchetto `graphicx`, ma questo comando è limitato alla gestione di file di immagini esterni. Pertanto, un file di immagine esterno (insieme a un file intermedio aggiuntivo) deve ancora essere creato al di fuori del file LaTeX, ma ciò avverrà solo durante la composizione. Il vantaggio è che devi solo distribuire il file LaTeX stesso, piuttosto che una serie di file.

Va bene, supponiamo che abbiamo in qualche modo incorporato un'immagine codificata nel file LaTeX. Come decodifichiamo questa immagine? Sfortunatamente, non possiamo decodificarlo direttamente leggendolo dal file LaTeX e scrivendolo in un file di immagine esterno. Invece, la stringa di testo che rappresenta l'immagine codificata deve prima essere scritta su un file di testo esterno, che può quindi essere decodificato per generare il file di immagine.

A questo punto, possiamo delineare i seguenti passaggi per ottenere il risultato desiderato:

1. Codificare l'immagine.
2. Inserire la stringa di testo che rappresenta i dati dell'immagine nel file latex.
3. Scrivi la stringa di testo che rappresenta i dati dell'immagine in un file esterno.
4. Decodifica il file esterno creato nel passaggio 3.
5. Includi l'immagine decodificata.

I primi due passaggi vengono eseguiti dall'autore del file LaTeX. Il motore Tex gestirà i passaggi rimanenti, purché sia ​​adeguatamente istruito, ovviamente.

Passiamo al **Passaggio 1**. Come possiamo codificare la nostra immagine per ottenere una stringa di caratteri? Uno dei metodi per farlo (e probabilmente il più popolare) è **Base64**.

## Codifica dati binari utilizzando Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) è un gruppo di schemi di codifica binaria-text che trasforma i dati binari in una sequenza di caratteri stampabili, usando un set di 64 caratteri unici. In particolare, i dati binari di origine vengono elaborati in gruppi di 6 bit, con ciascun gruppo mappato a uno dei 64 caratteri unici. Come tutti gli schemi di codifica binaria-text, Base64 ha lo scopo di facilitare la trasmissione di dati memorizzati in formati binari su canali che supportano prevalentemente il contenuto di testo.

Questa breve spiegazione mostra che **Base64** è esattamente ciò di cui abbiamo bisogno. Per codificare un file di immagine su **Base64**, è possibile utilizzare un'utilità della riga di comando (se disponibile sul sistema operativo), caratteristiche standard o di terze parti di quasi tutti i linguaggi di programmazione o strumenti online come [Base64.guru](https://base64.guru/converter/encode/file) o simili.

## Incorporare l'immagine codificata nel file LaTeX

La stringa di caratteri generati dal processo di codifica deve essere inserita nell'ambiente standard "FileContents" all'interno del preambolo di un file LaTeX, come segue:

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Ecco qui! **Passaggio 2** è completo. Abbiamo incorporato con successo l'immagine all'interno del file LaTex! Ma cosa succederà quando eseguirà la composizione di questo file con LaTeX? "
Un processore in LaTeX scriverà la stringa di caratteri dall'ambiente a un file esterno chiamato `campione-immagine.64`. A causa dell'opzione `Overwrite`, il file verrà sovrascritto se esiste già (ad esempio, se è stato creato durante una esecuzione precedente). Ecco come viene realizzato anche il passaggio 3 **!

## Decodifica una stringa di base64

**Passaggio 4** del nostro piano è dove entrano in gioco le differenze nelle implementazioni di Tex. La decodifica di una stringa di caratteri Base64 viene eseguita mediante una cosa più comune nota come funzione `\write18`.

### `\write18`

Nei motori Classic Tex, `\write <number> (<token list>)` è la primitiva usata per scrivere un *elenco di token *. Se usato, questo primitivo è seguito da un numero intero. Se l'intero è negativo, i token vengono scritti nel file Transcript (log). Se l'intero è maggiore di `15`, i token vengono inviati al terminale. Se l'intero rientra nell'intervallo di `0..15`, i token sono scritti in un file il cui nome è specificato da un precedente verificarsi della primitiva`\Openout`. `\Open <Integer a 4 bit> = <nome file>` primitivo associa un nome file con un numero.

Le nuove implementazioni Tex, come PDF Tex, consentono l'uso di `\write18`. In questo caso, interpretano l'elenco `<token>` come riga di comando da eseguire nella shell del sistema operativo. Poiché questa funzione ovviamente rappresenta un potenziale rischio per la sicurezza, potresti percepire un pizzico di mistero ogni volta che si fa riferimento nella documentazione relativa a Tex o su Internet. Per questo motivo, gli esecutibili TEX/latex PDF offrono opzioni di comando per controllare ACESS a questa funzione.

In genere, ci sono tre livelli di accessibilità: disabili, abilitati con restrizioni e completamente abilitato.

In **aspose.tex**, esiste un'opzione di lavoro tex chiamata `shellmode`, che può prendere uno dei due possibili valori:`noshellescape` e `shellrestricted`. Il valore `NoshelleScape` indica che la funzione è disabilitata. Quest'ultimo valore significa che qualsiasi comando che richiede l'esecuzione deve essere implementato dall'utente come estensione della classe `eseguibile`. Non entreremo nei dettagli di tali implementazioni qui, ma è importante notare che l'emulazione del comando `Base64` è già implementata in Aspose.TeX ed è inclusa per impostazione predefinita nella proprietà della raccolta` `eseguibili 'dell'istanza di classe` Texoptions'.

### Decodifica dati codificati da base64

Per decodificare il contenuto di un file che dovrebbe contenere dati codificati da base64, normalmente useremo la seguente riga di comando:


```
base64 -d  FILE1 > FILE2
```

dove file1 è il file "codificato" e `> file2` reindirizza l'output nel file`file2`.

Pertanto, dovremmo includere la seguente riga nel corpo del nostro file in LaTeX:


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> Il prefisso `\immediate` è necessario per garantire che l'operazione `\write` venga eseguita immediatamente quando lo scanner TeX incontra questa primitiva. In caso contrario, verrà elaborata durante l'invio della pagina.

Se eseguiamo ora la composizione del file, scopriremo che è stato creato il file di immagine `campione-image.png`. Vai avanti e aprilo in uno spettatore per controllare!

## Compresa l'immagine decodificata

Come abbiamo notato all'inizio dell'articolo, per includere l'immagine decodificata, utilizziamo il noto comando in LaTeX `\includegraphics`:


```tex
\includegraphics[options]{sample-image.png}
```

Quindi, il file completo (quasi) LaTeX potrebbe apparire come segue:


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

E il codice Java che utilizza l'API **aspose.tex** è simile a quello che può essere trovato in altri articoli, ad eccezione di specificare l'opzione della modalità shell:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.java" >}}

E ora **il passaggio 5** è completo. Per esempi davvero completi, esplora il nostro [esempio di esempio](https://github.com/aspose-tex/Aspose.TeX-for-Java).

**Puoi anche controllare la conversione gratuita [app Web](https://products.aspose.app/tex/conversion/latex/) in base a [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**