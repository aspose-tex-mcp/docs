---
translation: true
template: /templates/_template-java.md
title: 6. Come impostare nuovi caratteri
linktitle: Come impostare nuovi caratteri
weight: 60
url: /java/latex-fonts-setup/
keywords: Font in LaTeX, LaTeX, sostituzione del carattere in LaTeX, configurazione del carattere in LaTeX
description: Questo articolo copre la creazione di nuovi caratteri da utilizzare con LaTeX e include anche un esempio di definizione dei caratteri.
lastmod: "2025-06-13"
---

{{<section overview>}}

Per impostare nuovi caratteri per l'uso con LaTex, è fondamentalmente necessario riempire le tabelle di selezione dei caratteri interne necessarie per associare successivamente una richiesta di carattere in un documento con il file `.tfm` esterno contenente le informazioni sui caratteri utilizzate dal LaTeX. Pertanto, le tabelle sono responsabili dell'associazione del file esterno `cmdunh10.tfm` con la seguente richiesta:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{m}\fontshape{n}%
\fontsize{10}{12pt}\selectfont
```

Per aggiungere nuovi caratteri, devi invertire il processo. Per ogni nuovo carattere esterno, devi rispondere a cinque domande:

1. Qual è la codifica dei caratteri - cioè quali personaggi sono in quali posizioni?
2. Qual è il suo cognome?
3. Qual è la sua serie (peso e larghezza)?
4. Qual è la sua forma?
5. Qual è la sua taglia?

Le risposte a queste domande forniranno le informazioni necessarie per classificare i caratteri esterni in base alle convenzioni in LaTeX. Nelle prossime sezioni, discuteremo di come inserire nuovi caratteri nelle tabelle NFSS in modo che possano essere utilizzate nel testo principale. Normalmente hai bisogno di queste informazioni se si desidera utilizzare nuovi caratteri, come la creazione di un file di pacchetto corto per accedere a una nuova famiglia di carattere. Nelle sezioni successive, discuteremo di concetti più complicati che sono importanti se si desidera usare, ad esempio, caratteri speciali per la matematica anziché quelli standard.

## 6.1. La convenzione di denominazione per i caratteri esterni

Uno schema di denominazione di font standard di fatto nel mondo di Tex classifica tutti i nomi dei file di carattere utilizzando otto caratteri alfanumerici, in cui il caso non è significativo. Questo limite di otto caratteri garantisce che gli stessi nomi di file possano essere utilizzati su tutte le piattaforme di computer. Il principio dello schema è descritto nella tabella seguente, in cui le parti tra parentesi possono essere omesse se corrispondono a un valore predefinito. Ad esempio, una dimensione del design viene data solo se il carattere non è ridimensionato linearmente.

![La convenzione di denominazione per i caratteri esterni](/tex/images/java/tutorial/latex-font-selection-6-1.png)

Di seguito è riportata la classificazione dei caratteri PostScript "di base" da 35 secondo l'interfaccia del carattere di LaTex. Per ciascun carattere, vengono forniti il ​​nome completo Adobe e il corrispondente nome di file corto (nella classificazione attualmente in discussione). Per `ot1`,` t1` o `ts1`, è necessario aggiungere rispettivamente` 7t`, `8t` o` 8c`, per ottenere il nome completo del file. Ad esempio, `putr8t` per utopia regolare nella codifica` t1`.  Ciò sarà utile in ulteriori discussioni.

![Classificazione dei caratteri PostScript](/tex/images/java/tutorial/latex-font-selection-6-2.png)

La convenzione di denominazione copre i nomi interni di TEX per i caratteri (ovvero quelli usati nelle dichiarazioni `\dichiarafontShape` come descritto nella sezione successiva), nomi per caratteri virtuali e loro componenti (ad esempio, particolari reincodi di caratteri fisici) e i nomi dei caratteri fisici. Nel caso dei caratteri PostScript, i nomi dei caratteri fisici sono spesso diversi da quelli usati internamente da Tex.
In quest'ultimo caso, i nomi dei caratteri interni devono essere mappati su caratteri esterni corrispondenti quando viene visualizzato o stampato il risultato di una corsa in LaTeX. Ad esempio, il driver PostScript `dvips` utilizza i file di mappatura (estensione predefinita` .map`) che contengono linee come

```
putr8r Utopia-Regular "TeXBase1Encoding ReEncodeFont " <8r.enc <putr8a.pfb
```

dicendo che il carattere `putr8r` può essere ottenuto dal carattere esterno` putr8a.pfb` reincellandolo tramite un vettore di codifica speciale (`8r.enc`). Tuttavia, non troverai alcun riferimento a quel `putr8r` nel file` t1put.fd`, che contiene le dichiarazioni `\dichiarafontShape` per la famiglia Utopia nella codifica` T1`. Il motivo è che `putr8t` è un carattere virtuale (costruito con l'aiuto dell'utilità` Fontinst`) che fa riferimento a `putr8r '. Quest'ultimo collegamento può essere trovato solo nelle fonti dei caratteri virtuali.

## 6.2. Come dichiarare nuove famiglie di carattere e gruppi di forma di carattere

Ogni combinazione di famiglia/codifica deve essere introdotta in LaTeX con l'aiuto del comando `\dichiarafontfamily`, che richiede tre argomenti. I primi due sono lo schema di codifica e il cognome. Il terzo è di solito vuoto, ma può contenere opzioni speciali per il caricamento dei caratteri ed è ulteriormente spiegato in questo articolo. Quindi, se vuoi dichiarare una nuova famiglia - diciamo, computer moderno Dunhill con la vecchia codifica Tex - scriveresti

```tex
\DeclareFontFamily{OT1}{cmdh}{}
```

Normalmente, ci sono molti caratteri individuali in una famiglia. Per ridurre il numero di dichiarazioni, è necessario combinare caratteri che differiscono solo per dimensioni e dichiararli come un gruppo invece di annunciare individualmente ciascun membro della famiglia.

Tale gruppo viene inserito nelle tabelle interne del LaTeX con il comando `\dichiarafontShape`, che richiede sei argomenti. I primi quattro argomenti sono lo schema di codifica, il nome della famiglia, il nome della serie e il nome di forma in cui si desidera accedere a questi caratteri. Il quinto argomento è un elenco di dimensioni e nomi dei caratteri esterni, indicato in un formato speciale discusso di seguito. Il sesto argomento è generalmente vuoto e il suo uso è ulteriormente spiegato in questo articolo.

Ad esempio, è possibile inserire una voce da tavolo NFSS per computer moderno dunhill medio in posizione verticale nel vecchio schema di codifica Tex

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> cmdunh10 }{}
```

Supponendo che sia disponibile un solo carattere esterno per la dimensione 10pt. Se hai anche questo carattere disponibile a 12pt (ridimensionato da 10pt), la dichiarazione sarebbe

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> <12>cmdunh10 }{}
```

