---
translation: true
template: /templates/_template-java.md
linktitle: 4. Caratteri di LaTeX standard
title: Caratteri in LaTeX standard | Aspose.TeX per java
weight: 40
url: /java/latex-standard-fonts/
keywords: caratteri in LaTeX, LaTeX, caratteri standard in LaTeX, codifica del carattere in LaTeX, Tracefnt, nfssfont.tex
description: Questo articolo è una breve introduzione ai caratteri di testo standard distribuiti insieme al LaTeX.
lastmod: "2025-06-13"
---

{{<section overview>}}

Questo articolo contiene una breve introduzione ai caratteri di testo standard distribuiti insieme al LaTeX. Quindi copre il supporto standard di LaTex per le codifiche input e font. L'articolo si conclude con una descrizione di un pacchetto per la traccia di elaborazione dei caratteri del LaTeX e un altro pacchetto per la visualizzazione di grafici a gesso.

## 4.1. Computer romano moderno

Una famiglia di caratteri chiamati *Computer Modern* è stata sviluppata da Donald Knuth insieme a Tex. Fino all'inizio degli anni '90, solo questi caratteri erano per lo più utilizzabili con Tex e, di conseguenza, con LaTeX. Ognuno di questi caratteri contiene solo 128 glifi, quindi non può includere caratteri accentati come singoli glifi. Pertanto, l'uso di questi caratteri significa che i personaggi accentati devono essere prodotti con la primitiva `\accento` di Tex, che, a sua volta, significa che è impossibile l'ifemazione automatica delle parole con personaggi accentati. Sebbene questa restrizione sia accettabile con i documenti inglesi, è un evidente svantaggio per altre lingue.

![Famiglie di caratteri moderne del computer](/tex/images/java/tutorial/latex-font-selection-4-1.png)

Queste carenze erano di grande preoccupazione per gli utenti del Tex in Europa e alla fine hanno portato a una reimplementazione di Tex nel 1989 per supportare personaggi a 8 bit internamente ed esternamente. Nel 1990 è stata sviluppata una codifica standard a 8 bit per caratteri di testo (`t1`). Contiene molti caratteri diacritici e consente la composizione in più di 30 lingue in base all'alfabeto latino. Quindi, le famiglie di caratteri moderne del computer sono state reimplementate e sono stati progettati ulteriori personaggi in modo che i caratteri risultanti siano completamente conformi a questo schema di codifica.

## 4.2. Selezione della codifica input: il pacchetto `inputenc`

