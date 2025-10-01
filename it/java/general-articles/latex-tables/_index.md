---
translation: true
template: /templates/_template-java.md
linktitle: Tavoli in LaTeX
title: Tabelle in LaTeX
weight: 50
url: /java/latex-tables/
keywords: Tabelle in LaTeX, ambiente tabulare, design della tabella in LaTeX, formattazione delle tabelle in LaTeX, tabelle di composizione in LaTeX, layout della tabella in LaTeX, spaziatura del tavolo in LaTeX, personalizzazione di tabelle in LaTeX, allineamento della tabella in LaTeX, multirow e multicolunno nelle tabelle in LaTeX
description: Questo articolo è una guida rapida per la creazione di tabelle funzionali, adatte ai lettori, visivamente sporche e professionali in LaTeX.
lastmod: "2025-06-13"
---

{{<section overview>}}

## 1. Introduzione

Le tabelle svolgono un ruolo importante nel migliorare la chiarezza, l'organizzazione e il fascino visivo dei documenti accademici e professionali. Servono come un modo potente per presentare dati, confronti e relazioni complesse in un formato strutturato e facilmente digeribile. Ecco una breve panoramica della loro importanza:

1. **Riassunto dei dati**: le tabelle forniscono una rappresentazione condensata di informazioni che altrimenti potrebbero richiedere più paragrafi da spiegare. Consentono agli autori di presentare grandi quantità di dati in modo conciso, rendendo più facile per i lettori comprendere i punti chiave.

2. **Visualizzazione chiara**: dati complessi, come figure statistiche, risultati del sondaggio e risultati sperimentali, possono essere presentati in modo più efficace usando le tabelle. Il formato tabulare aiuta i lettori a identificare tendenze, schemi e valori anomali molto più facili.

3. **Analisi comparativa**: le tabelle abilitano confronti fianco a fianco di diversi set di dati. Che si tratti di confrontare le specifiche del prodotto, le prestazioni finanziarie o le variabili di ricerca, le tabelle aiutano i lettori a trarre conclusioni significative a colpo d'occhio.

4. **Organizzazione logica**: le tabelle forniscono una struttura logica che separa i dati in righe e colonne. Questa organizzazione facilita la presentazione di dati che hanno categorie distinte, consentendo ai lettori di navigare e trovare facilmente informazioni specifiche.

5. **Integrità dei dati**: in contesti accademici e professionali, l'accuratezza dei dati è fondamentale. Le tabelle consentono agli autori di presentare dati grezzi, eliminando il rischio di interpretazioni errate che possono sorgere quando i dati vengono trasmessi in forma narrativa.

6. **Riferimenti e citazioni**: quando le tabelle sono ben etichettate e correttamente referenziate, diventano preziosi punti di riferimento all'interno di un documento. Gli autori possono fare riferimento a tabelle specifiche quando discutono dei risultati, rendendo più facile per i lettori seguire l'argomento.

7. **Impegno visivo**: le tabelle ben progettate rompono la monotonia dei contenuti testuali, coinvolgono visivamente i lettori e aiutano a mantenerli interessati. Contribuiscono all'estetica generale e alla professionalità di un documento.

8. **Efficienza nella comunicazione**: Professionisti e ricercatori impegnati spesso devono estrarre rapidamente informazioni. Le tabelle consentono loro di visualizzare i dati e trovare dettagli specifici senza dover leggere i paragrafi del testo.

9. **Standardizzazione**: nella ricerca accademica, le tabelle standardizzate sono spesso utilizzate per presentare metodologie sperimentali, risultati e analisi statistiche. Ciò garantisce coerenza tra pubblicazioni e aiuti nella riproducibilità della ricerca.

In sostanza, le tabelle fungono da hub di informazioni, presentando in modo efficiente approfondimenti basati sui dati mantenendo un formato strutturato e adatto ai lettori. Il loro ruolo nel trasmettere dettagli intricati garantendo al contempo chiarezza e accessibilità li rende uno strumento indispensabile sia nella comunicazione accademica che professionale.

Passiamo ora al LaTeX come un potente sistema di composizione che consente agli autori di trasformare le loro idee in documenti meravigliosamente realizzati. Il LaTeX trascende i limiti dei tradizionali elaboratori di testi, offrendo un regno di precisione, eleganza e versatilità che è molto evidente durante l'elaborazione di strutture tabulari.
Alla base, LaTex è più di un semplice strumento di preparazione del documento; È una forma d'arte che combina la tipografia con la tecnologia. Che tu stia creando documenti accademici, report, presentazioni o persino libri, il LaTeX eccelle nella produzione di documenti che non sono solo esteticamente gradevoli, ma trasmettono anche informazioni con la massima chiarezza. La sua padronanza sta, tra le altre cose, nella sua perfetta integrazione di intricate strutture tabulari, che sono la spina dorsale della rappresentazione dei dati in vari campi.

