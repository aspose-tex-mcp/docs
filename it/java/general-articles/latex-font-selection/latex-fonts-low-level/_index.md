---
translation: true
template: /templates/_template-java.md
linktitle: 5. Interfaccia di basso livello
title: L'interfaccia di basso livello | Aspose.TeX per java
weight: 50
url: /java/latex-fonts-low-level/
keywords: Font in LaTeX, LaTeX, sostituzione del carattere in LaTeX, famiglie di caratteri in LaTeX, serie di caratteri in LaTeX, forma del carattere in LaTeX
description: Questo articolo copre l'interfaccia di carattere a basso livello di LaTeX che viene principalmente utilizzata nelle definizioni dei comandi.
lastmod: "2025-06-13"
---

{{<section overview>}}

Contrariamente ai comandi di carattere di alto livello, che sono destinati all'uso in un documento, i comandi di basso livello sono principalmente per definire nuovi comandi in pacchetti o nel preambolo del documento. Per sfruttare al meglio tali comandi, è utile comprendere l'organizzazione interna dei caratteri nello schema di selezione dei caratteri del LaTeX (NFSS).

Da un lato, l'obiettivo dello schema di selezione dei caratteri del LaTeX è consentire la selezione razionale dei caratteri con algoritmi guidati dai principi del markup generico. A tale scopo, sarebbe auspicabile consentire modifiche indipendenti a quanti più attributi di carattere possibile. D'altra parte, le famiglie di carattere nella vita reale normalmente contengono solo un sottoinsieme della miriade di combinazioni di attributi font immaginabili. Pertanto, consentire cambiamenti indipendenti in troppi attributi si traduce in troppe combinazioni per le quali non è disponibile alcun carattere esterno reale e un valore predefinito deve essere sostituito.

Internamente, il LaTeX tiene traccia di cinque attributi di carattere indipendenti: la *codifica corrente*, la *famiglia corrente*, la *serie corrente*, la *forma corrente* e la *dimensione corrente*. L'attributo di codifica è stato introdotto nella versione 2 NFSS quando è diventato chiaro che il supporto per più lingue non sarebbe stato possibile senza mantenere lo schema di codifica dei personaggi indipendentemente dagli altri attributi di carattere.