Se il file esterno è disponibile in tutte le dimensioni possibili, la dichiarazione diventa molto semplice. Questo è il caso dei caratteri di tipo 1 PostScript (schema) o quando il programma del driver è in grado di generare caratteri su richiesta chiamando Metafont.

Ad esempio, i tempi in grassetto romano in grassetto nello schema di codifica `t1` in LaTeX potrebbero essere introdotti come segue

```tex
\DeclareFontShape{T1}{ptm}{b}{n}{ <-> ptm8t }{}
```

Questo esempio dichiara un intervallo di dimensioni con due estremità aperte. Di conseguenza, lo stesso file `ptmb8t.tfm` esterno viene utilizzato per tutte le dimensioni e viene ridimensionato sulla dimensione desiderata. Se hai più di un file `.tfm` per un carattere - ad esempio,` emtt10` per dimensioni di testo e `emtt12` per dimensioni del display (macchina da scrivere europea moderna) - la dichiarazione potrebbe essere

```tex
\DeclareFontShape{T1}{emtt}{m}{n}{<-12> emtt10 <12-> emtt12}{}
```

In questo caso, il file `emtt10.tfm` verrebbe utilizzato per dimensioni inferiori a 12pt e` emtt12.tfm` per tutte le dimensioni più grandi o uguali a 12pt.

Gli esempi sopra dimostrano che il quinto argomento del comando `\dichiarafontShape` è costituito da specifiche di dimensioni circondate da parentesi angolari mescolate a informazioni di caricamento per le singole dimensioni (ad esempio, nomi di caratteri). La parte all'interno delle staffe angolari è chiamata *Informazioni dimensionali* e la parte che segue la staffa angolare di chiusura è chiamata *Font Info*.  Le informazioni sul carattere sono ulteriormente strutturate in una funzione * dimensione * (spesso vuota) e i suoi argomenti. All'interno degli argomenti di `\dichiarafontShape`, gli spazi bianchi vengono ignorati per rendere le voci più leggibili. In circostanze insolite, quando deve essere inserito uno spazio reale, è possibile utilizzare il comando `\Space`.

### Dimensioni semplici e gamme di dimensioni

Le dimensioni di INFOS possono essere divise in *dimensioni semplici* e *intervalli di dimensioni*. Una dimensione semplice è data da un singolo numero (decimale), come `<10>` o `<17.28>` e può avere un valore positivo. Tuttavia, probabilmente non troverai valori inferiori a 4 o più di 120 perché il numero rappresenta una dimensione del carattere misurata in punti. Un intervallo di dimensioni è dato da due dimensioni semplici separate da un trattino, per indicare una gamma di dimensioni dei caratteri che condividono le stesse informazioni sul carattere. Il limite inferiore è incluso nell'intervallo, mentre il limite superiore è escluso. Ad esempio, `<5-10>` sta per dimensioni superiori o uguali a 5pt e meno di 10pt. È possibile omettere il numero su entrambe le dimensioni del trattino in un intervallo di dimensioni: `<-->` sta per tutte le dimensioni possibili, `<-10>` sta per tutte le dimensioni inferiori a 10pt e `<12->` è per tutte le dimensioni maggiori o uguali a 12pt.
Diverse dimensioni semplici hanno spesso le stesse informazioni sul carattere. In tal caso, una comoda stenografia è quella di omettere tutte le ultime informazioni:

```tex
\DeclareFontShape{OT1}{panr}{m}{n}{ <5> <6> <7> <8> <9> <10>
    <10.95> <12> <14.4> <17.28> <20.74> <24.88> pan10 }{}
```

Ciò dichiara il mezzo di carattere di Pandora Roman come disponibile in diverse dimensioni, tutte prodotte ridimensionando le stesse dimensioni del design.

### Funzioni dimensionali

Come accennato in precedenza, le informazioni sul carattere sono ulteriormente strutturate in una funzione di dimensioni e nel suo argomento. Se una `*` appare nella stringa di informazioni sul carattere, tutto a sinistra forma il nome della funzione e tutto a destra è l'argomento. Se non c'è asterisco, come in tutti gli esempi finora, l'intera stringa è considerata l'argomento e il nome della funzione è *vuoto *.

Le funzioni di dimensioni producono le specifiche necessarie per il LaTeX per trovare il carattere esterno e caricarlo alla dimensione desiderata. Questo processo si basa sulle dimensioni richieste dall'utente e sulle informazioni nel comando `\dichiarafontShape`. Le funzioni delle dimensioni sono anche responsabili della notifica all'utente di eventi speciali. Ad esempio, alcune funzioni differiscono solo nel fatto che emettono avvertimenti. Questa capacità consente al manutentore del sistema di impostare il LaTeX nel modo più adatto al sito particolare.

Il nome di una funzione di dimensioni è costituito da zero o più lettere. Alcune delle funzioni di dimensioni possono richiedere due argomenti: uno opzionale e uno obbligatorio. Un parametro opzionale deve essere racchiuso tra parentesi quadrate. Ad esempio, la seguente specifica selezionerebbe, per tutte le dimensioni possibili, la funzione di dimensione `s` con l'argomento opzionale` 0.9` e l'argomento obbligatorio `cmfbi10`:

```tex
<-> s * [0.9] cmfib8
```

Le specifiche dimensioni in `\dichiarafontShape` sono ispezionate nell'ordine in cui vengono dati. Quando una dimensione di informazioni corrisponde alla dimensione richiesta, viene eseguita la funzione dimensione corrispondente. Se questo processo produce un carattere valido, non vengono ispezionate ulteriori voci. Altrimenti, la ricerca continua con la voce successiva. Le funzioni di dimensioni standard sono elencate di seguito.

**La funzione "vuota"** La funzione vuota carica le informazioni sul carattere esattamente alla dimensione richiesta se è una dimensione semplice. Se è presente un intervallo di dimensioni e le dimensioni richieste dall'utente rientrano all'interno di tale intervallo, carica il carattere esattamente alle dimensioni dell'utente.
Ad esempio, se l'utente ha richiesto `14.4`, la specifica

```tex
<-> panr10
```

caricherebbe il file `panr10.tfm` a 14.4pt. Tutti i valori nel file `.tfm` sono ridimensionati di 1,44 perché questo carattere è stato progettato per 10pt.

A volte potresti voler caricare un carattere a una dimensione leggermente diversa da quello richiesto dall'utente. Tale aggiustamento può essere necessario quando i caratteri di una famiglia sembrano essere troppo grandi rispetto ai caratteri di altre famiglie utilizzate nello stesso documento. A tale scopo, la funzione di dimensioni vuote consente a un argomento opzionale di specificare un fattore di scala che viene moltiplicato per la dimensione richiesta per produrre la dimensione effettiva da caricare.