Con il LaTeX, la disposizione delle informazioni all'interno delle tabelle va oltre una semplice griglia di righe e colonne. Invece, è una sinfonia accuratamente orchestrata in cui si armonizzano l'allineamento, la spaziatura e lo styling per fornire una raffinata presentazione dei dati. Le strutture tabulari in LaTeX diventano narrazioni visive, trasmette set di dati complessi, relazioni e confronti con eleganza e precisione.

Offrendo molti strumenti e pacchetti su misura per il design tabulare, il LaTeX trasforma i dati in narrazione visiva. Dal controllo della larghezza delle colonne alla regolazione dei bordi delle celle e dell'ombreggiatura, il livello di personalizzazione del LaTeX garantisce che ogni tabella si allinei perfettamente allo scopo del tuo documento. Per coloro che lavorano con contenuti matematici, tecnici o scientifici, l'inclusione senza soluzione di equazioni e simboli di LaTex eleva la comunicazione di idee complesse.

Tuttavia, il potere del LaTeX si estende oltre la semplice estetica. Introduce l'efficienza attraverso meccanismi di referenziazione incrociata, realizzando tabelle di riferimento navigational all'interno del tuo documento. Inoltre, i pacchetti del LaTeX consentono la creazione di layout complessi che abbracciano più righe o colonne, accomodando le presentazioni di dati più esigenti.

Più in profondità si approfondisci nel mondo del LaTeX, le caratteristiche più sfumate esplori; Le caratteristiche che rendono il LaTeX uno strumento indispensabile per scienziati, professionisti e ricercatori. Ti immergi nell'arte della progettazione di tabelle che catturano l'attenzione, presentano informazioni in modo persuasivo e contribuiscono all'impatto complessivo del tuo documento.


## 2. Nozioni di base sui tavoli in LaTeX

Il concetto fondamentale di tabelle in LaTeX ruota attorno all'ambiente `tabular", in cui si definiscono colonne, righe e il loro contenuto per organizzare e presentare i dati in un formato strutturato e visivamente piacevole.

La struttura di base di una tabella in LaTeX coinvolge i seguenti componenti:

1. **Inizia l'ambiente `tabular`**: per creare una tabella, racchiude il contenuto della tabella all'interno di un ambiente` tabular`. Questo ambiente specifica il layout e la struttura della tabella.

2. Specifiche della colonna: all'interno dell'ambiente `tabular`, si definisce il numero di colonne e il loro allineamento usando gli specificatori della colonna. Gli specificatori comuni includono `l` per` c` allineato a sinistra, per centrati e `r` per colonne allineate a destra. È inoltre possibile specificare quali colonne il LaTeX dovrebbe separarsi con le linee verticali e quali bordi esterni verticali dovrebbero essere disegnati.

3. **Contenuto di riga**: ogni riga della tabella viene creata specificando il contenuto per ogni cella all'interno della riga. Le celle sono separate dal simbolo `&` e ogni riga viene terminata con il comando `\\`.

4. **Linee orizzontali**: è possibile aggiungere linee orizzontali a righe separate, nonché bordi esterni orizzontali, usando il comando `\hline`. Ciò migliora la struttura visiva della tabella.

### Esempi semplici

Ecco un esempio di base di una tabella in LaTeX:

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}

```

In questo esempio, l'ambiente `tabular` viene utilizzato per creare una tabella con tre colonne, ciascuna centrata (`c`). Il risultato della composizione è mostrato di seguito:

<a href="/tex/images/java/tutorial/latex-tables-1.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-1.jpg)</a>

L'esempio seguente mostra come creare una tabella con colonne allineate a sinistra e a destra.

```tex
\begin{tabular}{|l r||}
  \hline
  Company & Income \\            \hline \hline
  Pinapple Computer & \$150M \\
  Megasoft & \$210M \\
  General Waters Ltd. & \$98M \\
  Alphamet & \$2117M \\           \hline
