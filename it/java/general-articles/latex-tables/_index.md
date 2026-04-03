---
translation: true
template: /templates/_template-java.md
linktitle: Tabelle in LaTeX
title: Tabelle in LaTeX
weight: 50
url: /java/latex-tables/
keywords: tabelle LaTeX, ambiente tabular, design tabelle LaTeX, formattazione tabelle LaTeX, composizione tabelle LaTeX, layout tabelle LaTeX, spaziatura tabelle LaTeX, personalizzazione tabelle LaTeX, allineamento tabelle LaTeX, multirow e multicolumn tabelle LaTeX
description: Questo articolo è una guida rapida per la creazione di tabelle funzionali, leggibili, visivamente accattivanti e professionali in LaTeX.
lastmod: "2026-03-30"
---

{{<section overview>}}

## 1. Introduzione

Le tabelle svolgono un ruolo fondamentale nel migliorare la chiarezza, l'organizzazione e l'impatto visivo dei documenti accademici e professionali. Rappresentano un modo efficace per presentare dati complessi, confronti e relazioni in un formato strutturato e facilmente comprensibile. Ecco una breve panoramica della loro importanza:

1. **Sintesi dei dati**: le tabelle forniscono una rappresentazione sintetica di informazioni che altrimenti richiederebbero diversi paragrafi per essere spiegate. Consentono agli autori di presentare grandi quantità di dati in modo conciso, facilitando la comprensione dei punti chiave da parte dei lettori.

2. **Visualizzazione chiara**: i dati complessi, come cifre statistiche, risultati di sondaggi e scoperte sperimentali, possono essere presentati in modo più efficace utilizzando le tabelle. Il formato tabulare aiuta i lettori a identificare tendenze, modelli e valori anomali in modo molto più semplice.

3. **Analisi comparativa**: le tabelle consentono confronti affiancati di diversi set di dati. Che si tratti di confrontare specifiche di prodotti, prestazioni finanziarie o variabili di ricerca, le tabelle aiutano i lettori a trarre conclusioni significative a colpo d'occhio.

4. **Organizzazione logica**: le tabelle forniscono una struttura logica che suddivide i dati in righe e colonne. Questa organizzazione facilita la presentazione di dati suddivisi in categorie distinte, consentendo ai lettori di navigare e trovare facilmente informazioni specifiche.

5. **Integrità dei dati**: in contesti accademici e professionali, l'accuratezza dei dati è fondamentale. Le tabelle consentono agli autori di presentare dati grezzi, eliminando il rischio di interpretazioni errate che possono sorgere quando i dati vengono trasmessi in forma narrativa.

6. **Riferimenti e citazioni**: quando le tabelle sono ben etichettate e correttamente referenziate, diventano preziosi punti di riferimento all'interno di un documento. Gli autori possono fare riferimento a tabelle specifiche durante la discussione dei risultati, facilitando il compito del lettore nel seguire l'argomentazione.

7. **Impatto visivo**: tabelle ben progettate interrompono la monotonia del testo, coinvolgono visivamente i lettori e contribuiscono a mantenerne l'interesse. Migliorano l'estetica generale e la professionalità di un documento.

8. **Efficienza nella comunicazione**: i professionisti e i ricercatori hanno spesso la necessità di estrarre informazioni rapidamente. Le tabelle consentono di visualizzare i dati e trovare dettagli specifici senza dover leggere interi paragrafi di testo.

9. **Standardizzazione**: nella ricerca accademica, le tabelle standardizzate vengono spesso utilizzate per presentare metodologie sperimentali, risultati e analisi statistiche. Ciò garantisce coerenza tra le pubblicazioni e aiuta nella riproducibilità della ricerca.

In sostanza, le tabelle fungono da hub di informazioni, presentando in modo efficiente approfondimenti basati sui dati e mantenendo al contempo un formato strutturato e leggibile. Il loro ruolo nel trasmettere dettagli intricati garantendo chiarezza e accessibilità le rende uno strumento indispensabile sia nella comunicazione accademica che professionale.

Passiamo ora a LaTeX, un potente sistema di composizione tipografica che consente agli autori di trasformare le proprie idee in documenti realizzati in modo eccellente. LaTeX supera i limiti dei tradizionali elaboratori di testi, offrendo un livello di precisione, eleganza e versatilità che risulta chiaramente visibile durante la gestione delle strutture tabulari.