Così, 

```tex
<-> [0.95] phvr8t
```

caricherebbe sempre il file `phvr8t.tfm` (Helvetica nella codifica` T1`) al 95% della dimensione richiesta. Se viene utilizzato l'argomento opzionale, la funzione di dimensioni vuote emetterà un avviso per avvisare all'utente che il carattere non viene caricato alla dimensione prevista.

**La funzione "s"** La funzione `s` fa la stessa della funzione vuota, tranne per il fatto che non verrà generato alcun messaggio sul terminale. I messaggi verranno comunque scritti nel file di trascrizione, in modo da poter scoprire quali caratteri sono stati usati se qualcosa va storto.

**La funzione "Gen"** I nomi dei caratteri esterni sono spesso costruiti aggiungendo la dimensione del carattere a una stringa che rappresenta il carattere tipografico. Ad esempio, `cmtt8`,` cmtt9` e `cmtt10` sono i nomi esterni per la macchina da scrivere moderna del computer dei caratteri rispettivamente 8, 9 e 10pt. Con i nomi dei caratteri organizzati in base a tale schema, è possibile utilizzare la funzione `Gen` per abbreviare la voce. Questa funzione combina le informazioni sul carattere e la dimensione richiesta per generare i nomi dei caratteri esterni. Quindi, se scrivi

```tex
<8> <9> <10> gen * cmtt
```

questa sarebbe una stenografia per
```tex
<8> cmtt8 <9> cmtt9 <10> cmtt10
```

che consente di risparmiare otto caratteri nelle tabelle NFSS interne. Questa funzione combina entrambe le parti letteralmente, quindi non dovresti usarla con dimensioni decimali come `14.4`. È inoltre necessario assicurarsi che le cifre nel nome del carattere esterno rappresentino davvero la dimensione del design (ad esempio, `CMR17` è in realtà un romano moderno del computer a 17.28pt).

Sotto tutti gli altri aspetti, la funzione `Gen` si comporta come la funzione vuota. Cioè, l'argomento opzionale, se specificato, rappresenta un fattore di scala e, se usato, genera un messaggio di informazione.

**La funzione "sgen"** La funzione `sgen` è la versione silenziosa della funzione gen. Scrive qualsiasi messaggio solo al file di trascrizione.

**La funzione "GenB"** questa funzione di dimensioni è simile a Gen, ma è destinata ai caratteri in cui la dimensione è codificata nel nome del carattere in centipunti, come i caratteri EC. Di conseguenza, una linea come 

```tex
<9> <10> <10.95> <12> genb * ecrm
```

funge da stenografia

```tex
<9> ecrm0900 <10> ecrm1000 <10.95> ecrm1095 <12> ecrm1200
```

Un argomento opzionale, se presente, avrà lo stesso effetto che farebbe con la funzione vuota.

**La funzione "sgenb"** La funzione `sgenb` è la versione silenziosa della funzione` genb`. Scrive qualsiasi messaggio solo al file di trascrizione.

**La funzione "sub"** La funzione `sub` viene utilizzata per sostituire un gruppo di forma di carattere diverso se non esiste un carattere esterno per il gruppo di forma del carattere corrente. In questo caso, l'argomento non è un nome di carattere esterno ma piuttosto una combinazione di famiglie, serie e forma diversa separata da barre. Ad esempio, il computer moderno del computer non ha una forma in corsivo, solo una forma inclinata. Pertanto, è ragionevole dichiarare la forma inclinata come sostituto di quella in corsivo:

```tex
\DeclareFontShape{OT1}{cmss}{m}{it}{ <-> sub * cmss/m/sl }{}
```

Senza questa dichiarazione, il meccanismo di sostituzione automatico del LaTeX sostituirà la forma predefinita, il computer moderno del computer in posizione verticale.

Ci sono altri buoni usi per la funzione `sub`. Guarda il seguente codice:

```tex
\DeclareFontShape{OT1}{cmss}{m}{sl}{ <-8> sub * cmss/m/n
   <8> cmssi8 <9> cmssi9 <10><10.95> cmssi10 <12><14.4> cmssi12
   <17.28><20.74><24.88> cmssi17 }{}
```

Questa dichiarazione afferma che per dimensioni inferiori a 8pt, il LaTeX dovrebbe guardare nella dichiarazione di forma del carattere per `OT1/CMSS/M/N`. Tali sostituzioni possono essere incatenate. Ad esempio, non esiste un carattere SANS moderno più piccolo di 8pt, quindi il gruppo di forma del carattere sostituito conterrà probabilmente un'altra voce di sostituzione. Tuttavia, l'uso di questo metodo ha il vantaggio che quando si ottiene un carattere aggiuntivo, è necessario modificare una sola dichiarazione di gruppo di forma di carattere: altre dichiarazioni che usano questo carattere ne trarranno beneficio.

**La funzione "ssub"** La funzione `ssub` ha la stessa funzionalità della funzione secondaria ma non produce avvertimenti sullo schermo (il primo 's' significa" silenzioso ").

**La funzione "subf"** La funzione `subf` carica i caratteri allo stesso modo della funzione vuota, ma produce un avvertimento che questa operazione è stata eseguita come sostituzione perché la forma del carattere richiesta non è disponibile. Questa funzione può essere utilizzata per sostituire alcuni caratteri esterni senza la necessità di dichiarare un gruppo di forma di carattere separato per loro, come nel caso della funzione `sub`. Per esempio, 

```tex
\DeclareFontShape{OT1}{ptm}{bx}{n}{ <-> subf * ptmb7t }{}
```

Avverterebbe l'utente che la combinazione richiesta non è disponibile e, quindi, che il carattere `ptmb7t` è stato invece caricato. Poiché questo è meno informativo rispetto all'utilizzo della funzione `sub`, quest'ultima dovrebbe essere preferita.

**La funzione "ssubf"** La versione silenziosa di `subf`, questa funzione scrive i suoi messaggi solo al file di trascrizione.

**La funzione "fissa"** Questa funzione ignora la dimensione richiesta e carica invece il carattere esterno dato come argomento. Se presente, l'argomento opzionale indica la dimensione (in punti) in cui verrà caricato il carattere. Pertanto, questa funzione consente di specificare intervalli di dimensioni per i quali verrà caricato un carattere di dimensioni fisse.