I valori di questi attributi determinano il carattere attualmente in uso. Il LaTeX mantiene anche un ampio set di tabelle utilizzate per associare le combinazioni di attributi a caratteri esterni (ovvero i file `.tfm che contengono i dati richiesti per il LaTeX per svolgere il proprio lavoro). La selezione dei caratteri viene quindi eseguita in due passaggi:

1. Un certo numero di attributi di carattere viene modificato usando i comandi di basso livello `\fontecoding`,`\fontfamily`, `\fontseries`,`\fontshape` e `\fontsize`.

2. Il carattere corrispondente a queste nuove impostazioni di attributo viene selezionato chiamando il comando `\SelectFont`.

Il secondo passo consiste in diverse azioni. Innanzitutto, il LaTeX controlla se il carattere corrispondente alle impostazioni degli attributi desiderati è noto al sistema (ovvero, il file `.tfm` è già caricato) e, in tal caso, questo carattere è selezionato. Altrimenti, le tabelle interne vengono cercate per trovare il nome del carattere esterno associato a queste impostazioni. Se viene trovato un nome di carattere del genere, il file `.tfm` corrispondente viene letto in memoria, quindi il carattere viene selezionato per la composizione. Se il nome del carattere non viene trovato, il LaTeX cerca di trovare un carattere alternativo, come spiegato più avanti in questo articolo.


## 5.1. Impostazione degli attributi individuali

C'è un comando per ogni attributo di carattere per modificare il suo valore corrente. Tutti questi comandi accettano più o meno qualsiasi stringa di carattere come argomento, ma solo pochi valori hanno senso. Questi valori non sono cablati nell'NFSS, ma piuttosto sono convenzioni impostate nelle tabelle interne. Le seguenti sezioni introducono le convenzioni di denominazione utilizzate nella configurazione standard in LaTeX, ma chiunque può modificare questo set-up aggiungendo nuove dichiarazioni di carattere nelle tabelle interne. Normalmente, chiunque istruisca nuovi caratteri da utilizzare con LaTex dovrebbe cercare di onorare queste convenzioni quando possibile perché solo una convenzione di denominazione coerente può garantire che i caratteri appropriati siano selezionati in un documento genericamente marcato.

Se si desidera selezionare un carattere specifico utilizzando questa interfaccia, ad esempio, il computer moderno Dunhill Bold Condensato 14pt - una conoscenza delle convenzioni di interfaccia da sola non è sufficiente poiché non esiste un carattere esterno per ogni combinazione di valori di attributo. Potresti provare a specificare qualcosa come i seguenti:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

Questo codice sarebbe corretto in base alle convenzioni di denominazione, come vedremo di seguito. Tuttavia, a causa del fatto che questa combinazione di attributi non corrisponde a un carattere reale, il LaTeX dovrebbe sostituire un carattere diverso. Il meccanismo di sostituzione può scegliere un carattere che è abbastanza diverso da quello desiderato, quindi è necessario consultare i tavoli dei caratteri per verificare se la combinazione desiderata è disponibile. Ecco maggiori dettagli sul [processo di sostituzione dei caratteri](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#53-automatic-substitution-of-fonts).

### Scegliere la famiglia dei caratteri

La famiglia dei caratteri è selezionata dal comando `\fontfamily`. Come argomento, prende una stringa di personaggi che si riferisce a una famiglia di carattere dichiarata nelle tabelle interne. La stringa del personaggio è stata definita quando queste tabelle sono state impostate ed è di solito una breve sequenza di lettere - ad esempio, `CMR` per la famiglia romana moderna del computer. I nomi di famiglia non dovrebbero essere più lunghi di cinque lettere perché saranno combinati con forse altre tre lettere per formare un nome di file, che su alcuni sistemi può avere al massimo otto lettere.

### Scegliere la serie di caratteri

Il comando `\fontseries` modifica l'attributo della serie. La serie combina un peso e una larghezza nella sua argomentazione, il che significa che è impossibile cambiare la larghezza dell'attuale carattere indipendentemente dal suo peso. Ciò è accettabile perché è improbabile che sia mai necessario cambiare peso o larghezza individualmente. Al contrario, un cambiamento di peso è spesso accompagnato da un cambiamento di larghezza nelle specifiche del progettista. Questa non è una sorpresa poiché i cambiamenti di peso alterano l'aspetto orizzontale delle lettere e quindi richiedono regolazioni nell'espansione (larghezza) per produrre un aspetto ben bilanciato.

I nomi sia per il peso che per la larghezza sono abbreviati nei nomi delle serie, in modo che ogni combinazione sia univoca. Queste convenzioni di denominazione sono mostrate nella tabella seguente. Qualsiasi istanza di `m` (in piedi per medio in peso o larghezza) viene omesso, tranne quando sia il peso che la larghezza sono medi, nel qual caso viene utilizzato un singolo` m`. Ad esempio, BOLD espanso sarebbe `bx`, mentre il mezzo espanso sarebbe` x` e il mezzo audace sarebbe `b`.

![Convenzioni di denominazione della serie di caratteri](/tex/images/java/tutorial/latex-font-selection-5-1.png)

### Scegliere la forma del carattere

Il comando `\fontShape` cambia l'attributo di forma. Per le forme standard, vengono utilizzate abbreviazioni a una e due lettere. Queste forme sono elencate nella tabella seguente:

![Font Forme Convenzioni di denominazione](/tex/images/java/tutorial/latex-font-selection-5-2.png)

### Scegliere la dimensione del carattere

Il comando `\fontsize {<sile>} {<skip>}` cambia la dimensione del carattere. Ci vogliono due argomenti: il `<size>` per passare e la base `<skip>` (la distanza tra le baseline per questa dimensione). Le dimensioni dei caratteri vengono normalmente misurate in punti, quindi per convenzione, l'unità viene omessa. Lo stesso vale per il secondo argomento. Tuttavia, se il salto di base dovrebbe essere una lunghezza della gomma, è necessario specificare un'unità. Pertanto, potrebbe essere richiesto una modifica della dimensione valida


```tex
\fontsize{14.4}{17}\selectfont
```

Anche se tale richiesta è valida, potrebbe non esserci un carattere esterno corrispondente in queste dimensioni. In tal caso, il LaTeX proverà a trovare una dimensione vicina se le sue tabelle interne consentono la correzione delle dimensioni o segnala un errore altrimenti.

Se usi caratteri esistenti in dimensioni arbitrarie, è possibile selezionare qualsiasi dimensione desideri, ovviamente:


```tex
\fontsize{1in}{1.2in}\selectfont A text in an arbitrary font size
```

### Scegliere la codifica

Il comando `\fontecoding` viene utilizzato per modificare la codifica. L'argomento è il nome interno per la codifica desiderata. Questo nome deve essere noto al LaTeX, sia come una delle codifiche predefinite (caricate dal kernel) o come dichiarato con il comando `\dichiarafontecoding`. Ecco ulteriori informazioni su [dichiarazione di codifiche di carattere](/tex/{{lang.url-fragment}}java/latex-fonts-setup/#64-how-to-declare-a-new-font-encoding-scheme). I nomi di codifica dei caratteri standard sono elencati nella tabella seguente:

![Nomi di codifica dei caratteri standard](/tex/images/java/tutorial/latex-font-selection-5-3.png)

NFSS si basa sul presupposto che la maggior parte (o meglio, tutti) caratteri per il testo sono disponibili nella stessa codifica purché vengano utilizzati per compensare nella stessa lingua. In altre parole, le modifiche alla codifica dovrebbero essere necessarie solo se si passa da una lingua all'altra. In questo caso, i pacchetti di supporto linguistici (ad es. Dal sistema `Babele ') dovrebbero normalmente prendersi cura delle codifiche dietro le quinte.

Nell'esempio seguente, cambiamo manualmente la codifica definendo un ambiente `cyr` per la composizione in cirillica. In questo ambiente, sia la codifica dei caratteri che la codifica input sono modificati localmente. Naturalmente, per un adeguato supporto linguistico, sarebbe necessario un lavoro aggiuntivo, come la modifica delle regole di sillado. Le codifiche vengono dichiarate in LaTeX caricandoli con il pacchetto `Fontenc`. `T2A` Specifica una delle codifiche cirilliche standard. `T1` diventa la codifica predefinita da quando viene caricata per ultimo.

![Impostazioni Codice sorgente Exmple Exmple](/tex/images/java/tutorial/latex-font-selection-5-4.png)

![Impostazioni output exmple](/tex/images/java/tutorial/latex-font-selection-5-5.png)

Sfortunatamente, `T1` non può essere completamente implementato per la maggior parte dei caratteri PostScript. Cinque caratteri nell'esempio seguente sono probabilmente visualizzati come macchie di inchiostro, che indicano glifi mancanti nel carattere. Si noti che i simboli "per mille" e "per diecimila" sono effettivamente formati unendo un segno percentuale e uno o due piccoli zeri aggiuntivi; Manca solo quest'ultimo glifo.


```tex
\usepackage[T1]{fontenc}
-----------------------------------------
\fontfamily{cmr}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand \par
\fontfamily{ptm}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand{}

```

![T1 per i caratteri postscritti](/tex/images/java/tutorial/latex-font-selection-5-5.png)

## 5.2. Impostazione di più attributi di carattere

Durante la progettazione di stili di pagina o comandi orientati al layout, spesso si desidera selezionare un particolare carattere, ovvero è necessario specificare i valori per tutti gli attributi. Per questo, LaTex fornisce il comando `\usefont`, che richiede quattro argomenti: codifica, famiglia, serie e forma. Il comando aggiorna tali attributi e quindi chiama `\SelectFont`. Se si desidera specificare anche le dimensioni e il salto di base, posiziona un comando `\fontsize` prima di`\usefont`. Per esempio,


```tex
\fontsize{14}{16pt}\usefont{OT1}{cmdh}{bc}{it}
```

produrrebbe lo stesso risultato dei seguenti comandi:


```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

Latex fornisce anche la dichiarazione `\dichiarafixedfont`, che può essere utilizzata per definire nuovi comandi che passano a un carattere completamente fisso. Tali comandi sono molto veloci perché non devono cercare tabelle interne. Pertanto, sono molto utili nelle definizioni di comando che devono passare avanti e indietro tra i caratteri. Ad esempio, se vogliamo dichiarare un comando per il composizione di determinati testo nella dimensione dello script, possiamo farlo come segue:


```tex
\DeclareFixedFont\ScriptSizeFont{\encodingdefault}{\familydefault}
    {\seriesdefault}{\shapedefault}{7pt}
\newcommand\theScript[1]{{\ScriptSizeFont #1}}
```

Puoi vedere che `\dichiarafixedfont` ha sei argomenti. Il nome del comando da definire è seguito dagli attributi dei cinque font nelle classificazioni NFSS. Invece di passare valori fissi (ad eccezione della dimensione), vengono utilizzati i ganci integrati che descrivono il carattere del documento principale. Pertanto, nell'esempio sopra `\ScriptSizeFont` dipende ancora dal layout complessivo del documento. Tuttavia, una volta eseguita la definizione, il suo significato è congelato, quindi le modifiche successive alle impostazioni predefinite non cambieranno il carattere `\ScriptSizeFont`.

## 5.3. Sostituzione automatica dei caratteri

Quando non è possibile effettuare una richiesta di modifica del carattere perché la combinazione non è nota al LaTeX, cerca di recuperare usando un carattere con attributi simili. Ecco cosa succede in dettaglio: se la combinazione di schema di codifica, famiglia, serie e forma non è dichiarata, il LaTeX cerca di trovare una combinazione nota cambiando prima l'attributo di forma in un valore predefinito. Se la combinazione risultante è ancora sconosciuta, cerca di cambiare la serie in un valore predefinito. Come ultima risorsa, cambia la famiglia in un valore predefinito. Infine, cerca la voce della tabella interna per trovare la dimensione richiesta. Ad esempio, se chiedi `\ttfamily \ bfseries \ itshape` - un carattere da scrivere in una serie audace e forma corsivo (che di solito non esiste) - allora otterrai un carattere da scrivere in serie medio e forma del LaTeX prima di ripristinare la forma prima di ripristinare la serie. In tal caso, se preferisci un carattere da scrivere con forma corsivo, devi annunciare le tue preferenze al LaTeX usando la funzione `sub`, che è spiegata nell'articolo [come impostare nuovi caratteri](/tex/{{lang.url-fragment}}java/latex-fonts-setup/).

Il processo di sostituzione non modifica mai lo schema di codifica perché qualsiasi alterazione può produrre caratteri errati nell'output. Come ricorderete, lo schema di codifica definisce come interpretare i caratteri di input, mentre gli altri attributi definiscono come dovrebbe apparire l'output. Pertanto, non sarebbe appropriato se, ad esempio, un segno di sterlina fosse sostituito con un cartello in dollari in un contratto solo perché il software cercava di essere intelligente.

Pertanto, ogni schema di codifica deve avere una famiglia, una serie e una forma predefinite, e almeno la combinazione costituita dallo schema di codifica insieme ai corrispondenti impostazioni predefinite deve avere una definizione all'interno del LaTeX.

## 5.4. Come utilizzare i comandi di basso livello nel documento

I comandi di basso livello descritti nelle sezioni precedenti sono destinati a essere utilizzati nelle definizioni di comandi di alto livello, in file di classe di documenti o pacchetto o nel preambolo del documento.

Se è possibile utilizzare comandi di alto livello come `\textsf`, è necessario evitare di utilizzare i comandi di basso livello direttamente nel documento quando possibile. Il motivo è che i comandi di basso livello sono istruzioni molto precise per passare a un carattere particolare, mentre i comandi di alto livello possono essere personalizzati usando pacchetti o dichiarazioni nel preambolo. Supponiamo che tu abbia selezionato il computer moderno sans nel tuo documento usando `\fontfamily {CMSS} \ SelectFont`. Se in seguito decidi di compromettere l'intero documento con i caratteri del pacchetto PSNFSS - diciamo, tempi - l'applicazione di un pacchetto cambierebbe solo quelle parti del documento che non contengono comandi espliciti `\fontfamily`.