Fondamentalmente, LaTeX è molto più di un semplice strumento di preparazione dei documenti; è una forma d'arte che unisce la tipografia alla tecnologia. Che si tratti di articoli accademici, report, presentazioni o libri, LaTeX eccelle nella produzione di documenti che non sono solo esteticamente gradevoli, ma trasmettono anche informazioni con la massima chiarezza. La sua forza risiede, tra le altre cose, nella perfetta integrazione di complesse strutture tabulari, che rappresentano la spina dorsale della rappresentazione dei dati in vari campi.

Con LaTeX, la disposizione delle informazioni all'interno delle tabelle va oltre una semplice griglia di righe e colonne. Si tratta di una sinfonia accuratamente orchestrata in cui allineamento, spaziatura e stile si armonizzano per fornire una presentazione raffinata dei dati. Le strutture tabulari in LaTeX diventano narrazioni visive, che trasmettono set di dati complessi, relazioni e confronti con eleganza e precisione.

Offrendo numerosi strumenti e pacchetti su misura per il design tabulare, LaTeX trasforma i dati in narrazione visiva. Dal controllo della larghezza delle colonne alla regolazione dei bordi delle celle e delle ombreggiature, il livello di personalizzazione di LaTeX garantisce che ogni tabella si allinei perfettamente allo scopo del documento. Per chi lavora con contenuti matematici, tecnici o scientifici, l'inclusione fluida di equazioni e simboli all'interno delle celle eleva la comunicazione di idee complesse.

Inoltre, la potenza di LaTeX si estende oltre l'estetica. Introduce l'efficienza attraverso meccanismi di riferimenti incrociati, rendendo le tabelle punti di riferimento navigabili all'interno del documento. Inoltre, i pacchetti di LaTeX consentono la creazione di layout complessi che si estendono su più righe o colonne, gestendo le presentazioni di dati più esigenti.

Più approfondisci il mondo di LaTeX, più scopri caratteristiche sfumate che lo rendono uno strumento indispensabile per scienziati, professionisti e ricercatori. Ti immergerai nell'arte di progettare tabelle che catturano l'attenzione, presentano informazioni in modo persuasivo e contribuiscono all'impatto complessivo del tuo documento.


## 2. Nozioni di base sulle tabelle in LaTeX

Il concetto fondamentale delle tabelle in LaTeX ruota attorno all'ambiente `tabular`, in cui si definiscono colonne, righe e il loro contenuto per organizzare e presentare i dati in un formato strutturato e visivamente gradevole.

La struttura di base di una tabella in LaTeX coinvolge i seguenti componenti:

1. **Inizio dell'ambiente `tabular`**: per creare una tabella, si racchiude il contenuto all'interno di un ambiente `tabular`. Questo ambiente specifica il layout e la struttura della tabella.

2. **Specifiche di colonna**: all'interno dell'ambiente `tabular`, si definisce il numero di colonne e il loro allineamento utilizzando gli specificatori di colonna. Gli specificatori comuni includono `l` per l'allineamento a sinistra, `c` per il centraggio e `r` per l'allineamento a destra. È inoltre possibile specificare quali colonne separare con linee verticali e quali bordi esterni verticali devono essere tracciati.

3. **Contenuto di riga**: ogni riga della tabella viene creata specificando il contenuto per ogni cella all'interno della riga. Le celle sono separate dal simbolo `&` e ogni riga viene terminata dal comando `\\`.

4. **Linee orizzontali**: è possibile aggiungere linee orizzontali per separare le righe, nonché bordi esterni orizzontali, utilizzando il comando `\hline`. Ciò migliora la struttura visiva della tabella.

### Esempi semplici