\end{tabular}
```

Il bordo esterno destro è fatto doppio, l'intestazione è anche separata dalla tabella da una doppia linea, non esiste una linea verticale che separa le colonne.

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

Puoi anche disegnare linee orizzontali che non vanno l'intero tavolo da sinistra a destra.

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

Qui, il comando `\cline {i-j}` dice a LaTex di trarre una riga dalla colonna I <up> th </up> alla colonna J <up> th </up>.

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![Esempio di output](latex-tables-3.jpg)</a>

Le colonne in una tabella possono avere una larghezza fissa, nel qual caso vengono chiamate colonne *paragrafo*. Per creare tali colonne, si utilizza lo specificatore `P` seguito dalla larghezza della colonna nelle parentesi graffe. Considera il seguente esempio:

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

Nota l'uso del comando `\newline`.

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

Con il pacchetto `Array` incluso, sono disponibili altre due opzioni per le colonne a larghezza fissa:` m {larghezza} ` - Come` p {larghezza} `, ma allinea verticalmente il contenuto della cella nel mezzo;
`b {larghezza}` - Come `p {larghezza}`, ma allinea verticalmente il contenuto della cella in basso.

Nel raro caso in cui una tabella deve essere inclusa nel testo di un paragrafo, è possibile specificare la posizione della tabella relativa alla linea di base della riga di testo allentata. A tal fine, si utilizza l'opzione `t`,` c` (impostazione predefinita) o `b` per allineare la linea di base in alto, al centro o alla parte inferiore del tavolo. Per esempio,

```tex
This is the text of the paragraph
\begin{tabular}[t]{|r|l|}     \hline
  9D5 & hexadecimal \\
  4725 & octal \\             \cline{2-2}
  1001 1101 0101 & binary \\  \hline \hline
  2517 & decimal \\           \hline
\end{tabular}
that include a table.
```

Qui diciamo al LaTeX che la linea di base dovrebbe allinearsi alla parte inferiore del tavolo.

<a href="/tex/java/latex-tables/latex-tables-5.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### Definizione di più colonne

Quando la tabella contiene colonne allineate identicamente, è possibile definirle tutte utilizzando la sintassi `*{num} {formato}`. Ciò è particolarmente utile quando la tabella ha molte colonne.

```tex
\begin{tabular}{l*{7}{c}r}
  Employee   & Sun & Mon & Tue & Wed & Thu & Fri & Sat & Total \\ \hline
  John Doe   &     &  x  &     &     &     &  x  &     &   2   \\
  Dean Jones &  x  &     &  x  &     &  x  &     &     &   3   \\
  Chris Cross&     &     &     &  x  &     &     &     &   1   \\
  Pete Brad  &     &     &     &     &     &     &  x  &   1
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-6.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-6.jpg)</a>

### Specifica della colonna usando `> {\ CommMand}` e `<{\ Command}`

Un altro modo per specificare le colonne è utilizzare `> {\ Command}` per i comandi eseguiti a destra * prima di * ogni elemento di colonna e `<{\ Command}` per i comandi eseguiti a destra * dopo * ogni elemento di colonna. Questo è disponibile quando si dispone del pacchetto `Array` incluso nel preambolo del documento. Nell'esempio seguente, utilizziamo questa sintassi per centrare ciascuna di due colonne e per digitare la prima in faccia in grassetto.

```tex
\begin{tabular}{>{\centering\textbf\bgroup}p{3.5cm}<{\egroup}>|{\centering}p{3.5cm} }
  History & Geometry
  \tabularnewline \hline
  Ancient & Elementary
  \tabularnewline
  Medieval & Affine 
  \tabularnewline
  Modern & Analytic
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. Personalizzazione del layout del tavolo

Nelle tabelle di LaTeX, la distanza di regolazione è fondamentale per garantire che la tabella appaia ben strutturata e visivamente accattivante. La spaziatura adeguata migliora la leggibilità e impedisce l'affollamento di contenuti. Ecco alcuni aspetti chiave della regolazione della spaziatura nelle tabelle in LaTeX:

### Spaziatura inter-colonna

Il LaTeX aggiunge automaticamente un po 'di spazio tra le colonne. Per regolare lo spazio inter-colonna, è possibile utilizzare il comando `\setLength {\ tabColsep} {value}` prima dell'ambiente tabulare. L'aumento del valore aumenta lo spazio tra le colonne. Il valore predefinito è `6pt '.

### Spaziatura inter-fila

Per aumentare lo spazio tra le righe, è possibile utilizzare il comando `\RenewCommand {\ Arraystretch} {Value}` prima dell'ambiente `tabular`. L'aumento del valore si allunga le righe, migliorando la spaziatura verticale del tavolo. Il valore predefinito è `1.0`.

È inoltre possibile specificare il salto dopo una riga utilizzando esplicitamente la colla dopo il terminator della linea.

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### Usando espressioni `@` e `!`

Avendo il pacchetto `Array` incluso nel preambolo del documento, è possibile specificare i separatori di colonne con i costrutti`@{...} `o`! {...} `.