**La funzione "Sfixed"** La versione silenziosa di `fissa", questa funzione viene utilizzata, ad esempio, per caricare il carattere contenente i grandi simboli matematici, che è spesso disponibile solo in una dimensione.

### Opzioni di caricamento dei caratteri
Come accennato in precedenza, ogni famiglia di carattere deve essere dichiarato utilizzando il comando `\dichiarafontfamily`. L'argomento a questo comando, così come il sesto argomento di `\dichiarafontShape`, può essere utilizzato per specificare operazioni speciali che vengono eseguite quando viene caricato un carattere. In questo modo, è possibile modificare i parametri associati a un carattere nel suo insieme.

Oltre alle informazioni su ciascun personaggio, Tex mantiene per ogni carattere esterno una serie di dimensioni globali e altri valori associati al carattere. Ad esempio, ogni carattere ha il suo "personaggio del trattino", il personaggio che viene inserito quando Tex si alza una parola. Un altro esempio è la larghezza normale e l'eleguabilità dello spazio vuoto tra le parole; Un valore viene mantenuto per ogni carattere e cambiato ogni volta che Tex passa a un nuovo carattere. Modificando questi valori nel momento in cui viene caricato il carattere, è possibile ottenere effetti speciali.

Normalmente, i cambiamenti si applicano a un'intera famiglia; Ad esempio, potresti voler proibire le sillabe per tutte le parole comproettanti nella famiglia da scrivere. In questo caso, dovrebbe essere usato il terzo argomento di `\dichiarafontfamily`. Se le modifiche devono essere applicate solo a un gruppo specifico di forma del carattere, è necessario utilizzare il sesto argomento di `\DichiarafontShape`. In altre parole, quando viene caricato un carattere, NFSS applica per la prima volta l'argomento di `\dichiarafontfamily` e quindi la sesta argomento di`\dichiarafontShape`, in modo che possa sovrascrivere le opzioni di carico specificate per l'intera famiglia se necessario.

Con `\Hyphenchar \ font = <number>`, Tex specifica il carattere utilizzato per la sillana. `<number>` rappresenta la posizione di questo carattere all'interno dello schema di codifica. L'impostazione predefinita è il valore di `\defaulthyphenchar`, che è` 45`, che rappresenta la posizione del carattere '-' nella maggior parte degli schemi di codifica. Se si imposta questo numero su `-1`, viene soppressa le sillabazioni. Pertanto, dichiarando

```tex
\DeclareFontFamily{0T1}{cmtt}{\hyphenchar\font=-1}
```

È possibile sopprimere le sillabe per tutti i caratteri nella famiglia `cmtt` con lo schema di codifica` ot1`. I caratteri con la codifica `t1` hanno un carattere di trattino alternativo in posizione 127, in modo da poter impostare, ad esempio,

```tex
\DeclareFontFamily{T1}{cmr}{\hyphenchar\font=127}
```

Il che rende il carattere del trattino diverso dal cruscotto della parola composta inserita in parole come "il cosiddetto". Tex non si alza le parole che contengono già caratteri espliciti del trattino (tranne subito dopo il trattino), che può essere un problema nelle lingue in cui la lunghezza media della parola è molto più grande che in inglese. Con le impostazioni di cui sopra, questo problema può essere risolto.

Ogni carattere tex ha un set associato di dimensioni, che vengono modificate dalle assegnazioni della forma `\fontdimen <umera> \ font = <Meen>`, dove `<number>` è il numero di riferimento per la dimensione e `<Men>` è il valore da assegnare. I valori predefiniti vengono recuperati dal file `.tfm` quando viene caricato il carattere. Ogni carattere ha almeno sette tali dimensioni:

* `\fontdimen1` Specifica l'inclinazione per punto dei personaggi. Se il valore è zero, il carattere è in posizione verticale.

* `\fontdimen2` Specifica la larghezza normale di uno spazio utilizzato tra le parole (spazio interno).

* `\fontdimen3` Specifica l'ulteriore elasticità dello spazio interno, che è la quantità aggiuntiva di spazio bianco che Tex è autorizzato ad aggiungere allo spazio tra le parole per produrre linee giustificate in un paragrafo. In un'emergenza, Tex può aggiungere più spazio di questo valore consentito; In tal caso verrà segnalata una * scatola underfull *.

* `\Fontdimen4` Specifica il restringimento consentito dello spazio intersWord, che è la quantità di spazio che Tex è autorizzato a sottrarre dal normale spazio interno (\ fontdimen2) per produrre linee giustificate in un paragrafo. Tex non si restringerà mai lo spazio interno a meno di questo minimo.

* `\fontdimen5` Specifica *x-height *. Definisce la dimensione orientata al carattere `1ex`.

* `\fontdimen6` specificava la larghezza * quad *. Definisce la dimensione orientata al carattere `1em`.
* `\Fontdimen7` Specifica la quantità prevista come spazio extra da aggiungere dopo determinati caratteri di punteggiatura di fine-frase quando`\non-froccespacing` è in vigore. Viene sempre ignorato o piuttosto sostituito dal valore `\xpaceSkip` quando quel valore è diverso da zero.

Quando si modifica la spaziatura dell'interfaccia associata a un carattere, non è possibile utilizzare un valore assoluto perché tale valore deve essere utilizzabile per tutte le dimensioni all'interno di un gruppo di forma. Pertanto, è necessario definire il valore utilizzando qualche altro parametro che dipende dal carattere. Potresti dire, ad esempio,

```tex
\DeclareFontShape{0T1}{cmr}{m}{n}{...}
   {\fontdimen2\font=.7\fontdimen2\font}
```

Questa dichiarazione riduce lo spazio interno normale al 70% del suo valore originale. Allo stesso modo, la tragualità e il restringimento potrebbero essere cambiate.

Alcuni caratteri nelle formule hanno bisogno di più di sette dimensioni dei caratteri. Vale a dire, i caratteri dei simboli chiamati `simboli` e` largesymbols`. Tex non sarà in grado di compromettere una formula se questi caratteri hanno meno di 22 e 13 parametri `\fontdimen`, rispettivamente. I valori di questi parametri vengono utilizzati per posizionare i caratteri in una formula matematica.

C'è una sfortunata ottimizzazione nel sistema TEX: Tex carica ogni file `.tfm` solo una volta per una determinata dimensione. Pertanto, è impossibile definire un gruppo di forma del carattere (con il comando `\dichiarafontShape`) di caricare un po 'di carattere esterno - dire: `cmtt10` - e usare un altro`\dichiarafontShape` per caricare lo stesso carattere esterno, questa volta cambiando alcuni dei parametri `\fontdimen` o altri parametri associati al contatore. Un tentativo di farlo cambia i valori per entrambi i gruppi di forma del carattere.

Ad esempio, supponiamo di provare a definire una forma del carattere con una spaziatura stretta rendendo più piccolo lo spazio di interword:

```tex
\DeclareFontShape{T1}{ptm}{m}{n}{ <-> ptmr8t }{}
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> ptmr8t }
                     {\fontdimen2\font=.7\fontdimen2\font}