Ecco un esempio di base di una tabella in LaTeX:

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}
```

In questo esempio, l'ambiente `tabular` viene utilizzato per creare una tabella con tre colonne, ciascuna centrata (`c`). Il risultato della composizione tipografica è mostrato di seguito:

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

Il bordo esterno destro è doppio, l'intestazione è separata dalla tabella da una doppia linea e non ci sono linee verticali che separano le colonne.

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

È anche possibile tracciare linee orizzontali che non coprono l'intera tabella da sinistra a destra.

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

In questo caso, il comando `\cline{i-j}` indica a LaTeX di tracciare una linea dalla colonna i-esima alla colonna j-esima.

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![Esempio di output](latex-tables-3.jpg)</a>

Le colonne di una tabella possono avere una larghezza fissa, nel qual caso sono chiamate colonne *paragrafo*. Per creare tali colonne, si utilizza lo specificatore `p` seguito dalla larghezza della colonna tra parentesi graffe. Considerate il seguente esempio:

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

Si noti l'uso del comando `\newline`.

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

Con il pacchetto `array` incluso, sono disponibili altre due opzioni per le colonne a larghezza fissa:
`m{larghezza}` - come `p{larghezza}`, ma allinea verticalmente il contenuto della cella al centro;
`b{larghezza}` - come `p{larghezza}`, ma allinea verticalmente il contenuto della cella in basso.

Nel raro caso in cui una tabella debba essere inclusa nel testo di un paragrafo, è possibile specificare la posizione della tabella rispetto alla linea di base della riga di testo circostante. A tale scopo, si utilizzano le opzioni `t`, `c` (predefinita) o `b` per allineare la linea di base alla parte superiore, centrale o inferiore della tabella. Per esempio:

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

In questo caso indichiamo a LaTeX che la linea di base deve allinearsi alla parte inferiore della tabella.

<a href="/tex/images/java/tutorial/latex-tables-5.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### Definizione di più colonne

Quando la tabella contiene colonne allineate in modo identico, è possibile definirle tutte insieme utilizzando la sintassi `*{num}{formato}`. Questo risulta particolarmente utile quando la tabella ha molte colonne.

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

### Specifica di colonna tramite `>{\comando}` e `<{\comando}`

Un altro modo per specificare le colonne consiste nell'utilizzare `>{\comando}` per i comandi eseguiti appena *prima* di ogni elemento della colonna e `<{\comando}` per i comandi eseguiti appena *dopo* ogni elemento della colonna. Questa opzione è disponibile quando il pacchetto `array` è incluso nel preambolo del documento. Nell'esempio seguente, utilizziamo questa sintassi per centrare ciascuna delle due colonne e per scrivere la prima in grassetto.

```tex
\begin{tabular}{>{\centering\textbf\bgroup}p{3.5cm}<{\egroup}>|{\centering}p{3.5cm} }
  History & Geometry
  \tabularnewline \hline
  Ancient & Elementary
  \tabularnewline
  Medieval & Affine 
  \tabularnewline
  Modern & Analytic
  \tabularnewline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. Personalizzazione del layout della tabella

Nelle tabelle LaTeX, la regolazione della spaziatura è fondamentale per garantire che la tabella appaia ben strutturata e visivamente accattivante. Una spaziatura adeguata migliora la leggibilità e impedisce l'affollamento dei contenuti. Ecco alcuni aspetti chiave della regolazione della spaziatura nelle tabelle LaTeX:

### Spaziatura inter-colonna

LaTeX aggiunge automaticamente un po' di spazio tra le colonne. Per regolare lo spazio inter-colonna, è possibile utilizzare il comando `\setlength{\tabcolsep}{valore}` prima dell'ambiente tabulare. L'aumento del valore incrementa lo spazio tra le colonne. Il valore predefinito è `6pt`.

### Spaziatura inter-riga

Per aumentare lo spazio tra le righe, è possibile utilizzare il comando `\renewcommand{\arraystretch}{valore}` prima dell'ambiente `tabular`. L'aumento del valore allontana le righe tra loro, migliorando la spaziatura verticale della tabella. Il valore predefinito è `1.0`.

È inoltre possibile specificare esplicitamente un salto dopo una riga utilizzando dello spazio (glue) dopo il terminatore di riga.

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### Utilizzo delle espressioni `@` e `!`

Includendo il pacchetto `array` nel preambolo del documento, è possibile specificare i separatori di colonna con i costrutti `@{...}` o `!{...}`.

Questi costrutti solitamente accettano del testo come argomento e, quando aggiunti a una colonna, inseriscono automaticamente tale testo in ogni cella della colonna prima e/o dopo i dati effettivi. Il comando `@{...}` sostituisce lo spazio inter-colonna con il contenuto specificato come argomento. Lasciando l'argomento vuoto, è possibile eliminare gli spazi inter-colonna.