In genere prendono un po 'di testo come argomento e, se aggiunti a una colonna, inseriscono automaticamente quel testo in ciascuna cella in quella colonna prima e/o dopo i dati effettivi per quella cella. Il comando `@{...}` sostituisce lo spazio inter-colonna con il contenuto specificato come argomento. Lasciando vuoto l'argomento, è possibile sopprimere gli spazi inter-colonna.

Prendiamo una tabella di base specificata dal seguente codice:

```tex
\begin{tabular}{|l|l|}
  \hline
  1.1 & 1.2 \\ \hline
  2.1 & 2.2 \\
  \hline
\end{tabular}
```

Variando la descrizione della colonna, otteniamo i seguenti risultati:

<a href="/tex/java/latex-tables/latex-tables-9.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-9.jpg)</a>

Per preservare la spaziatura iniziale, puoi usare `! {...}`.

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

Ed ecco un esempio di una colonna di numeri di punta mobile allineati al punto decimale:

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}

```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### Usando il pacchetto `dColumn`

È possibile centrare una colonna sul separatore decimale usando il pacchetto `dColumn`, che fornisce un nuovo specificatore di colonna per i numeri di punta mobile. Il modo semplice per utilizzare questo pacchetto è dimostrato nel seguente esempio:

```tex
\usepackage{dcolumn}
................................................
\newcolumntype{d}[1]{D{.}{\cdot}{#1} } %the argument for d specifies the maximum number of decimal places
\begin{tabular}{l r c d{1} }
  Left&Right&Center&\mathrm{Decimal}\\
  1&2&3&4\\
  11&22&33&44\\
  1.1&2.2&3.3&4.4\\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

Si noti che una colonna allineata a decimale è composta in modalità matematica, quindi l'uso di `\mathrm` per l'intestazione della colonna nell'esempio sopra. Inoltre, il testo in una colonna allineata decimale (ad esempio, l'intestazione) sarà allineato a destra prima del separatore decimale (supponendo che non vi sia separatore decimale nel testo). Sebbene ciò possa andare bene per il testo molto breve o le intestazioni di colonne numeriche, sembra ingombrante nell'esempio sopra. Una soluzione a questo è quella di utilizzare il comando `\multicolumn` descritto di seguito, specificando una singola colonna e il suo allineamento. Ad esempio, per centrare l'intestazione *decimale* sulla sua colonna nell'esempio sopra, la prima riga della tabella stessa sarebbe `sinistra e destra e centro & \ multicolumn {1} {c} {decimale} \\`.

## 4. Fusione di cellule

Una tabella leggermente più complessa può essere ottenuta unendo le celle in orizzontale e/o verticalmente.

### Celle che abbracciano più colonne

La forma generale del comando che rende una cella su più colonne è: `\multicolumn {num_cols} {alignment} {contenuti}`. Qui, `num_cols` è il numero di colonne da unire; `allineamento` è` l`, `c`,` r`, o, per avere un avvolgimento di testo, `p {larghezza}`. E `Content 'è i dati che si desidera inserire in quella cella.

Ecco il semplice esempio:

```tex
\begin{tabular}{|l|l|}
  \hline
  \multicolumn{2}{|c|}{Available currencies} \\
  \hline
  CNY & Chinese Yuan \\
  JPY & Japanese Yen \\
  GBP & Great Britain Pound \\
  USD & US Dollar \\
  CAD & Canadian Dollar \\
  EUR & Euro \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-13.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-13.jpg)</a>

### Celle che abbracciano più file

Per creare una cella per più righe, dovrai includere il pacchetto `Multirow`. Il pacchetto fornisce il seguente comando: `\multirow {num_rows} {width} {contenuti}`.

Qui, `num_rows` è il numero di righe da unire; `La larghezza` è la larghezza della cella (`*`per la larghezza naturale del contenuto) e` contenuto` è i dati effettivi da compensare nella cella.

```tex
\begin{tabular}{|l|l|l|}
  \hline
  \multicolumn{3}{ |c| }{Available currencies} \\
  \hline
  South America & BRL & Brazilian Real \\ \hline
  \multirow{3}{*}{Asia} & CNY & Chinese Yuan \\
   & JPY & Japanese Yen \\
   & HKD & Hong Kong Dollar \\ \hline
  \multirow{3}{*}{Europe} & EUR & Euro \\
   & GBP & Great Britain Pound \\
   & CHF & Swiss Franc \\ \hline
  Oceania & AUD & Australian Dollar \\ \hline
  \multirow{2}{*}{North America} & USD & US Dollar \\
   & CAD & Canadian Dollar \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-14.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-14.jpg)</a>

È necessario ricordare che quando si utilizza il comando `\multirow`, è necessario inserire una voce vuota per ogni cella appropriata in ciascuna riga successiva da attraversare.

### Cellule che attraversano entrambe le direzioni

L'esempio seguente dimostra come attraversare contemporaneamente le celle in entrambe le direzioni e ottenere i bordi correttamente:

```tex
\begin{tabular}{cc|c|c|c|c|l}
  \cline{3-6}
  & & \multicolumn{4}{ c| }{Primes} \\ \cline{3-6}
  & & 2 & 3 & 5 & 7 \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{504} & 3 & 2 & 0 & 1 & \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{540} & 2 & 3 & 1 & 0 & \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{gcd} & 2 & 2 & 0 & 0 & min \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{lcm} & 3 & 3 & 1 & 1 & max \\ \cline{1-6}