```

Questa dichiarazione non funzionerà. La spaziatura intersword per la forma media cambierà quando la forma stretta viene caricata sui valori specificati lì, e questo non è ciò che è previsto. Il modo migliore per gestire questa situazione è definire un carattere virtuale che contiene gli stessi caratteri del carattere originale ma differisce nelle impostazioni delle dimensioni del carattere. Un'altra possibile soluzione è caricare il carattere a dimensioni leggermente diverse, come nella seguente dichiarazione:

```tex
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> [0.9999] ptmr8t }
                 {\fontdimen2\font=.7\fontdimen2\font}
```

Questo metodo li rende diversi caratteri per Tex con parametri separati `\fontdimen`, in alternativa, in questo caso particolare, è possibile controllare lo spazio di interword impostando`\Spaceskip`, sovrascrivendo così i valori dei caratteri.

## 6.3. Come modificare le famiglie di caratteri e i gruppi di forma dei caratteri

Se è necessaria una dichiarazione di forma del carattere non standard per un determinato documento, questa dichiarazione privata dovrebbe essere inserita in un pacchetto o in preambolo del documento. Sovrascriverà qualsiasi dichiarazione esistente per la combinazione di forma del carattere. Tuttavia, è importante che l'uso di `\dichiarafontfamily` impedisca un successivo caricamento del corrispondente file` .fd` (discusso più avanti in questo articolo). Inoltre, questa nuova dichiarazione non ha alcun effetto sui caratteri che sono già caricati.

## 6.4. Come dichiarare un nuovo schema di codifica dei caratteri

I cambiamenti del carattere che comportano alterazioni nello schema di codifica richiedono determinate precauzioni. Nella codifica `T1`, ad esempio, la maggior parte delle lettere accentate ha i loro glifi, mentre nella tradizionale codifica del testo TEX (` ot1`), le lettere accentate devono essere generate da lettere e accenti usando la primitiva `\accent`. Se i due approcci devono essere miscelati, forse perché un carattere è disponibile solo in una delle codifiche, la definizione di un comando come `\" `deve comportarsi in modo diverso a seconda della codifica attuale del carattere.

Questo è il motivo per cui ogni codifica dei caratteri deve essere introdotta formalmente in LaTeX con un comando `\dichiarafontecnoding`, che richiede tre argomenti. Il primo argomento è il nome della codifica, che verrà successivamente utilizzato per accedere alla codifica con il comando `\fontecoding`. L'elenco di [Schemi di codifica standard](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#choosing-the-encoding) e i loro nomi interni è fornito nella tabella nella Sezione 5.1.
Il secondo argomento contiene qualsiasi codice (come le definizioni) da eseguire ogni volta che il LaTeX passa da uno che codifica a un altro usando il comando `\fontecoding`. L'ultimo argomento contiene il codice da utilizzare ogni volta che si accede al carattere come alfabeto matematico. Pertanto, questi tre argomenti possono essere usati per ridefinire i comandi che dipendono dalle posizioni dei caratteri nella codifica.

Il progetto Latex3E si riserva l'uso di codifiche che iniziano con le seguenti lettere:

* `T` - codifica di testo standard con 256 caratteri.
* `Ts` - simboli progettati per estendere la codifica` t` corrispondente.
* `X` - codifica di testo che non sono conformi ai requisiti rigorosi per le codifiche` T`.
* `M` - codifica matematica standard con 256 caratteri.
* `S` - Altre codifiche di simboli.
* `A` - Altre applicazioni speciali.
* `Ot` - codifica di testo standard con 128 caratteri.
* `OM` - codifica matematica standard con 128 caratteri.

La lettera `O` sottolinea che le codifiche a 128 caratteri sono vecchie e *obsolete *. Idealmente, queste codifiche saranno sostituite dagli standard definiti dal gruppo di utenti Tex in modo che in futuro sarà necessario un cambio di codifica solo se si passa da una lingua all'altra.

Quando si dichiara le tue codifiche private, dovresti scegliere nomi a partire da `l` per" locale "o` e ` per "sperimentale". Le codifiche che iniziano con `u` sono per codifiche" sconosciute "o" non classificate ", cioè per i caratteri che non si adattano a un modello di codifica comune. La convenzione di denominazione introdotta garantisce che i file che utilizzano codifiche ufficiali siano portatili.

Il comando `\dichiarafontecoding` memorizza il nome della codifica recentemente dichiarata nel comando `\lastdeclaredEnCoding`. Questo a volte è utile quando si dichiarano altre informazioni di codifica correlate e, ad esempio, utilizzato nei file di dichiarazione di codifica per i linguaggi cirillici.

Inoltre, come abbiamo menzionato nella discussione sulla sostituzione dei caratteri nell'articolo precedente, i valori predefiniti della famiglia, delle serie e della forma potrebbero dover essere diversi per le codifiche diverse. Per un tale caso, NFSS fornisce il comando `\dichiarafontsubstitution`, che prende la codifica come primo argomento. I prossimi tre argomenti sono i valori predefiniti (associati a questa codifica) per la famiglia, le serie e la forma da utilizzare nel processo di sostituzione automatica. È importante che questi tre argomenti debbano formare una forma di carattere valida. In altre parole, esiste una dichiarazione `\dichiarafontShape` per loro. Altrimenti, verrà emesso un messaggio di errore quando NFSS controlla le sue tabelle interne in `\inizio {Documento}`.

## 6.5. Organizzazione dei file interni

Le famiglie di carattere possono essere dichiarate quando viene generato un file di formato, dichiarato nel preambolo del documento o caricate su richiesta quando un comando che cambia il carattere nel documento richiede una combinazione che non è stata ancora utilizzata. Il primo modo porta al consumo di memoria interna in ogni corsa in LaTeX, anche se il carattere non viene utilizzato. Le ultime due opzioni richiedono un po 'più di tempo durante la formattazione del documento perché le definizioni dei caratteri devono essere lette in fase di esecuzione. Tuttavia, queste ultime soluzioni sono preferibili per la maggior parte dei gruppi di forma perché ti consentono di compromettere un'ampia varietà di documenti con un singolo formato in LaTeX.

Quando viene generato il file di formato, LaTex legge un file chiamato `fontText.ltx`, che contiene il set standard di definizioni della famiglia dei caratteri e alcune altre dichiarazioni relative ai caratteri di testo.
Tutte le altre definizioni della famiglia dei caratteri devono essere dichiarate in file esterni caricati su richiesta: file pacchetto o file di definizione dei caratteri (`.fd`).  Se le definizioni della famiglia dei caratteri vengono inserite in un file di pacchetto, è necessario caricare esplicitamente questo pacchetto dopo il comando `\documentclass`. Tuttavia, esiste una terza possibilità: ogni volta che NFSS ottiene una richiesta per una famiglia di carattere `foo` in uno schema di codifica` bar` e non sa nulla di questa combinazione, proverà a caricare un file chiamato `barfoo.fd`. Se questo file esiste, si suppone che contenga definizioni del gruppo di forma di carattere per la famiglia `foo` nello schema di codifica` bar` - cioè dichiarazioni della forma