Consideriamo una tabella di base definita dal seguente codice:

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

Per preservare la spaziatura iniziale, è possibile utilizzare `!{...}`.

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

Ed ecco un esempio di una colonna di numeri in virgola mobile allineati al punto decimale:

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### Utilizzo del pacchetto `dcolumn`

È possibile centrare una colonna sul separatore decimale utilizzando il pacchetto `dcolumn`, che fornisce un nuovo specificatore di colonna per i numeri in virgola mobile. Un modo semplice per utilizzare questo pacchetto è illustrato nel seguente esempio:

```tex
\usepackage{dcolumn}
................................................
\newcolumntype{d}[1]{D{.}{\cdot}{#1} } %l'argomento per d specifica il numero massimo di cifre decimali
\begin{tabular}{l r c d{1} }
  Left&Right&Center&\mathrm{Decimal}\\
  1&2&3&4\\
  11&22&33&44\\
  1.1&2.2&3.3&4.4\\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

Si noti che una colonna allineata al punto decimale viene composta in modalità matematica, da qui l'uso di `\mathrm` per l'intestazione della colonna nell'esempio precedente. Inoltre, il testo in una colonna allineata al punto decimale (ad esempio, l'intestazione) sarà allineato a destra prima del separatore decimale (supponendo che non vi sia alcun separatore decimale nel testo). Sebbene ciò possa andare bene per testi brevi o intestazioni di colonne numeriche, appare sgradevole nell'esempio sopra. Una soluzione consiste nell'utilizzare il comando `\multicolumn` descritto di seguito, specificando una singola colonna e il suo allineamento. Ad esempio, per centrare l'intestazione *Decimal* sulla sua colonna nell'esempio precedente, la prima riga della tabella sarebbe `Left&Right&Center&\multicolumn{1}{c}{Decimal}\\`.


## 4. Unione di celle

È possibile ottenere una tabella leggermente più complessa unendo le celle in orizzontale e/o in verticale.

### Celle che spaziano su più colonne

La forma generale del comando che permette a una cella di estendersi su più colonne è: `\multicolumn{num_cols}{allineamento}{contenuto}`. Qui, `num_cols` è il numero di colonne da unire; `allineamento` può essere `l`, `c`, `r` o, per avere il wrapping del testo, `p{larghezza}`. E `contenuto` è il dato che si desidera inserire nella cella.

Ecco un esempio semplice:

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

### Celle che spaziano su più righe

Per far sì che una cella si estenda su più righe, sarà necessario includere il pacchetto `multirow`. Il pacchetto fornisce il seguente comando: `\multirow{num_rows}{larghezza}{contenuto}`.

Qui, `num_rows` è il numero di righe da unire; `larghezza` è la larghezza della cella (`*` per la larghezza naturale del contenuto) e `contenuto` è il dato effettivo da comporre nella cella.

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

È importante ricordare che, quando si utilizza il comando `\multirow`, è necessario inserire una voce vuota per ogni cella corrispondente in ciascuna riga successiva interessata dall'unione.

### Unione di celle in entrambe le direzioni

L'esempio seguente mostra come unire celle in entrambe le direzioni contemporaneamente e tracciare correttamente i bordi:

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

Il comando `\multicolumn{1}{` viene utilizzato per tracciare sia il bordo verticale sinistro che quello destro. Sebbene sia combinato con `\multirow{2}{*}{...}`, traccia comunque bordi verticali che coprono solo la prima riga. Per compensare questo, aggiungiamo `\multicolumn{1}{` nelle righe successive interessate dal `multirow`.

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-15.jpg)</a>


## 5. Dimensioni della tabella

Il pacchetto `graphicx` fornisce il comando `\resizebox{larghezza}{altezza}{oggetto}` che può essere utilizzato con l'ambiente `tabular` per allargare o ridurre una tabella a una larghezza e altezza specifiche. Nell'esempio seguente, ridimensioniamo la tabella a una larghezza di 12 cm mantenendo le proporzioni.

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

È anche possibile utilizzare `\scalebox{rapporto}{oggetto}` nello stesso modo, ma impostando dei rapporti invece di dimensioni fisse:

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```


## 6. Posizionamento delle tabelle

È possibile posizionare facilmente una tabella all'interno di una pagina inserendola in un ambiente `table`.

```tex
\begin{table}[opzione_posizionamento]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

Le opzioni di posizionamento disponibili sono:

`h` - posizionerà la tabella approssimativamente *qui* (here).

`t` - posiziona la tabella nella parte *superiore* (top) della pagina.

`b` - posiziona la tabella nella parte *inferiore* (bottom) della pagina.

`p` - mette la tabella in una pagina speciale (solo per le tabelle).

`!` - forza il superamento dei parametri interni di LaTeX.

`H` - posiziona la tabella in questa posizione precisa (analogamente a `h!`).

Per centrare una tabella orizzontalmente, è possibile far precedere l'ambiente `tabular` dal comando `\centering` all'interno di un ambiente `table`.


## 7. Didascalie, etichette e riferimenti

È possibile aggiungere una didascalia a una tabella con un breve testo. Nell'output, il testo sarà preceduto da *Tabella N.*, dove *N* è il numero della tabella calcolato automaticamente da LaTeX. A tale scopo, si utilizza il comando `\caption`. È inoltre possibile assegnare un'etichetta a una tabella in modo che essa possa essere citata da qualsiasi punto del documento. La coppia di comandi corrispondente è `\label` e `\ref`. Considerate il seguente esempio:

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

In questo caso, il riferimento nella prima riga sarà sostituito automaticamente dal numero impostato dal comando `\label`.

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-17.jpg)</a>


## 8. Colorazione delle tabelle

### Alternanza di colori nelle righe della tabella

Il pacchetto `xcolor` fornisce i comandi necessari per produrre tabelle con colori di riga alternati. Il pacchetto deve essere caricato con l'opzione `table`: `\usepackage[table]{xcolor}`.
Il comando `\rowcolors{riga_iniziale}{colore_dispari}{colore_pari}` deve apparire prima dell'inizio dell'ambiente `tabular`.

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

Il comando `\hiderowcolors`, fornito dal pacchetto `xcolor`, disattiva l'evidenziazione a partire dalla riga in cui viene inserito fino alla fine della tabella. Per riattivarla, si usa il comando `\showrowcolors`.

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### Colorazione di singole celle

Con il pacchetto `xcolor` è anche possibile specificare il colore di una particolare cella.

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

### Utilizzo del pacchetto `colortbl`

Il pacchetto `colortbl` fornisce il comando `\columncolor` per specificare il colore di una colonna nel preambolo di un ambiente tabulare all'interno del costrutto `>{...}`. Ciò significa che è necessario includere anche il pacchetto `array`. (Non dimenticate di includere anche il pacchetto `xcolor`).

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-20.jpg)</a>

Il comando `\rowcolor` può essere utilizzato per specificare i colori di una riga. Deve essere inserito all'inizio della riga stessa. Il comando ha la stessa sintassi di `\columncolor`.

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

È possibile colorare anche le linee verticali. Per esempio:

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

produrrà:

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

Si noti l'uso di `\setlength{\arrayrulewidth}{2pt}` per modificare lo spessore delle linee.

Tuttavia, colorare `\hline` e `\cline` è un po' più complesso ed è possibile tramite comandi aggiuntivi (che si applicano anche alle linee verticali). Il comando `\arrayrulecolor` può essere utilizzato a livello globale o all'interno di una tabella. In entrambi i casi, influisce su tutte le linee successive. Pertanto, se si desidera un colore diverso per le linee verticali, è necessario specificarlo nel preambolo della tabella. Per esempio:

```tex
\setlength\arrayrulewidth{2pt}
%\arrayrulecolor{blue} % per impostare il colore per tutte le linee
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

produrrà:

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-23.jpg)</a>


## 9. Creazione di tabelle lunghe

L'ambiente `tabular` presenta uno svantaggio significativo: produce tabelle che non possono essere suddivise tra più pagine dall'algoritmo integrato di TeX per l'interruzione di pagina. Pertanto, se la tabella è molto lunga, supererà semplicemente il bordo inferiore della pagina.

Fortunatamente, esiste il pacchetto `longtable`, ormai presente nella maggior parte delle distribuzioni, che definisce l'ambiente `longtable` per la gestione di tabelle di questo tipo. Per molti versi, questo ambiente funziona in modo simile a `tabular`, ma con alcune differenze.

Presenteremo la maggior parte delle funzionalità di `longtable` nell'esempio seguente, in cui troverete anche note sull'uso e differenze rispetto all'ambiente `tabular`. (L'esempio utilizza anche il pacchetto `verbatim` per la formattazione di alcuni testi, che deve quindi essere incluso).