\end{tabular}
```

Il comando `\multicolumn {1} {` viene utilizzato per disegnare entrambi i bordi sinistro e destro verticali. Sebbene sia combinato con `\multirow {2} {*} {...}`, disegna ancora bordi verticali che abbracciano solo la prima riga. Per compensare questo, aggiungiamo `\multicolumn {1} {` nelle seguenti righe attraversate dal `mutltirow`.

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-15.jpg)</a>

## 5. Dimensione del tavolo

Il pacchetto `graphicx` fornisce il comando `\resizeBox {larghezza} {altezza} {oggetto} `che può essere usato con l'ambiente` tabular` per allungare o ridurre una tabella su una larghezza e altezza specificate. Nell'esempio seguente, stiamo ridimensionando la tabella alla larghezza di 12 cm mantenendo le proporzioni.

```tex
\resizebox{12cm}{!} {
  \begin{tabular}{|c|c|c|}                           \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
}
```

<a href="/tex/java/latex-tables/latex-tables-16.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-16.jpg)</a>

Puoi anche usare `\scalebox {rapporto} {oggetto}` allo stesso modo, ma con rapporti anziché dimensioni fisse:

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```

## 6. Tabelle di posizionamento

Puoi facilmente posizionare una tabella su una pagina se la posiziona all'interno di un ambiente `Table`.

```tex
\begin{table}[positioning_option]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

Le opzioni di posizionamento disponibili sono:

`H` - posizionerà il tavolo *qui* approssimativamente.

`T` - Posiziona la tabella nella *top* della pagina.

`B` - Posiziona la tabella nella *in basso* della pagina.

`P` - Metti la tabella in una pagina speciale (solo per le tabelle).

`!` - Sostituire i parametri interni in LaTeX.

`H` - Posiziona il tavolo in questa posizione precisa (praticamente come` h! `).

Per centrare una tabella in orizzontale, è possibile precedere l'ambiente `tabular` con il comando `\centratura`"all'interno di un ambiente Tabella '.

## 7. Didascalie, etichette e riferimenti
Puoi didascalia una tabella con un po 'di testo. Nell'output, il testo verrà prefisso con *Tabella N. *, dove *n*è il numero di tabella appropriato tracciato automaticamente da LaTeX. Per fare ciò, usa il comando `\didascalia`. È anche possibile assegnare un'etichetta a una tabella in modo che la tabella possa essere referenziata da qualsiasi luogo del documento. La coppia corrispondente di comandi è `\etichetta` e `\ref`. Considera il seguente esempio:

```tex
Table \ref{table:1} is an example of a referenced \LaTeX{} element.

\begin{table}[h!]
  \centering
  \begin{tabular}{|c|c|c|} \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
  \caption{A caption for the table.}
  \label{table:1}
\end{table}
```

Qui, il riferimento nella prima riga verrà automaticamente sostituito con il numero impostato dal comando `\label`.

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-17.jpg)</a>

## 8. Tabelle da colorare

### Modificare i colori nelle righe da tavolo

Il pacchetto `xcolor` fornisce i comandi necessari per produrre tabelle con colori di riga alternativi. Il pacchetto deve essere caricato con l'opzione tabella: `\usapackage {tabella] {xcolor}`.
Il comando `\RowColors {starting_row} {odd_color} {even_color}` deve verificarsi prima che inizi l'ambiente `tabular`.

```tex
\begin{center}
  \rowcolors{2}{green}{pink}

  \begin{tabular}{lll}
    \multicolumn{3}{c}{The header} \\
    odd & odd & odd \\
    even & even & even\\
    \hiderowcolors odd & odd & odd \\
    \showrowcolors even & even & even\\
     even & even & even\\
  \end{tabular}
\end{center}
```

Il comando `\hiderowcolors`, fornito dal pacchetto` xcolor`, disattiva l'evidenziazione a partire dalla riga che si verifica alla fine della tabella. Per riattivare l'evidenziazione, utilizzare il comando `\ShowrowColors`.

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### Colorare singole cellule

Con il pacchetto `xcolor`, puoi anche specificare il colore di una particolare cella.

```tex
\begin{tabular}{|l|l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  \cellcolor{red} odd & odd & odd \\
  \hline
  even & \cellcolor{red} even & even\\
  \hline
  odd & odd & \cellcolor{red} odd \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-19.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-19.jpg)</a>

### Utilizzando il pacchetto `colortbl`

Il pacchetto `Colortbl` fornisce il comando `\columncolor` per specificare il colore della colonna nel preambolo di un ambiente tabulare all'interno del costrutto `>{...}`. Ciò significa che devi anche avere il pacchetto `Array` incluso. (Non dimenticare di includere anche il pacchetto `xcolor`.)

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-20.jpg)</a>

Il comando `\RowColor` può essere utilizzato per specificare i colori della riga. Deve essere usato all'inizio della riga. Il comando ha la stessa sintassi di `\coloncolor`.

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

Puoi anche colorare le regole verticali. Per esempio, 

```tex
\setlength{\arrayrulewidth}{2pt}
\begin{tabular}{!{\color{blue}\vline} l !{\color{blue}\vline} l !{\color{blue}\vline}
    l !{\color{blue}\vline}}
  \multicolumn{3}{c}{The header} \\
  odd & odd & odd \\
  even & even & even\\
  odd & odd & odd \\
\end{tabular}
```

comporterà

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

Nota l'uso di `\setLength {\ ArrayruleWidth} {2pt}` per modificare lo spessore della regola.

Tuttavia, la colorazione di `\hline` e `\cline` è un po 'più complicata ed è disponibile con comandi extra (che si applicano anche alle regole verticali). Il comando `\arrayrulecolor 'può essere usato a livello globale o all'interno di una tabella. In entrambi i casi, influisce su tutte le regole successive. Pertanto, se si desidera un colore diverso per le regole verticali, è necessario specificarlo nel preambolo della tabella. Per esempio,

```tex
\setlength\arrayrulewidth{2pt}
%\arrayrulecolor{blue} % to set the color for all rules
\begin{tabular}{|l!{\color{green}\vline}l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  odd & odd & odd \\
  \arrayrulecolor{blue} \hline
  even & even & even\\
  \hline
  odd & odd & odd \\ \arrayrulecolor{red}
  \hline
\end{tabular}
```

comporterà

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-23.jpg)</a>