Se puoi digitare caratteri accentati tramite singoli tasti o con qualche altro metodo di input (ad esempio, premendo `` `` `` `e poi` a` per ottenere 'a-thrave') e il tuo computer li visualizza correttamente nell'editor ...

![Testo francese correttamente visualizzato nell'editor di testo](/tex/images/java/tutorial/latex-font-selection-4-2.png)

... quindi idealmente useresti un tale testo direttamente con LaTeX invece di dover digitare ``\`a``,` \^e`, ecc.

Con lingue come il francese e il tedesco, quest'ultimo approccio è fattibile. Tuttavia, per lingue come il russo e il greco, è necessario il potenziale di input diretto, poiché quasi ogni personaggio in queste lingue ha un nome di comando come forma di LaTeX interno. Ad esempio, la definizione russa predefinita per `\refTextAfter` contiene il seguente testo (che significa" nella pagina successiva "):

```tex
\cyrn\cyra\ \cyrs\cyrl\cyre\cyrd\cyru\cyryu\cyrshch\cyre\cyrishrt
\ \cyrs\cyrt\cyrr\cyra\cyrn\cyri\cyrc\cyre
```

È improbabile che qualcuno vorrebbe digitare tali cose su base regolare. Tuttavia, ha il vantaggio di essere universalmente portatile, in modo che possa essere interpretato correttamente su qualsiasi installazione in LaTeX. D'altra parte, digitare

!["Nella pagina successiva" in russo](/tex/images/java/tutorial/latex-font-selection-4-3.png)

Su una tastiera appropriata è chiaramente preferibile, se è possibile far comprendere il LaTeX a questo input. Il problema è che ciò che viene archiviato in un file non sono i caratteri che vediamo nella sequenza sopra, ma piuttosto gli ottetti che rappresentano i personaggi. In circostanze diverse (usando codifiche diverse), gli stessi ottetti potrebbero rappresentare caratteri diversi.

Finché tutto accade su un singolo computer e tutti i programmi interpretano gli ottetti nei file allo stesso modo, di solito tutto va bene. In tal caso, ha senso attivare un meccanismo di traduzione automatico integrato in alcune recenti implementazioni di Tex. Ma quando un file prodotto in tale ambiente viene inviato a un altro computer, è probabile che l'elaborazione fallisca o, peggio ancora, possa sembrare avere successo, ma in realtà produrrà risultati errati visualizzando caratteri errati.
Il pacchetto `inputenc` è stato creato per far fronte a questo problema. Il suo scopo principale è informare il LaTeX della codifica utilizzata nel documento o in una parte del documento. Questo viene fatto caricando il pacchetto con il nome di codifica come opzione. Per esempio:

```tex
\usepackage[cp1252]{inputenc} % Windows 1252 (Western Europe) code page
```

Da quel momento in poi, il LaTeX sa come interpretare gli ottetti nel resto del documento su qualsiasi installazione, indipendentemente dalla codifica utilizzata per altri scopi su quel computer.

Un esempio tipico è mostrato di seguito. È un breve testo scritto nella codifica `Koi8-R`, che è popolare in Russia. Il codice sorgente mostra come appare il testo su un computer usando una codifica latina 1 (ad esempio, in Germania). L'output dimostra che il LaTeX era ancora in grado di interpretare correttamente il testo perché è stato detto quale codifica input veniva utilizzato.

![Testo russo nella codifica tedesca: il codice sorgente](/tex/images/java/tutorial/latex-font-selection-4-4.png)

![Testo russo nella codifica tedesca: l'output](/tex/images/java/tutorial/latex-font-selection-4-5.png)

L'elenco delle codifiche attualmente supportate da `inputenc` è fornito di seguito. L'interfaccia è ben documentata e il supporto per nuovi codifica può essere facilmente aggiunto. Pertanto, vale la pena consultare la documentazione del pacchetto `inputenc` se la codifica utilizzata dal computer non è elencata qui. È inoltre possibile cercare su Internet la codifica di file per `inputenc` creati da altri autori. Ad esempio, le codifiche relative alle lingue cirilliche sono distribuite insieme ad altri pacchetti di supporto per i linguaggi cirillici.

Lo standard ISO-8859 definisce una serie di importanti codifiche singoli. Le codifiche relative all'alfabeto latino sono supportate da `inputenc`. Per il sistema operativo di Windows, Microsoft è stata definita una serie di codifiche a singolo byte. Inoltre, sono disponibili alcune codifiche definite da altri fornitori di computer.

* `Latin1` Questa è la codifica ISO-8859-1 (a.k.a. latino 1). Può rappresentare la maggior parte delle lingue dell'Europa occidentale, tra cui albanese, catalano, danese, olandese, inglese, faroese, finlandese, francese, galiziano, tedesco, islandese, irlandese, italiano, norvegese, portoghese, spagnolo e svedese.
* `Latin2` La codifica ISO Latin 2 (ISO-8859-2) supporta le lingue slave dell'Europa centrale che usano l'alfabeto latino. Può essere usato per le seguenti lingue: croato, ceco, tedesco, ungherese, polacco, rumeno, slovacco e sloveno.
* `Latin3` Questo set di personaggi (ISO-8859-3) viene utilizzato per esperanto, galiziano, maltese e turco.
* `Latin4` La codifica ISO Latin 4 (ISO-8859-4) può rappresentare lingue come estone, lettone e lituano.
* `Latin5` La codifica ISO Latin 5 (ISO 8859-9) è strettamente correlata al latino 1 e sostituisce le lettere islandesi usate raramente dal latino 1 con lettere turche.
* `Latin9` Latino 9 (o ISO-8859-15) è un'altra piccola variazione sul latino 1 che aggiunge il segno della valuta euro e alcuni altri personaggi, come la ligatura`\ae`, che mancavano in francese e finlandese. Sta diventando sempre più popolare in sostituzione del latino 1.
* Pagina del codice `CP437` IBM 437 (latino MS-DOS ma contenente molti caratteri grafici per disegnare caselle).
* Pagina di codice `CP850` IBM 850 (MS-DOS multilingue, simile a latino1).
* Pagina di codice `CP852` IBM 852 (MS-DOS multilingue, simile a latin2).
* Pagina del codice `CP858` IBM 858 (IBM 850 con il simbolo Euro aggiunto).
* Pagina del codice `CP865` IBM 865 (MS-DOS Norvegia).
* Pagina di codice `CP1250` Windows 1250 (Europa centrale e orientale).
* Pagina di codice `CP1252` Windows 1252 (Europa occidentale).
* Pagina di codice `CP1257` Windows 1257 (Baltico).
* Codifica `Ansinew` Windows 3.1 ANSI; un sinonimo di CP1252.
* Decmulti` Dec Multinational Caratteri Set codifica.
* Codifica `Applemac` Macintosh (standard).
* Pagina del codice dell'Europa centrale `MacCE` Macintosh.
* `Next` Next Computer codifica.
* `UTF8` Supporto di codifica UTF8 di Unicode.
La maggior parte delle installazioni di Tex accetta caratteri a 8 bit per impostazione predefinita. Tuttavia, senza ulteriori aggiustamenti, come quelli eseguiti da `inpuenc`, i risultati possono essere imprevedibili: alcuni personaggi possono scomparire o potresti ottenere qualunque personaggio sia presente nell'attuale carattere nella posizione dell'ottetto a cui si fa riferimento, che può o meno essere il gesso desiderato. Questo comportamento è stato predefinito per molto tempo, quindi non è stato cambiato in latex2e perché alcune persone si affidano a esso. Tuttavia, per garantire che tali errori possano essere catturati, `inputenc` offre l'opzione` ascii`, che rende illegale qualsiasi personaggio al di fuori dell'intervallo 32-126.

```tex
\inputencoding{encoding}
```

Inizialmente, il pacchetto `inputenc` era progettato per specificare la codifica utilizzata per un documento nel suo insieme, da cui l'uso di opzioni nel preambolo. Tuttavia, è possibile modificare la codifica nel mezzo di un documento utilizzando il comando `\inputencoding`. Questo comando prende il nome di una codifica come argomento.

Quando è stato sviluppato `inputenc`, la maggior parte delle installazioni in LaTeX erano su computer che utilizzavano codifiche a singolo byte come quelle discusse in questa sezione. Tuttavia, oggi un altro codifica è popolare poiché i sistemi forniscono supporto per Unicode: UTF8. Questa codifica a lunghezza variabile rappresenta caratteri Unicode in uno o quattro ottetti. Il supporto di codifica è stato aggiunto a `inputenc` tramite l'opzione` utf8`. Tecnicamente, non fornisce un'implementazione UTF8 completa. Vengono mappati solo i caratteri Unicode che hanno una rappresentazione nei caratteri standard in LaTeX (ovvero set di caratteri latini e cirillici): tutti gli altri si tradurranno in un messaggio di errore adatto. Inoltre, gli Unicode che combinano caratteri non sono supportati, sebbene quella particolare omissione non debba essere un problema nella pratica.

```tex
\usepackage[utf8]{inputenc}
\usepackage{textcomp} % for Latin interpretation
-----------------------------------------------
German umlauts in UTF-8: ^^c3^^a4^^c3^^b6^^c3^^bc
\par\inputencoding{latin1}% switch to Latin 1
But interpreted as Latin 1: ^^c3^^a4^^c3^^b6^^c3^^bc
```

![UTF8 supportato dal pacchetto inputc](/tex/images/java/tutorial/latex-font-selection-4-6.png)

In UTF8, i personaggi ASCII rappresentano se stessi e la maggior parte dei caratteri latini sono rappresentati da due byte. Nel codice sorgente dell'esempio, le rappresentazioni a due byte degli Umlaut tedeschi in UTF8 sono mostrate nella notazione esadecimale di Tex, cioè con ogni ottetto preceduto da `^^`. In un editore che non comprende UTF8, ON probabilmente li vedrebbe simili all'output che viene prodotto quando vengono interpretati come caratteri latini 1.

Un pacchetto con supporto UTF8 più completo (incluso il supporto per i personaggi coreani, cinesi e giapponesi), sebbene di conseguenza più complesso nella sua configurazione, è il pacchetto UCS scritto da Dominique Unruh. Puoi provarlo se la soluzione `inputenc 'non copre le tue esigenze.

## 4.3. Selezione delle codifiche dei caratteri con il pacchetto `Fontenc`

Per abilitare una codifica del carattere di testo per l'uso con LaTeX, la codifica deve essere caricata nella classe di preambolo o documento. Più precisamente, devono essere caricate le definizioni per accedere ai glifi nei caratteri con una certa codifica. Il modo canonico per farlo è tramite il pacchetto `Fontenc`, che prende un elenco di codifiche di font separate da virgola come opzione di pacchetto. L'ultimo di queste codifiche viene automaticamente reso la codifica del documento predefinito. Se vengono caricate le codifiche cirilliche, l'elenco dei comandi interessati da `\makeuppercase` e `\makelowercase` viene automaticamente esteso. Per esempio,

```tex
\usepackage[T2A,T1]{fontenc}
```
caricherà tutte le definizioni necessarie per la codifica cirillica `t2a` e ` t1` e impostare quest'ultimo come codifica del documento predefinito.

A differenza del normale comportamento del pacchetto, è possibile caricare questo pacchetto più volte con diverse opzioni per il comando `\usapackage`. Ciò è necessario per consentire a una classe di documenti di caricare una determinata serie di codifica e consentire all'utente di caricare ancora più codifica nel preambolo. Il caricamento delle codifiche più di una volta viene eseguita senza effetti collaterali oltre a modificare potenzialmente la codifica del carattere predefinita del documento.

Se nel documento vengono utilizzati pacchetti di supporto linguistico (ad esempio, quelli che vengono con il sistema * Babele *), è spesso il caso che le codifica di carattere necessarie siano già caricate dal pacchetto di supporto.

## 4.4. Come tracciare la selezione dei caratteri con il pacchetto `Tracefnt`

Per rilevare i problemi nel sistema di selezione dei caratteri, è possibile utilizzare il pacchetto `Tracefnt`. Supporta diverse opzioni che consentono di personalizzare la quantità di informazioni visualizzate da NFSS sullo schermo e nel file di trascrizione.

* `ErrorShow` Questa opzione sopprime tutti gli avvertimenti e i messaggi di informazione sul terminale; Saranno scritti solo nel file di trascrizione. Verranno mostrati solo errori reali. Dovresti studiare attentamente il file di trascrizione prima di stampare un'importante pubblicazione perché avvertimenti sulle sostituzioni dei caratteri e così via può significare che il risultato finale sarà errato.
* `Warningshow` Quando questa opzione è specificata, nel terminale vengono mostrati avvertimenti ed errori. Questa impostazione ti fornisce informazioni dettagliate come il latex2e senza il pacchetto `tracefnt` caricato.
* `Infoshow` Questa opzione è il valore predefinito quando si carica il pacchetto` Tracefnt`. Informazioni aggiuntive, che normalmente vengono scritte solo nel file di trascrizione, ora vengono visualizzate anche sul tuo terminale.
* `Debugshow` Questa opzione mostra inoltre informazioni sulle modifiche al carattere di testo e sul ripristino di tali caratteri alla fine di un gruppo di tute o alla fine di un ambiente. Fai attenzione quando si accende questa opzione perché può produrre file di trascrizione molto grandi.
* `Pausa` Questa opzione trasforma tutti gli avvertimenti in errori per aiutare il rilevamento di problemi in pubblicazioni importanti.
* `Caricamento` Questa opzione mostra il caricamento di caratteri esterni. Tuttavia, se il formato o la classe di documenti utilizzati ha già caricato alcuni caratteri, questi non saranno mostrati da questa opzione.

## 4.5. Come visualizzare tabelle e campioni di carattere con `nfssfont.tex`

Il file chiamato `nfssfont.tex` può essere utilizzato per testare nuovi caratteri, produrre tabelle di carattere che mostrano tutti i caratteri ed eseguire altre operazioni relative ai caratteri. Puoi trovare questo file in qualsiasi distribuzione in LaTeX. Quando si esegue questo file tramite LaTex, ti verrà richiesto il test del nome del carattere. La risposta può essere il nome del carattere esterno senza estensione - come `cmr10` (computer moderno romano 10pt) - se lo sai o un nome di carattere vuoto. In quest'ultimo caso, ti verrà richiesto una specifica del carattere NFSS: un nome di codifica (impostazione predefinita `t1`), un nome familiare di carattere (impostazione predefinita` cmr`), una serie di caratteri (predefinita `m`), una forma del carattere (default` n`) e una dimensione del carattere (inadempienza `10pt`). Il programma carica quindi il file esterno corrispondente a tale classificazione.

Successivamente, ti verrà chiesto di inserire un comando. Il più importante è probabilmente `\table`, che produce un grafico dei caratteri come quello qui sotto. Il comando `\text` è anche interessante in quanto produce un campione di testo più lungo. Per passare a un nuovo carattere di prova, digitare `\init`; Per finire il test, digitare `\ciao` o`\stop`; E per conoscere tutti gli altri test disponibili, digitare `\help`.

```
**********************************************
* NFSS font test program version <v2.2b>
*
* Follow the instructions
**********************************************

Input external font name, e.g., cmr10
(or <enter> for NFSS classification of font):

\currfontname=cmr10
Now type a test command (\help for help):)
*\table

*\newpage
*\init
Input external font name, e.g., cmr10
(or <enter> for NFSS classification of font):

\currfontname=
*** NFSS classification ***

Font encoding [T1]:

\encoding=OT1
(ot1enc.def)
Font family [cmr]:

\family=cmdh
Font series [m]:

\series=m
Font shape [n]:

\shape=n
Font size [10pt]:

\size=10
(ot1cmdh.fd) Now type a test command (\help for help):
*\text

*\bye

```

![Il grafico dei caratteri per CMR10](/tex/images/java/tutorial/latex-font-selection-4-7.png)

![Il campione di testo per OT1/CMDH/M/N/10](/tex/images/java/tutorial/latex-font-selection-4-8.png)

> Ci sono due punti da tenere a mente. In primo luogo, il programma `nfssfont.tex` emette un comando `\init` implicito, quindi la prima riga di input dovrebbe contenere il nome del font o essere completamente vuota per indicare che segue una classificazione NFSS. In secondo luogo, l'input di `\init` deve apparire su singole righe senza nient'altro (nemmeno un commento), perché la fine della riga indica la fine della risposta a un prompt del tipo `Font encoding[T1]: \encoding=` che si otterrà.