```tex
\begin{longtable}{|r||p{1in}|}
  \caption[An optional table caption ...]{A long table\label{long}}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of the table}\\
  \textsc{First}&\textsc{Second}\\
  \hline\hline
  \endfirsthead % Tutto ciò che precede questo comando apparirà all'inizio della tabella, nella prima pagina.

  \caption[]{(continued)}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of every other page}\\
  \textbf{First}&\textbf{Second}\\
  \hline\hline
  \endhead % Tutto ciò che si inserisce prima di questo comando e sotto \endfirsthead sarà visualizzato in cima alla tabella in ogni pagina tranne la prima.

  \hline
  This goes at the&bottom.\\
  \hline
  \endfoot % Ciò che si inserisce dopo \endhead e prima di questo comando apparirà in fondo alla tabella in ogni pagina tranne l'ultima.

  \hline
  These lines will&appear\\
  in place of the & usual foot\\
  at the end& of the table\\
  \hline
  \endlastfoot % Gli elementi dopo \endfoot e prima di questo comando saranno visualizzati in fondo alla tabella ma solo nell'ultima pagina in cui la tabella appare.

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
  \bold{This is a \texttt{\textbackslash multicolumn\{2\}\{||c||\}}} & \\
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

Il risultato si estenderà su due pagine:

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-24.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

Non preoccupatevi se non ottenete lo stesso risultato dopo la prima esecuzione di TeX. A causa delle limitazioni tecniche di TeX, potrebbero essere necessarie diverse esecuzioni per ottenere la tabella visualizzata nelle immagini.


## 10. Un esempio di tabella complessa

Forniamo un altro esempio piuttosto complesso di una tabella che combina molte delle caratteristiche sopra descritte.

```tex
\documentclass{article}
  \usepackage{dcolumn}
  \usepackage{verbatim}
  \usepackage{colortbl}
  \usepackage[table]{xcolor}
  \usepackage{longtable}
