---
translation: true
template: /templates/_template-java.md
linktitle: Caratteri di testo in LaTeX
title: 3. Come usare i caratteri in LaTeX nel testo
weight: 30
url: /java/latex-text-fonts/
keywords: Caratteri in LaTeX, LaTeX, comandi del carattere di testo in LaTeX, LaTeX grande, dimensione del carattere in LaTeX
description: Questo articolo copre i comandi del carattere in LaTeX che cambiano indipendentemente attributi di carattere per l'uso nel testo normale.
lastmod: "2026-04-21"
---

{{<section overview>}}

Quando si scrive un documento LaTex, i tag di markup utilizzati per strutturare il documento scelgono automaticamente i caratteri appropriati. Ad esempio, per l'intestazione di una sezione, tali attributi di carattere come dimensioni di grandi dimensioni e peso audace sono definiti dalla classe del documento e applicati quando viene utilizzato un comando `\sezione`. Pertanto, raramente è necessario specificare direttamente gli attributi di carattere.

Ma a volte è necessario. Ad esempio, potresti voler scegliere una famiglia di caratteri diversa (o un altro attributo di carattere generale) per il testo principale. Tale alterazione spesso può essere effettuata semplicemente come specificando un pacchetto appropriato.

Un altro caso è quando si desidera contrassegnare alcuni frammenti del documento come speciale, ad esempio, per indicare acronimi, esempi o nomi delle società. Se scegli di usare, diciamo, un carattere sans serif per questi frammenti, puoi farlo mediante nomi dell'azienda circostante con `\textsf {...}`. Ma la migliore pratica è definire un nuovo comando (diciamo, `\Company`) a questo scopo. La definizione di singoli comandi per cose logicamente diverse rende più facile cambiare la formattazione in seguito in modo coerente.

Potresti anche voler scrivere una tabella di dimensioni più piccole per adattarlo a una pagina. Poiché le classi di documenti possono formattare i documenti automaticamente solo in una certa misura, questo desiderio è legittimo. Ne consegue che la formattazione a mano, come l'inserimento delle pause di pagina, è spesso necessaria per creare una versione finale. Sfortunatamente, la formattazione esplicita rende difficile l'utilizzo del documento difficile e soggetto a errori. Pertanto, l'uso diretto dei comandi che cambia i caratteri in un documento dovrebbe essere ridotto al minimo. Questo vale anche per tutti i comandi di formattazione visiva.


## 3.1. Come utilizzare i comandi font nel LaTeX standard

Il carattere utilizzato per il testo principale di un documento è chiamato *Font principale *, *Body Font* o *Font normale*. Viene automaticamente selezionato all'inizio del documento e in alcuni costrutti, come note a piè di pagina e figure. Intestazioni di sezione e altri tag di markup logico passano automaticamente a un carattere o dimensione diverso, a seconda della classe del documento. Pertanto, l'introduzione del markup logico corretto è l'unica azione richiesta dall'autore. Tuttavia, a volte può essere desiderabile evidenziare manualmente alcune parti del testo scegliendo un carattere tipografico appropriato. Questo viene fatto con i comandi discussi di seguito.