## 9. Costruire tavoli lunghi

L'ambiente "tabular" ha uno svantaggio significativo. Produce tabelle che non possono essere suddivise tra le pagine con l'algoritmo di rottura della pagina integrato del Tex. Pertanto, se la tabella è lunga, si diffonderà solo sotto la pagina in basso.

Fortunatamente, c'è il pacchetto `longtable`, oggi fornito nella maggior parte delle distribuzioni, che definisce l'ambiente` longtable` per la gestione di tabelle così lunghe. Per la maggior parte degli aspetti, questo ambiente funziona allo stesso modo dell'ambiente "tabulare". Ci sono alcune differenze, però.

Dimostreremo la maggior parte delle caratteristiche di "Longtable" nel seguente esempio, in cui puoi anche trovare note di utilizzo e differenze dall'ambiente "tabulari". (L'esempio utilizza anche il pacchetto `Verbatim` per una formattazione di testo, quindi deve anche essere incluso.)

```tex
\begin{longtable}{|r||p{1in}|}
  \caption[An optional table caption ...]{A long table\label{long}}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of the table}\\
  \textsc{First}&\textsc{Second}\\
  \hline\hline
  \endfirsthead % Everything above this command will appear at the beginning of the table, in the first page.

  \caption[]{(continued)}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of every other page}\\
  \textbf{First}&\textbf{Second}\\
  \hline\hline
  \endhead % Whatever you put before this command and below \endfirsthead will be displayed at the top of the table in every page except the first one.

  \hline
  This goes at the&bottom.\\
  \hline
  \endfoot % What you put after \endhead and before this command will appear at the bottom of the table in every page except the last one.

  \hline
  These lines will&appear\\
  in place of the & usual foot\\
  at the end& of the table\\
  \hline
  \endlastfoot % The elements after \endfoot and before this command will be displayed at the bottom of the table but only in the last page where the table appears.

  \texttt{longtable} columns are specified& in the \\
  same way as in the \texttt{tabular}& environment.\\
  \verb!|r||p{1in}|! & inthis case. \\
  Each row ends with a & \verb|\\| command. \\
  The \verb|\\| command has an & optional \\
  argument, just as in & the \\
  \texttt{tabular} & environment. \\ [10pt]
  See the effect of \verb|\\[10pt]| & ? \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Also \verb|\hline| may be used, & as in \texttt{tabular}. \\
  \hline
  That was a \verb|\hline| & . \\
  \hline\hline
  That was a \verb|\hline\hline| & . \\
  \multicolumn{2}{||c||}
    {This is a \texttt{\textbackslash multicolumn\{2\}\{||c||\}}} \\
  If a page break occurs at a \verb|\hline| then & a line is drawn \\
  at the bottom of one page and at the & top of the next. \\
  \hline
  The \texttt{[t] [b] [c]} argument of \texttt{tabular} & cannot be used. \\
  The optional argument may be one of & \texttt{[l] [r] [c]} \\
  to specify whether the table should be & adjusted \\
  to the left, right, & or centrally. \\
  \hline\hline
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Some lines may take up a lot of space, like this: &
  \raggedleft This last column is a ``p'' column so this ``row'' of the table can take
  up several lines. Note however that \TeX will never break a page within such a row.
  Page breaks only occur between rows of the table or at \verb|\hline| commands.
  \tabularnewline
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  \hline
  Lots of lines& like this.\\
  Lots of lines& like this.\\
\end{longtable}
```