\begin{document}
  \hbox{}\vspace{100pt} % Per forzare l'interruzione della tabella tra le pagine

  \newcolumntype{A}{>{\color{white}\columncolor{red}[.5\tabcolsep]\raggedright}
    p{2cm}}
  \newcolumntype{B}{>{\columncolor{blue}[.5\tabcolsep]\color{yellow}\raggedright}
    p{3cm}}
  \newcolumntype{C}{>{\columncolor{yellow}[.5\tabcolsep]}D{.}{\cdot}{-1}}
  \newcolumntype{E}{>{\large\bfseries \columncolor{cyan}[.5\tabcolsep]}c}
  \newcolumntype{F}{>{\color{white} \columncolor{magenta}[.5\tabcolsep]}c}
  \newcolumntype{G}{>{\columncolor[gray]{0.8}[.5\tabcolsep]\tabcolsep}l}
  \newcolumntype{H}{>{\columncolor[gray]{0.8}}l}
  \newcolumntype{I}{>{\columncolor[gray]{0.8}[\tabcolsep][.5\tabcolsep]}D{.}{\cdot}
    {-1}}
  \setlength\minrowclearance{2pt} % Prima di iniziare, diamo un po' di spazio

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

Prima dell'ambiente `longtable`, definiamo i tipi di colonna con il comando `\newcolumntype` fornito dal pacchetto `dcolumn`. All'interno degli argomenti, utilizziamo la notazione `>{...}` per definire i formati delle colonne. Le definizioni delle colonne, a loro volta, utilizzano comandi che specificano colori, allineamento, font e larghezze di colonna. Viene inoltre impiegato l'ambiente `longtable`. All'interno dell'ambiente, utilizziamo il comando `\multicolumn` per unire le celle in orizzontale insieme ai tipi di colonna precedentemente definiti.

Il risultato di questo lavoro è mostrato qui sotto:

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-26.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-tables-27.jpg)</a>


## 11. Best practice e suggerimenti