```tex
\DeclareFontFamily{BAR}{foo}{...}
\DeclareFontShape{BAR}{foo}{...}{...}{...}{...}
...
\endinput
```

È così che diventa possibile dichiarare un numero enorme di famiglie di carattere per il LaTeX senza riempire la preziosa memoria con le informazioni che probabilmente non vengono mai utilizzate.

Ogni file `.fd` dovrebbe contenere tutte le definizioni dei caratteri per una famiglia di caratteri in uno schema di codifica. Nel file, devono esserci una o più dichiarazioni `\dichiarafontShape` ed esattamente una dichiarazione`\dichiarafontfamily`. Non dovrebbero apparire altre definizioni nel file, tranne forse una dichiarazione `\fornisce File` o alcune dichiarazioni`\typoout` che che informano l'utente sul caricamento del carattere. Invece del comando `\typeout`, è possibile utilizzare il semplice comando tex`\wlog`, che scrive il suo argomento solo al file di trascrizione. Le informazioni dettagliate nel file di trascrizione dovrebbero essere generate da tutti i file `.fd` che vengono utilizzati in produzione perché guardare a questa trascrizione aiuterà a individuare errori fornendo informazioni sui file e sulle loro versioni utilizzate in un determinato lavoro. Se vengono utilizzati comandi `\typeout` o`\wlog`, è importante ricordare che gli spazi e le righe vuote in un file `.fd` vengono ignorati. Pertanto, è necessario utilizzare il comando `\spazio` nell'argomento su`\typeout` o `\wlog` per ottenere uno spazio vuoto sullo schermo e sul file di trascrizione.

Nuovi schemi di codifica non possono essere introdotti tramite il meccanismo `.fd`. NFSS rifiuterà qualsiasi richiesta di passare a uno schema di codifica che non è stato esplicitamente dichiarato nel formato LaTeX (ovvero, `fonttext.ltx`), in un file di pacchetto o nel preambolo del documento.

## 6.6. Come dichiarare nuovi caratteri da utilizzare in matematica

### Come specificare le dimensioni dei caratteri

Per ogni dimensione del testo, NFSS mantiene [tre dimensioni che vengono utilizzate per scrivere formule di matematica](/tex/{{lang.url-fragment}}java/latex-math-fractions-binomial-styles/): la dimensione in cui compromettere la maggior parte dei simboli (selezionati da `\textStyle` o`\DisplayStyle`); la dimensione per abbonamenti e apice del primo ordine (`\scriptstyle`); e le dimensioni per abbonamenti e apripisti di ordine superiore (`\ScriptscriptStyle`). Se si passa a una nuova dimensione del testo per la quale le dimensioni matematiche corrispondenti non sono ancora note, NFSS cerca di calcolarle come frazioni della dimensione del testo. Se non si desidera che NFSS calcoli queste dimensioni, è possibile specificare i valori corretti da soli tramite `\dichiarati '. Questa dichiarazione richiede quattro argomenti: la dimensione del testo esterno e le tre dimensioni matematiche per questa dimensione del testo. Ad esempio, la seguente dichiarazione definisce le dimensioni matematiche per la dimensione 14pt (intestazione) in 14pt, 10pt e 7pt, rispettivamente:

```tex
\DeclareMathSizes{14}{14}{10}{7}
```

Un'altra dichiarazione di seguito (per titoli di livello superiore) informa NFSS che non sono necessarie dimensioni matematiche per la dimensione del testo a 36pt. Ciò può aiutare a evitare il carico inutile di molti caratteri.

```tex
\DeclareMathSizes{36}{}{}{}
```

### Come aggiungere nuovi simboli

Abbiamo già discusso di come usare [comandi alfabeti di matematica](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) per produrre lettere con forme speciali in una formula. Qui mostreremo come aggiungere caratteri contenenti simboli speciali, chiamati *caratteri simboli *e come rendere tali simboli accessibili nelle formule.

L'aggiunta di nuovi caratteri di simbolo è simile alla dichiarazione di un nuovo identificatore di alfabeto matematico: `\Dichiaratesymbolfont` definisce le impostazioni predefinite per tutte le versioni di matematica,`\setSymbolfont` sovrascrive le impostazioni predefinite per una versione particolare.
I caratteri del simbolo matematico sono accessibili tramite un nome simbolico. Ad esempio, se si desidera installare il carattere AMS `MSBM10` (vedere il grafico del glyph di seguito), devi prima rendere il carattere tipografico noto a NFSS usando le dichiarazioni descritte nelle sezioni precedenti.

![grafico msbm10 glyph](/tex/images/java/tutorial/latex-font-selection-6-3.png)

Queste istruzioni sarebbero simili

```tex
\DeclareFontFamily{U}{msb}{}
\DeclareFontShape{U}{msb}{m}{n}{ <5> <6> <7> <8> <9> gen * msbm
        <10> <10.95> <12> <14.4> <17.28> <20.74> <24.88> msbm10}{}
