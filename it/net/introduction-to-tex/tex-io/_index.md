---
translation: true
template: /templates/_template-net.md
title: Input/output in TeX
linktitle: Tex i/o
weight: 12
url: /net/tex-io/
description: Fondamenti di lavoro con Tex come output o formato di input all'interno di API Aspose.Tex. Tex Job si svolge su un file esplicitamente specificato.
lastmod: 2026-10-20
---

{{<section overview>}}

## File tex {#tex-file}

Tecnicamente, qualsiasi file può essere un file tex. Non ha nemmeno bisogno di avere l'estensione *.tex*. Un motore TEX legge il byte di input per byte che cerca di riconoscere i comandi ad esso conosciuti (cioè quelli che sono nel suo stato interno). Segnala semplicemente errori sui comandi non riconosciuti e/o richiede correzioni sul terminale (se è in esecuzione in una modalità [interattiva](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)). Ma se ti aspetti di vedere qualcosa come un documento ben composto, l'input dovrebbe seguire la sintassi di Tex e, idealmente, contenere solo comandi noti al motore.

## Input tex {#tex-input}

Un lavoro Tex funziona su un file TEX esplicitamente specificato. Quindi, includiamo questo file nell'input di un determinato lavoro Tex. Inoltre, Tex ha quattro primitive relative all'input ausiliario:

* `\input <Nome file>` richiede un nome file e inizia a elaborare quel file non appena l'elaborazione del file contenente raggiunge il comando `\input`. Una volta raggiunta la fine del file ausiliario, l'elaborazione ritorna al file contenente il comando `\input`.
* `\openin <4-BIT-Number> = <nome file>` richiede anche un nome file, ma apre solo un file e lo mappa a un numero da 0 a 15.
* `\read <umber> a <sequenza di controllo>` richiede il numero a cui un file viene mappato e legge una riga da esso alla volta in modo che `<Sequenza di controllo>` corrisponda all'elenco dei token letti.
* `\closein <4-BIT-Number>` chiude il file mappato al numero.

I file i cui nomi sono passati ai comandi `\input` e `\openin` sono anche inclusi nell'ingresso di TEX e li chiameremo *file di input ausiliario* o *dipendenze*, mentre il file specificato per il lavoro chiameremo il file *input principale*.

I quattro comandi possono verificarsi nel file di input principale o in un file di input ausiliario. Ma attenzione alle dipendenze circolari.

Quando si esegue in una modalità [interattiva](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), in caso di errore, il motore TEX richiede una correzione sul terminale. A questo punto, potresti voler sostituire il comando errato con uno nuovo. E questo sarà un altro e l'ultimo modo per fornire input a Tex che chiameremo l'input *terminale *.

## TEX Output

Come abbiamo detto [sopra](/tex/{{lang.url-fragment}}net/tex-io/#tex-input), un lavoro Tex funziona su un file esplicitamente specificato. Il file non può contenere dati da compensare. Potrebbero esserci solo sequenze di controllo che non producono caratteri da digitare. Ma normalmente conterrà tali dati, in modo da ottenere un file nel formato di destinazione che dovrebbe contenere il nostro testo di composizione (o qualsiasi altra cosa consentita dal motore e dal formato, se sono estesi per adattarsi a funzionalità extra di un determinato formato target). Il file avrà lo stesso nome del file specificato come input. Chiameremo questo file il file *principale output*. Come abbiamo detto [sopra](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex), per il Tex originale, questo sarà un file in formato DVI. Chiameremo il nome dei file di input e output senza estensione il nome *lavoro *.

Inoltre, Tex ha tre primitive relative all'output ausiliario:

* `\Open <4-BIT-Number> = <nome file>` richiede un nome di file, apre un file e lo mappa a un numero da 0 a 15.
* `\write <number> {elenco token}` richiede il numero a cui un file viene mappato e scrive l'elenco `token` nel file.
* `\Closeout <4-BIT-Number>` chiude il file mappato al numero.
 
I file i cui nomi sono passati ai comandi `\Open` sono anche inclusi nell'output di Tex e li chiameremo *file* output ausiliari *.

Poiché il motore TEX esegue l'input, può produrre alcune informazioni di debug al file* o *trascript*,. Includeremo questo file nell'output Tex.
Contemporaneamente alla scrittura nel file di registro, il motore TEX può fornire informazioni meno dettagliate al terminale. E questo è l'ultimo modo in cui il motore Tex scrive l'output che chiameremo l'output *del terminale *.

## Modalità di interazione tex {#tex-interaction-modes}

Un lavoro Tex può essere eseguito in una delle quattro modalità di interazione in qualsiasi momento. Queste modalità sono cambiate dai seguenti primitivi Tex:

* `\batchmode`. Il motore omette tutte le fermate e omette l'uscita del terminale e quindi non richiede il terminale per ingresso o output.
* `\nonstopmode`. Il motore omette tutte le fermate e quindi richiede il terminale solo per l'uscita.
* `\scrollmode`. Il motore omette l'errore si arresta e richiede il terminale sia per l'ingresso che per l'output.
* `\errorstopmode`. Il motore si ferma ad ogni opportunità di interagire.

Aspose.Tex ci consente di specificare la modalità di interazione come opzione di lavoro Tex quando viene creato il suo oggetto. Questa modalità verrà impostata nello stato interno del motore immediatamente dopo il caricamento del formato TEX (se si suppone che un formato dovrebbe essere caricato) e verrà trasferito in un'altra modalità non appena il motore incontra uno dei quattro comandi. Il valore predefinito di questa opzione preserverà la modalità di interazione definita dal formato Tex. Quando non viene caricato alcun formato, la modalità di interazione è la stessa impostata dal comando `\errorstopmode`.

## Il ruolo dell'astrazione tramite interfacce (`IInputWorkingDirectory` e `IOutputWorkingDirectory`)

I motori TeX tradizionali sono intrinsecamente legati al file system del sistema operativo locale, trattando i file come percorsi assoluti o relativi sul disco. Aspose.TeX supera questo limite ereditato dal passato introducendo un solido strato di astrazione, basato su due interfacce principali: `IInputWorkingDirectory` e `IOutputWorkingDirectory`. Questo disaccoppiamento consente di:

- Elaborare i documenti interamente in memoria, utilizzando uno storage basato su flussi di dati (stream).
- Gestire archivi compressi leggendo direttamente dai flussi ZIP, senza doverli prima estrarre su disco.
- Garantire la sicurezza dei thread (thread safety) in applicazioni server multi-tenant, isolando ogni operazione di composizione tipografica all'interno della propria istanza di directory di lavoro virtuale.

### Perché l'astrazione tramite interfacce è importante per gli sviluppatori

Nelle moderne applicazioni aziendali — come i microservizi in cloud o le code di elaborazione in background — fare affidamento sui percorsi fisici del disco comporta notevoli criticità:

- Più thread che leggono o scrivono nella stessa directory fisica possono entrare in conflitto, sovrascrivendo i file temporanei (come i file `.aux`, `.log` o i file di output) generati dagli altri thread.
- Scrivere su disco risorse intermedie o stringhe dinamiche provenienti da un database, solo per permettere al motore di composizione di leggerle, comporta un calo delle prestazioni.
- Gli ambienti cloud (come i container Docker o le funzioni serverless) presentano spesso file system in sola lettura o limitazioni nell'accesso allo storage.

Astrarre le operazioni di input e output tramite interfacce permette agli sviluppatori di reindirizzare tali operazioni verso flussi in memoria, archivi ZIP, database o file system virtuali personalizzati, senza dover apportare alcuna modifica alla logica fondamentale del motore di composizione.