La composizione delle tabelle in LaTeX può essere un compito complesso, ma seguire le migliori pratiche e i suggerimenti riportati di seguito può aiutare a creare tabelle chiare, esteticamente gradevoli e dall'aspetto professionale. Ecco alcuni preziosi suggerimenti per la composizione delle tabelle in LaTeX:

1. **Utilizzare intestazioni di colonna significative**:
   - Fornite intestazioni chiare e descrittive per ogni colonna per aiutare i lettori a comprendere il contenuto.
   
2. **Allineare i dati numerici al punto decimale**:
   - Quando presentate dati numerici, allineate i numeri alla virgola per una migliore leggibilità. A tale scopo è possibile utilizzare il pacchetto `dcolumn`.
   
3. **Evitare le linee verticali**:
   - Nelle pubblicazioni professionali, si consiglia spesso di evitare l'uso di linee verticali per separare le colonne. Utilizzate con parsimonia le linee orizzontali per favorire la chiarezza.

4. **Mantenere la coerenza**:
   - Mantenete una formattazione coerente in tutto il documento, inclusi font, dimensioni dei caratteri e allineamento all'interno delle tabelle.
   
5. **Ridurre al minimo il contenuto delle celle**:
   - Evitate di sovraccaricare le celle con troppi contenuti. Se una cella contiene troppo testo, valutate la possibilità di suddividerla in più righe o colonne.
   
6. **Aggiungere didascalie ed etichette**:
   - Includete didascalie informative sopra o sotto le tabelle e utilizzate il comando `\label` per abilitare i riferimenti incrociati all'interno del documento.

7. **Utilizzare `multirow` e `multicolumn` con parsimonia**:
    - Sebbene `multirow` e `multicolumn` siano utili per unire le celle, evitate un uso eccessivo perché può rendere le tabelle complesse e difficili da leggere.

8. **Evitare tabelle troppo complesse**:
    - Se i dati sono troppo complessi per una singola tabella, valutate la possibilità di suddividerli in più tabelle più piccole o di utilizzare altri supporti visivi come grafici o diagrammi.
    
9. **Utilizzare lo spazio orizzontale in modo ponderato**:
    - Regolate lo spazio tra le colonne usando `\setlength{\tabcolsep}{valore}` e lo spazio tra le righe usando `\renewcommand{\arraystretch}{valore}` per ottimizzare il layout delle tabelle.

10. **Rileggere le tabelle**:
    - Rileggete attentamente e controllate eventuali errori nelle tabelle, inclusi l'accuratezza dei dati, la formattazione e l'allineamento.

Seguendo queste migliori pratiche e suggerimenti, è possibile creare tabelle in LaTeX che non solo comunicano efficacemente i dati, ma migliorano anche la qualità generale e la professionalità dei documenti.


## 12. Conclusione

Abbiamo viaggiato attraverso l'intricato mondo delle strutture tabulari in LaTeX, scoprendo la notevole versatilità e precisione che questo sistema di composizione tipografica offre. La capacità di LaTeX di integrare perfettamente le tabelle nei documenti consente agli utenti di comunicare dati complessi, confronti e relazioni con eleganza e chiarezza.

Dai concetti fondamentali dell'ambiente `tabular` alle tecniche avanzate che coinvolgono i pacchetti `multirow` e `longtable`, abbiamo esplorato gli strumenti e le strategie che rendono LaTeX una potenza per la creazione di tabelle. Abbiamo imparato come LaTeX non solo abbellisca le tabelle, ma ne semplifichi anche la presentazione, favorendo una comunicazione efficace. 

Abbiamo sottolineato l'importanza delle migliori pratiche: intestazioni di colonna significative, allineamento, spaziatura adeguata e coerenza. Queste pratiche ci consentono di creare tabelle che non sono solo funzionali, ma anche visivamente accattivanti e professionali.

Mentre continui a esplorare LaTeX, ricorda che padroneggiare le strutture tabulari è un'arte tanto quanto una scienza. È un'abilità che può migliorare significativamente l'impatto dei tuoi articoli accademici, report e presentazioni. 

Quindi, armato della conoscenza delle capacità tabulari di LaTeX, porta i tuoi documenti al livello successivo. Sperimenta, perfeziona e innova nel regno delle strutture tabulari, e lascia che LaTeX sia il tuo fidato compagno nella creazione di documenti che trasmettano informazioni in modo efficace, splendido e professionale.