```

e di solito sono inseriti in un file `.fd`. Quindi, devi dichiarare quel carattere simbolo per tutte le versioni matematiche dal seguente comando:

```tex
\DeclareSymbolFont{AMSb}{U}{msb}{m}{n}
```

Rende disponibile il gruppo di forma di carattere `u/msb/m/n` come carattere di simbolo sotto il nome` amsb`. Se ci fosse una serie audace in questa famiglia di caratteri (in effetti, non c'è), si potrebbe successivamente cambiare il set-up per la versione matematica audace dicendo

```tex
\SetSymbolFont{AMSb}{bold}{U}{msb}{b}{n}
```

Dopo essersi preso cura delle dichiarazioni del carattere, è possibile utilizzare questo carattere simbolo in modalità matematica. Ma come dire a NFSS che, ad esempio il comando `\lessdot` in modalità matematica dovrebbe produrre il simbolo corrispondente nell'output? Per fare ciò, devi introdurre i tuoi nomi di simboli a NFSS usando `\dichiarathsymbol`:

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

Il primo argomento è il nome di comando che scegli. Il secondo argomento è uno dei comandi mostrati nella tabella sottostante e determina la natura del simbolo, che, a sua volta, determina la quantità di spazio che il LaTeX mette attorno al simbolo quando si verifica in una formula.

![Tipi di oggetti matematici](/tex/images/java/tutorial/latex-font-selection-6-4.png)

Per inciso, ad eccezione di `\Mathalpha`, questi comandi possono essere usati nelle formule di matematica come funzioni con un argomento, nel qual caso spaziano il loro (possibile complesso) argomento come se fosse del tipo corrispondente.

Il terzo argomento identifica il carattere del simbolo da cui dovrebbe essere recuperato il simbolo, cioè il nome simbolico definito dal comando `\Dichiarali`. Il quarto argomento fornisce la posizione del simbolo nella codifica del carattere, sia come decimale, ottale o valore esadecimale. Puoi facilmente scoprire le posizioni di tutti gli glifi in questo carattere dal diagramma di glifi sopra. Ad esempio, `\lessdot` può essere dichiarato come

```tex
\DeclareMathSymbol{\lessdot}{\mathbin}{AMSb}{"6c}
```

Invece di un nome di comando, puoi usare un singolo carattere come primo argomento. Ad esempio, il pacchetto `Eulerervm` ha diverse dichiarazioni della forma

```tex
\DeclareMathSymbol{0}{\mathalpha}{letters}{"30}
```

Per specificare da dove prendere le cifre da.

Il comando `\dichiarathsymbol` specifica una posizione in qualche carattere di simbolo. Pertanto, è importante che tutti i caratteri esterni associati a questo carattere di simbolo tramite i comandi `\dichiasymbolfont` e `\setSymbolfont` abbiano lo stesso carattere in quella posizione. Il modo più semplice per garantire che ciò sia utilizzare solo caratteri con la stessa codifica (a meno che non sia la codifica `U`, o sconosciuta,, poiché due caratteri in questa codifica non sono necessari per contenere gli stessi caratteri).

Nella tabella di Glyph sopra, puoi anche trovare lettere "Blackboard Bold" (ABC ... a partire dalla posizione `'101`). Se vuoi usare queste lettere come alfabeto matematico, puoi definirle usando `\dichiarathalphabet '. Tuttavia, se questo carattere di simbolo è già caricato, è meglio utilizzare un collegamento per accedere ai singoli simboli:

```tex
\DeclareSymbolFontAlphabet{\mathbb}{AMSb}
```

Cioè, fornisci il nome dell'identificatore di alfabeto matematico e il nome simbolico del carattere del simbolo precedentemente dichiarato.

Un motivo importante per non caricare inutilmente i caratteri due volte è che esiste un limite superiore di 16 caratteri di matematica che possono essere attivi in ​​qualsiasi momento in Tex. Nel calcolo di questo limite, ogni carattere simbolo conta; Gli alfabeti matematici contano solo se vengono effettivamente utilizzati nel documento e contano localmente in ogni versione matematica. Pertanto, se vengono dichiarati otto caratteri di simboli, è possibile utilizzare al massimo otto identificatori di alfabeti matematici (possibilmente diversi) all'interno di ogni versione.

Come breve riassunto: per introdurre nuovi caratteri di simbolo, è necessario emettere un numero limitato di dichiarazioni `\dichiarasymbolfont` e `\setsymbolfont` e un numero potenzialmente elevato di dichiarazioni `\dichiarathsymbol`. Pertanto, l'aggiunta di tali caratteri è meglio eseguita in un file di pacchetto.

### Come introdurre nuove versioni matematiche
Abbiamo già [menzionato](/tex/{{lang.url-fragment}}java/latex-math-fonts/#83-math-formula-versions) che la configurazione standard dichiari automaticamente due versioni matematiche: normale e in grassetto. Per introdurre ulteriori versioni, è possibile utilizzare la dichiarazione `\dichiarathversion`, che prende un argomento: il nome della nuova versione matematica. Tutti i caratteri simboli e tutti gli alfabeti di matematica precedentemente dichiarati sono automaticamente disponibili in questa versione matematica; I caratteri predefiniti sono assegnati a loro, ovvero i caratteri che hai specificato con `\dichiarathalphabet` o`\dichiararingymbont`.

È quindi possibile modificare la configurazione per la tua nuova versione emettendo comandi `\setmathalphabet` e `\setSymbolfont` appropriati per la versione matematica audace, come mostrato in precedenza in questa sezione e nell'articolo su [Fonts in matematica](/tex/{{lang.url-fragment}}java/latex-math-fonts/). Ancora una volta, l'introduzione di una nuova versione matematica è normalmente eseguita in un file pacchetto.


### Come cambiare la configurazione del carattere del simbolo

Abbiamo visto come aggiungere nuovi caratteri di simboli per accedere a più simboli. Gli stessi comandi possono essere utilizzati per modificare una configurazione esistente. Questa capacità potrebbe essere interessante se decidi di utilizzare caratteri speciali in alcune o tutte le versioni matematiche.

Di seguito sono riportate le impostazioni in LaTeX predefinite:

```tex
\DeclareMathVersion{normal} \DeclareMathVersion{bold}
\DeclareSymbolFont{operators} {OT1}{cmr}{m} {n}
\DeclareSymbolFont{letters} {OML}{cmm}{m}{it}
\DeclareSymbolFont{symbols} {OMS}{cmsy}{m}{n}
\DeclareSymbolFont{largesymbols} {OMX}{cmex}{m}{n}

% Special bold fonts only for these:
\SetSymbolFont {operators}{bold}{OT1}{cmr}{bx}{n}
\SetSymbolFont {letters} {bold}{OML}{cmm}{b}{it}
```

Nella configurazione standard, cifre e testo prodotte da operatori come `\log` e `\max` sono prelevati dal carattere simbolo chiamato `operatori '. Per cambiare questo in modo che questi elementi si fondano bene con il carattere di testo principale - diciamo, il computer moderno sans piuttosto che il computer moderno romano - puoi emettere i seguenti comandi:

```tex
\SetSymbolFont{operators}{normal}{0T1}{cmss}{m} {n}
\SetSymbolFont{operators}{bold} {0T1}{cmss}{bx}{n}
```

I caratteri dei simboli con i nomi `simboli` e` largesymbols` svolgono un ruolo unico in tex. Ecco perché richiedono un numero speciale di parametri `\fontdimen` associati. Pertanto, solo i caratteri appositamente preparati possono essere usati come questi due caratteri di simbolo. In linea di principio, si possono aggiungere tali parametri a qualsiasi carattere al momento del caricamento utilizzando il terzo parametro di `\dichiarafontfamily` o il sesto parametro di`\dichiarafontShape`.

## 6.7. Come definire il tuo file `.fd` (esempio)

Se si desidera impostare i caratteri (PostScript) e creare il file `.fd` richiesto, è necessario seguire la procedura discussa in precedenza in questo articolo. Se `fontinst` viene utilizzato per generare i file metrici di carattere richiesti, vengono anche automaticamente generati i corrispondenti file` .fd`. Tuttavia, è facile scrivere a mano un file `.fd` per una singola famiglia di caratteri, a condizione che tu sappia quale codifica dei caratteri viene utilizzato. Ad esempio, studiamo il file di dichiarazione `t1bch.fd` per * bitstream charter * nella codifica` t1`:

```tex
\ProvidesFile{t1bch.fd}[2001/06/04 font definitions for T1/bch.]
% Primary declarations
\DeclareFontFamily{T1}{bch}{}
\DeclareFontShape{T1}{bch}{m}{n}{<-> bchr8t}{}
\DeclareFontShape{T1}{bch}{m}{sc}{<-> bchrc8t}{}
\DeclareFontShape{T1}{bch}{m}{sl}{<-> bchro8t}{}
\DeclareFontShape{T1}{bch}{m}{it}{<-> bchri8t}{}
\DeclareFontShape{T1}{bch}{b}{n}{<-> bchb8t}{}
\DeclareFontShape{T1}{bch}{b}{sc}{<-> bchbc8t}{}
\DeclareFontShape{T1}{bch}{b}{sl}{<-> bchbo8t}{}
\DeclareFontShape{T1}{bch}{b}{it}{<-> bchbi8t}{}
% Substitutions
\DeclareFontShape{T1}{bch}{bx}{n}{<->ssub * bch/b/n}{}
\DeclareFontShape{T1}{bch}{bx}{sc}{<->ssub * bch/b/sc}{}
\DeclareFontShape{T1}{bch}{bx}{sl}{<->ssub * bch/b/sl}{}
\DeclareFontShape{T1}{bch}{bx}{it}{<->ssub * bch/b/it}{}
\endinput
```

La prima riga è una *linea di identificazione *. Quindi segue la dichiarazione della famiglia dei caratteri e la codifica (`bch` e ` t1`) usando `\dichiarafontfamily`. L'argomento di questo comando dovrebbe corrispondere al nome del file `.fd`, tranne per il fatto che la codifica nel nome del file è minuscola. Successivamente, ogni combinazione di serie e forma è mappata al nome di un file `.tfm`. Questi caratteri saranno ridimensionati a qualsiasi dimensione desiderata (avviso `<-->`). La seconda parte del file imposta alcune sostituzioni per le combinazioni per le quali non è disponibile un carattere (ovvero la sostituzione delle serie estese in grassetto con la serie Bold).

Supponendo che tu abbia i caratteri * charter * aggiuntivi (nero e blackitalic), è possibile che tu possa aggiungere le definizioni corrispondenti al file `.fd`. Dovresti prima fornire i caratteri virtuali appropriati, ovviamente, per emulare il set di caratteri `T1`. Fortunatamente, per molti caratteri, questi possono essere scaricati da Internet.
Un altro possibile motivo per creare i tuoi file `.fd` potrebbe derivare dalla necessità di combinare caratteri di famiglie diverse e introdurli al LaTeX come una singola nuova famiglia di caratteri. Ad esempio, esiste la famiglia dei caratteri * aldus * progettata come compagna del carattere tipografico * palatino * (che è stato originariamente progettato come un carattere tipografico display). Poiché Aldus non ha serie audaci, Palatino è una scelta naturale da usare come sostituto audace. Nell'esempio seguente, combiniamo Aldus nella sua serie media con Palatino Bold, chiamando la famiglia di carattere compositi `Zasj`. Viene presentato solo un frammento di un file ".fd` completo, che è sufficiente per illustrare l'idea.

```tex
\ProvidesFile{t1zasj.fd}
   [2003/10/12 font definitions for T1 Aldus/Palatino mix.]
\DeclareFontFamily{T1}{zasj}{}
% Medium series
\DeclareFontShape{T1}{zasj}{m}{n} {<->pasr9d}{}
\DeclareFontShape{T1}{zasj}{m}{sc}{<->pasrc9d}{}
\DeclareFontShape{T1}{zasj}{m}{it}{<->pasri9d}{}
\DeclareFontShape{T1}{zasj}{m}{sl}{<->ssub * pasj/m/it}{}
% Bold series
\DeclareFontShape{T1}{zasj}{b}{n}{<-> pplb8t}{}
\DeclareFontShape{T1}{zasj}{b}{sc}{<->pplbc8t}{}
\DeclareFontShape{T1}{zasj}{b}{sl}{<->pplbo8t}{}
\DeclareFontShape{T1}{zasj}{b}{it}{<->pplbi8t}{}
```

Per accedere a questa "pseudo-famiglia", dobbiamo selezionare `Zasj` nella codifica` T1`. Dobbiamo anche garantire che `\textbf` passi a grassetto, non in grassetto esteso, poiché il nostro file` .fd` non fornisca alcuna sostituzione. Tutto ciò può essere automaticamente fornito da un piccolo pacchetto come questo:

```tex
\ProvidesPackage{fontmix}[2003/10/12 T1 Aldus/Palatino mix.]
\RequirePackage[T1]{fontenc}
\renewcommand\rmdefault{zasj} \renewcommand\bfdefault{b}
```

Quindi, caricando il pacchetto `FontMix`, otteniamo Aldus e Palatino in grassetto per i titoli. Un tale mix di carattere potrebbe non migliorare spesso il testo, quindi questo esempio non suggerisce la creazione di combinazioni casuali.

## 6.8. L'ordine delle dichiarazioni

NFSS richiede di fornire tutte le dichiarazioni in un ordine specifico, in modo che possa verificare se hai specificato tutte le informazioni necessarie. Se dichiari oggetti nell'ordine sbagliato, si lamenta. Ecco le dipendenze che devi onorare:

* `\Dichiarafontfamily` verifica che lo schema di codifica era stato precedentemente dichiarato con`\dichiarafontencoding`.
* `\DichiarafontShape` verifica che la famiglia dei caratteri sia stata dichiarata disponibile nella codifica richiesta (`\dichiarafontfamily`).
* `\Dichiarazioni dichiarate` si assicura che lo schema di codifica sia valido.
* `\Setsymbolfont` assicura inoltre che la versione matematica richiesta sia stata dichiarata (`\dichiarathversion`) e che il carattere simbolo richiesto sia stato dichiarato (`\dichiararymbolfont`).
* `\Dichiaralfontalphabet` verifica che il nome di comando per l'identificatore di alfabeto possa essere usato e che il carattere simbolo sia stato dichiarato.
* `\Dichiarathalphabet` verifica che il nome di comando scelto possa essere usato e che lo schema di codifica sia stato dichiarato.
* `\Setmathalphabet` verifica che l'identificatore di alfabeto fosse stato precedentemente dichiarato con`\dichiarathalphabet` o ``\dichiaralfontalphabet 'e che la versione matematica e lo schema di codifica sono noti.
* `\Dichiarathsymbol` si assicura che il nome del comando possa essere usato (cioè non è definito o precedentemente dichiarato un simbolo di matematica) e che il carattere simbolo fosse stato precedentemente dichiarato.
* Quando viene raggiunto il comando `\Begin {Document}`, NFSS effettua alcuni controlli aggiuntivi. Ad esempio, verifica che la sostituzione predefinita per ogni schema di codifica indichi dichiarazioni di gruppo di caratteri noti.