Ciò comporterà due pagine:

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-24.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

Non essere confuso se non ottieni lo stesso risultato dopo la prima manche di Tex. A causa dei limiti tecnici di Tex, potrebbero essere necessarie alcune corse per ottenere il tavolo che vedi nelle immagini.

## 10. Un esempio di tabella complessa

Forniremo un altro esempio piuttosto complesso di una tabella che combina molte delle caratteristiche di cui sopra.

```tex
\documentclass{article}
  \usepackage{dcolumn}
  \usepackage{verbatim}
  \usepackage{colortbl}
  \usepackage[table]{xcolor}
  \usepackage{longtable}
\begin{document}
  \hbox{}\vspace{100pt} % To make the table break between pages

  \newcolumntype{A}{>{\color{white}\columncolor{red}[.5\tabcolsep]\raggedright}
    p{2cm}}
  \newcolumntype{B}{>{\columncolor{blue}[.5\tabcolsep]\color{yellow}\raggedright}
    p{3cm}}
  \newcolumntype{C}{>{\columncolor{yellow}[.5\tabcolsep]}D{.}{\cdot}{-1}}
  \newcolumntype{E}{>{\large\bfseries \columncolor{cyan}[.5\tabcolsep]}c}
  \newcolumntype{F}{>{\color{white} \columncolor{magenta}[.5\tabcolsep]}c}
  \newcolumntype{G}{>{\columncolor[gray]{0.8}[.5\tabcolsep][\tabcolsep]}l}
  \newcolumntype{H}{>{\columncolor[gray]{0.8}}l}
  \newcolumntype{I}{>{\columncolor[gray]{0.8}[\tabcolsep][.5\tabcolsep]}D{.}{\cdot}
    {-1}}
  \setlength\minrowclearance{2pt} %Before starting give a little space

  \begin{longtable}{ABC}
    \multicolumn{3}{E}{A long table example} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endfirsthead

    \multicolumn{3}{E}{A long table example (continued)} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endhead

    \multicolumn{3}{E}{Continued\ldots}
    \endfoot

    \multicolumn{3}{E}{The End}
    \endlastfoot

    P-column & and another one & 12.34 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6}\\
    Some long text in the first column & bbb & 1.2 \\
    aaa & and some long text in the second column & 1.345 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6} \\
    aaa&bbb & 1.345 \\
    Note that the colored rules in all columns stretch to accommodate large entries
      In one column. & bbb & 1.345 \\
    aaa & bbb & 100 \\
    aaa & Depending on your driver you may get unsightly gaps or lines
      where the `screens' used to produce different shapes interact
      badly. You may want to cause adjacent panels of the same color by
      specifying a larger overhang or by adding some negative space (in a
      \verb|\noalign| between rows. & 12.4 \\
    aaa & bbb & 45.3 \\
  \end{longtable}
\end{document}
```

Prima dell'ambiente `longtable`, definiamo i tipi di colonna con il comando `\newcolumntype` fornito dal pacchetto `dColumn`. All'interno degli argomenti, utilizziamo la notazione `>{...}` per definire i formati di colonna. Le definizioni della colonna, a loro volta, usano comandi che specificano colori, allineamento, caratteri e larghezze della colonna. L'ambiente "Longtable" è un'altra caratteristica impiegata. All'interno dell'ambiente, utilizziamo il comando `\multicolumn` per unire le celle in orizzontale insieme ai tipi di colonne precedentemente definiti.

Il risultato di tutti gli sforzi è sotto:

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-26.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-27.jpg)</a>

## 11. Best practice e suggerimenti

Le tabelle di composizione in LaTeX possono essere un compito sfumato, ma le seguenti migliori pratiche e suggerimenti possono aiutarti a creare tavoli chiari, esteticamente piacevoli e dall'aspetto professionale. Ecco alcune preziose migliori pratiche e suggerimenti per le tabelle di composizione in LaTeX:

1. **Usa intestazioni di colonna significative:**
   - Fornire intestazioni chiare e descrittive per ogni colonna per aiutare i lettori a comprendere il contenuto.
   
2. **Allinea i dati numerici nel punto decimale:**
   - Quando si presentano dati numerici, allineare i numeri alla virgola per una migliore leggibilità. A questo scopo, è possibile utilizzare il pacchetto `dcolumn`.
   
3. **Evita le viti verticali**:
   - Nelle pubblicazioni professionali, si consiglia spesso di evitare l'uso di linee verticali per separare le colonne. Utilizzare con parsimonia le linee orizzontali per maggiore chiarezza.

4. **Mantenere la coerenza:**
   - Mantieni una formattazione coerente in tutto il documento, inclusi i tipi di carattere, le dimensioni dei caratteri e l'allineamento nelle tabelle.
   
5. **Riduci al minimo il contenuto cellulare:**
   - Evita di sovraccaricare le celle con contenuti eccessivi. Se una cella contiene troppo testo, valuta la possibilità di suddividerla in più righe o colonne.
   
6. **Aggiungi didascalie ed etichette:**
   - Includi didascalie informative sopra o sotto le tabelle e usa il comando `\label` per abilitare i riferimenti incrociati all'interno del documento.

7. **impiega `multirow` e ` multicolumn`:**
    - Sebbene `multirow` e `multicolumn` siano utili per unire le celle, evitarne un uso eccessivo in quanto può rendere le tabelle complesse e difficili da leggere.

8. **Evita tabelle troppo complesse:**
    - Se i dati sono troppo complessi per una singola tabella, valuta la possibilità di suddividerli in più tabelle più piccole o di utilizzare altri supporti visivi come grafici o diagrammi.
    
9. **Usa lo spazio orizzontale pensieroso:**
    - Regola lo spazio tra le colonne usando `\setlength{\tabcolsep}{value}` e lo spazio tra le righe usando `\renewcommand{\arraystretch}{value}` per ottimizzare il layout della tabella.

10. **ROUND REGLIUNGI I TUOI TABLI:**
    - Rileggi attentamente e controlla eventuali errori nelle tue tabelle, inclusi l'accuratezza dei dati, la formattazione e l'allineamento.
    
Implementando queste migliori pratiche e suggerimenti, è possibile creare tabelle in LaTeX che non solo comunicano efficacemente i tuoi dati, ma migliorano anche la qualità generale e la professionalità dei tuoi documenti.

## 12. Conclusione

Abbiamo viaggiato attraverso l'intricato mondo di strutture da tavola in LaTeX, scoprendo la notevole versatilità e precisione che offre questo sistema di composizione. La capacità del LaTeX di integrare perfettamente le tabelle nei documenti consente agli utenti di comunicare dati, confronti e relazioni complesse con grazia e chiarezza.

Dai concetti fondamentali dell'ambiente `tabular` alle tecniche avanzate che coinvolgono pacchetti` multirow` e `longtable ', abbiamo esplorato gli strumenti e le strategie che rendono il LaTeX una potenza per la creazione di tabelle. Abbiamo imparato come il LaTeX non solo abbellisce le nostre tabelle, ma semplifica anche la presentazione dei dati, aiutando in una comunicazione efficace. 

Abbiamo sottolineato l'importanza delle migliori pratiche: intestazioni di colonne significative, allineamento, spaziatura adeguata e coerenza. Queste pratiche ci consentono di creare tabelle che non sono solo funzionali ma visivamente accattivanti e professionali.

Mentre continui a esplorare il LaTeX, ricorda che le strutture da tavola di mastering è un'arte tanto quanto una scienza. È un'abilità che può migliorare significativamente l'impatto dei tuoi documenti accademici, rapporti e presentazioni. 

Quindi, armato della conoscenza delle capacità del tavolo del LaTeX, porta i tuoi documenti al livello successivo. Sperimenta, perfeziona e innova nel regno delle strutture da tavola e lascia che il LaTeX sia il tuo compagno di fiducia nell'elaborazione di documenti che trasmettono informazioni efficacemente, magnificamente e professionalmente.