Esistono due forme per la maggior parte dei comandi che cambiano il carattere: un comando con un argomento, come `\textbf {...}` e una dichiarazione, come `\bfseries`. La forma dichiarativa non richiede argomenti ma piuttosto istruisce il LaTeX che da ora in poi (fino alla fine dell'attuale gruppo di parentesi graffe o ambienti) dovrebbe comportarsi in modo speciale. Ciò significa che non dovresti scrivere qualcosa come `\bfseries {...}`, perché ciò renderebbe tutto audace da questo punto fino alla fine dell'ambiente attuale.

È meglio utilizzare i comandi del carattere con un argomento per cambiare i caratteri per le singole parole o le frasi brevi all'interno del tuo documento. Per frammenti più lunghi, è necessario utilizzare la forma dell'ambiente della dichiarazione, come mostrato nell'esempio seguente:

```tex
Some words in this sentence are \begin{bfseries}typeset in bold letters.
The bold typeface\end{bfseries} continues here. 
```

![La forma dell'ambiente di \ bfseries](/tex/images/java/tutorial/latex-font-selection-3-1.png)

Le stesse forme dichiarative sono spesso migliori nella definizione di nuovi ambienti o comandi.

> È anche importante che i comandi di carattere con un argomento non consentano interruzioni di paragrafo nei loro argomenti.

### Il carattere del documento principale
Usando il comando `\textNormal` o la dichiarazione`\NormalFont`, è possibile passare al carattere del documento principale. In genere si verificano solo nelle definizioni di comandi o ambienti quando è importante definire un modo per compromettere sempre lo stesso carattere indipendentemente dalle condizioni circostanti. Ad esempio, il comando per compensare i nomi dei comandi in LaTeX sembrerebbe come segue:

```tex
\newcommand\Lcs[1]{{\normalfont\ttfamily\textbackslash#1}%}
```

L'uso di `\NormalFont` impedisce ai nomi dei comandi che escono in corsivo anche all'interno del testo di testo in corsivo.

### Famiglie di caratteri standard

Per impostazione predefinita, LaTex mantiene tre famiglie di carattere: un carattere di testo serificato, accessibile con il comando `\textrm`; un carattere di testo sans serif, accessibile da `\textsf`; e un carattere da scrivere (monospaziato), accessibile da `\textttt`. Le forme di dichiarazione di questi comandi sono rispettivamente `\rmfamily`,`\sffamily` e `\ttfamily`.

I nomi esatti delle famiglie di carattere esterne accessibili da questi comandi dipendono dalla classe del documento ma possono essere modificati nel preambolo o dai pacchetti. Come impostazione predefinita di installazione, la famiglia dei caratteri Serifed è **Computer Modern Roman**, la famiglia Sans Serif è **Computer Modern sans** e la famiglia da scrivere è **computer moderno di computer**. Se si utilizza un configurazione diversa, dovresti fare attenzione a definire queste famiglie di carattere predefinite in modo che i caratteri possano essere miscelati senza scontri visivi. È anche importante assicurarsi che i caratteri esterni siano disponibili nella corretta risoluzione per il dispositivo di uscita mirato.

La maggior parte delle classi di documenti imposta il carattere serificato, accessibile da `\textrm`, come carattere principale del documento, quindi il comando `\textrm` non viene spesso utilizzato. Ma se un designer di documenti ha scelto un carattere sans serif come carattere tipografico principale, il `\textrm` sarebbe la famiglia di carattere serificata alternativa.

### Serie di caratteri standard

Nel LaTeX, la * serie * è una combinazione di due attributi: larghezza e peso (audacia). Latex consente di modificare la serie con due comandi: `\textmd` e `\textbf`. Le dichiarazioni corrispondenti sono rispettivamente `\mdseries` e `\bfseries`. Il primo comando seleziona un carattere con valori medi per la larghezza e il peso, mentre quest'ultimo passa a una serie più audace. Ancora una volta, i valori effettivi dipendono dalla classe del documento e dalle sue opzioni o dai pacchetti successivi. In una configurazione predefinita, `\textbf` passa a una versione estesa in grassetto del tipografico corrente, mentre`\textmd` ritorna alla versione medio e media del peso del carattere corrente.

### Forme di carattere standard

La *forma* dell'attuale carattere tipografico è il terzo attributo di carattere che può essere modificato indipendentemente dagli altri. La forma predefinita per la maggior parte dei documenti è la forma verticale, a cui è possibile accedere con il comando `\textup` o la dichiarazione`\upshape` se necessario.

I comandi più comunemente usati sembrano essere rispettivamente `\textit` e `\textsc`, che passano a una forma di carattere in corsivo o piccoli tappi. Le dichiarazioni corrispondenti sono `\itshape` e `\schape`.

Il comando `\texsl` (il suo modulo di dichiarazione è`\sshape`) passa alla forma inclusa. Una famiglia di carattere contiene spesso solo un corsivo o una forma inclusa, sebbene il romano moderno del computer contenga entrambi.

Nel punto in cui si passa da inclinazione a verticale, i personaggi di solito si avvicinano troppo insieme, specialmente se l'ultimo personaggio inclinato ha un ascender. La giusta quantità di spazio extra che dovrebbe essere aggiunto a questo confine è chiamata correzione **corsivo**. La larghezza esatta di questo spazio dipende dal singolo carattere ed è memorizzata nel file `.tfm`. I comandi del carattere con gli argomenti aggiungono automaticamente la correzione del corsivo, ma quando vengono impiegate dichiarazioni, deve essere inserito manualmente usando `\/`. Per un carattere verticale, la correzione corsiva dei personaggi è generalmente zero o molto piccola, sebbene ci siano alcune eccezioni. L'esempio successivo mostra come utilizzare correttamente le dichiarazioni che cambiano la forma che passano a forme inclinate.

```tex
\raggedright
When switching back from {\itshape italic\/} or {\slshape slanted\/} shapes to an upright font one
should add the {\itshape italic correction}, except when a small punctuation character follows.
```

![La correzione corsiva](/tex/images/java/tutorial/latex-font-selection-3-2.png)

I piccoli tappi sono talvolta usati nelle intestazioni o nei nomi dei formati. Per quest'ultimo caso, è possibile, ad esempio, definire il comando `\name` come segue:

```tex
\newcommand\name[1]{\textsc{#1}}
```

In alternativa, è possibile utilizzare due dichiarazioni:

```tex
\newcommand\name[1]{{\normalfont\scshape #1}}
```

Il primo comando passa semplicemente alla forma dei piccoli capsuli, mentre la seconda forma ripristina inizialmente tutti gli attributi di carattere ai loro impostazioni predefinite. Quale opzione da scegliere dipende dai caratteri disponibili e dal tipo di documento. Con il computer moderno, solo le famiglie romane e da scrivere contengono forme di piccoli tappi, quindi la seconda definizione potrebbe essere preferita in alcune applicazioni perché utilizzerà piccoli tappi (sebbene seritati) anche in un contesto `\sffamily`. Il primo comando richiederebbe una serie media, piccoli cappelli, carattere a forma di famiglia SANS moderna del computer. Questo carattere non è disponibile, quindi il LaTeX proverebbe a trovare un sostituto cambiando prima l'attributo di forma al suo valore predefinito. Di conseguenza, non otterresti piccoli tappi.

Un altro comando di forma speciale in LaTeX è il comando `\empe` , che enfatizza i frammenti nel testo normale. La sua forma dichiarativa è `\em`. Come tradizione, le parole enfatizzate nel testo sono ambientate in corsivo; Ma se si desidera enfasi in un frammento già in corsivo del testo, di solito si passa al carattere verticale. Il comando `\emugh` supporta questa convenzione passando alla forma`\itshape` se il carattere corrente è in posizione verticale e alla forma `\upshape` se il carattere corrente è già inclinato (cioè, se la forma è`\itshape` o `` slshape`). Pertanto, l'utente non deve preoccuparsi dello stato attuale del testo quando si utilizza il comando `\emugh` o la dichiarazione`\em`.

```tex
{\em Nevertheless, one has to be careful about the\/ {\em proper\/} use of italic corrections
on both ends of the emphasized text}. It is therefore better to use the \verb=\emph= command,
which \emph{automatically} takes care of the italic correction on both sides.
```

![Enfatizzare i frammenti di testo](/tex/images/java/tutorial/latex-font-selection-3-3.png)

### Dimensioni di carattere standard

Ci sono 10 comandi che cambiano dimensione in LaTeX. Questi comandi non hanno moduli di comando corrispondenti con un argomento poiché le modifiche alla dimensione del carattere sono normalmente utilizzate solo nelle definizioni dei comandi.

![Dimensioni di carattere standard](/tex/images/java/tutorial/latex-font-selection-3-4.png)

La dimensione selezionata da questi comandi dipende dalle impostazioni della classe del documento e possibilmente da opzioni (ad esempio, `11pt`) specificate. In generale, `\normalize` corrisponde alla dimensione principale del documento e i comandi che cambiano dimensioni formano una sequenza ordinata che inizia con `\tiny` come la più piccola e sale fino a `\enorme` come dimensioni più grandi. Può succedere che più di un comando si riferisca alle stesse dimensioni. Ad esempio, quando viene scelto un grande `\normalize`, `\enorme` può essere uguale a `\enorme`. Ma l'ordine è sempre onorato però.

I comandi che cambiano dimensioni per le dimensioni del testo principali (cioè, `\normalize`, `\piccolo` e `\footnotesize`) in genere influenzano la spaziatura intorno agli elenchi e ai display. Pertanto, per cambiare il loro comportamento, non si dovrebbe semplicemente sostituire la loro definizione con una chiamata a `\fontsize`, ma invece iniziare dalla loro definizione originale, come documentato in` classi.dtx`.

## 3.2. Come combinare i comandi di carattere standard

Come già mostrato, i comandi e le dichiarazioni che cambiano il carattere standard possono essere combinati, risultando nella selezione di un carattere tipografico che corrisponde alla combinazione di attributi di carattere. Vedi l'esempio seguente:

```tex
One can typeset a text {\sffamily\bfseries\large in a large sans serif
bold typeface} but note the unchanged leading! \LaTeX{} uses the value
in force at the \emph{end} of the paragraph!
```

![Combinazioni del carattere in LaTeX](/tex/images/java/tutorial/latex-font-selection-3-5.png)

Internamente, il comando `\sffamily` passa alla famiglia predefinita sans serif, quindi `\bfseries` passa alla serie Bold predefinita in questa famiglia e infine `\Large` seleziona una grande dimensione ma lascia invariati tutti gli altri attributi. La principale sembra essere invariata perché l'ambito di `\grandi` finisce prima della fine del paragrafo. I file metrici di carattere vengono caricati per tutti i caratteri tipografici intermedi, anche se questi caratteri non vengono mai utilizzati. Nell'esempio sopra, sarebbero "sans serif media 10pt" dopo la `\sffamily`, quindi" sans serif grad esteso 10pt "dopo il`\bfseries` e, infine, "sans serif grad esteso 14pt", che è il carattere che viene effettivamente usato. Pertanto, tali comandi di alto livello possono forzare la selezione dei caratteri del LaTeX a caricare inutilmente caratteri che non vengono mai utilizzati. Vi è solo una piccola perdita di velocità di elaborazione quando una data combinazione viene utilizzata per la prima volta. Ma se hai molte combinazioni diverse di questo tipo, dovresti considerare meglio di definendole in termini di [dichiarazioni primitive che cambiano i caratteri](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/).

## 3.3. Comandi e dichiarazioni di carattere confronto

I comandi che cambiano il carattere con gli argomenti iniziano tutti con `\text ...` (tranne `\enf`) per sottolineare che sono destinati all'uso nel testo normale. L'uso di tali comandi anziché le forme dichiarative ha il vantaggio di mantenere la coerenza con altri costrutti in LaTeX. Sono destinati a compromettere brevi pezzi di testo in una famiglia, serie o forma specifiche. La tabella seguente mostra l'effetto di questi comandi.

![Comandi e dichiarazioni](/tex/images/java/tutorial/latex-font-selection-3-6.png)

Un altro vantaggio di questi comandi è che inseriscono automaticamente qualsiasi correzione in corsivo necessaria su entrambi i lati della loro argomentazione. Pertanto, non devi preoccuparti di perdere le correzioni in corsivo quando si cambiano i caratteri.

La correzione corsiva inserita automaticamente è sbagliata in pochissime situazioni. Di solito si consiglia di omettere la correzione in corsivo se un piccolo carattere di punteggiatura (una virgola o un periodo) segue direttamente il cambiamento di carattere. È possibile definire in quali casi la correzione corsivo dovrebbe essere soppressa. Questo viene fatto specificando i personaggi che dovrebbero annullare una precedente correzione corsivo nell'elenco `\nocorrlist`. La definizione predefinita per questo comando è

```tex
\newcommand{\nocorrlist}{,.}
```

È anche possibile sopprimere la correzione corsivo in singoli casi. A tale scopo, viene fornito il comando `\nocorr`. Si noti che devi mettere `\nocorr` sull'estremità sinistra o destra all'interno dell'argomento dei comandi`\text ... `, a seconda del lato del frammento richiede la soppressione della correzione corsivo.

```tex
\emph{When using the \LaTeX{} high-level font commands, the \emph{proper} use of
italic corrections is automatically taken care of}. Only \emph{sometimes} one has
to help \LaTeX{} by adding a \verb=\nocorr= command.
```

![La correzione corsiva](/tex/images/java/tutorial/latex-font-selection-3-7.png)

Al contrario, i moduli di dichiarazione sono spesso più adatti per definire i propri comandi o ambienti.

```tex
% Part of the preamble
\newenvironment{bfitemize}{\begin{itemize}%
  \normalfont\bfseries\raggedright}{\end{itemize}}
-----------------------------------------------
\begin{bfitemize}
\item This environment produces boldface items.
\item It is defined in terms of \LaTeX's
\texttt{itemize} environment and NFSS declarations.
\end{bfitemize}
```

![L'elenco con elementi BoldFace](/tex/images/java/tutorial/latex-font-selection-3-8.png)

## 3.4. Come accedere a tutti i personaggi di un carattere

Anche se un personaggio esiste in un carattere, a volte è impossibile inserirlo dalla tastiera. Molti caratteri utili sono accessibili tramite comandi come `\ss` o`\ae`. Alcuni personaggi possono essere implicitamente generati da sequenze di lettere come `ffi`, che produce la legatura" FFI "e` --- `, che produce il lungo trattino nei caratteri tex standard.

Inoltre, il comando `\Symbol` consente di accedere a qualsiasi carattere in un carattere dando il suo numero nello schema di codifica corrente come decimale, ottale (preceduto da` '`) o esadecimale (preceduto dal numero` ``).

```tex
\fontencoding{T1}\selectfont
-----------------------------------------------
In the font encoding (\texttt{T1}), characters like \symbol{"DE},
symbol{'237}, and \symbol{32} are included and can be accessed with
the \verb=\symbol= command.
```

![Il comando \ simbolo](/tex/images/java/tutorial/latex-font-selection-3-9.png)

## 3.5. Come modificare i caratteri di testo predefiniti

Se si desidera modificare facilmente l'aspetto generale di un documento, è possibile utilizzare i ganci integrati di LaTex che modificano il comportamento dei comandi che cambiano il carattere di alto livello discussi in precedenza. I valori di questi ganci possono essere impostati nei file del pacchetto o nel preambolo di un documento utilizzando `\RenewCommand`. Ecco l'elenco dei ganci:

![I ganci per il carattere di alto livello](/tex/images/java/tutorial/latex-font-selection-3-10.png)

Ad esempio, se scrivi nel preambolo
```tex
\renewcommand\familydefault{cmss}
```

Un intero documento verrebbe fuori in Computer Modern Sans, perché questa ridefinizione cambia la famiglia dei caratteri per il carattere principale utilizzato dal LaTeX. In dettaglio, il carattere del documento principale è determinato dai valori di `\encodingDefault`,`\FamilyDefault`, `\SeriesDefault` e `\ShapEDefault`. Ciò significa che devi assicurarti che questi comandi siano definiti in modo tale che la loro combinazione indica una forma di carattere esistente nelle tabelle interne del LaTeX.

Il valore predefinito di `\encodingDefault` (` ot1`) serve effettivamente la compatibilità. Ciò significa che il LaTeX presume che la maggior parte dei caratteri utilizzi la codifica originale. Nella maggior parte dei casi, è meglio usare la codifica `T1` perché contiene molti glifi aggiuntivi che non sono disponibili con` ot1` e consente una corretta sillabazione per le parole con caratteri accentati. Al giorno d'oggi, alcuni caratteri non supportano affatto `ot1` poiché sono progettati per l'uso con` t1`.

È importante ricordare che non tutti i caratteri possono essere utilizzati come impostazione predefinita di codifica dei documenti. Un prerequisito è che la codifica deve includere la maggior parte delle lettere ASCII visibili nelle loro posizioni standard. `\EncodingDefault` può essere modificato caricando il pacchetto` Fontenc` con una o più opzioni.

L'impostazione iniziale di `\FamilyDefault` significa che la modifica di`\rmDefault` cambierà implicitamente `\FamilyDefault` al nuovo valore, purché non sia definita alcuna impostazione speciale per`\FamilyDefault`. Ma se `\familydefault` viene modificato,`\rmdefault` non è influenzato.