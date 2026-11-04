---
translation: true
template: /templates/_template-net.md
title: Fondamenti dell'uso di TikZ | Aspose.TeX .NET
linktitle: Fondamenti di TikZ
weight: 19
url: /net/tikz-fundamentals-of-using-tikz/
keywords: basi di tikz, fondamenti tikz, tutorial tikz
description: Esplora i principi fondamentali e i comandi di base di TikZ per creare grafiche per i tuoi documenti TeX e LaTeX.
lastmod: "2026-11-04"
---

{{<section overview>}}

In questo capitolo, esploreremo i principi e i comandi fondamentali di TikZ. Comprendere queste basi ti permetterà di creare grafiche chiare ed espressive per i tuoi documenti.

## Sistema di coordinate in TikZ

Le grafiche TikZ sono create utilizzando le coordinate. Le coordinate definiscono le posizioni all'interno dei tuoi disegni e possono essere specificate in diversi modi:

- **Coordinate cartesiane (x,y)**:

```tex
\documentclass{article}
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
    \draw (0,0) -- (2,2);
\end{tikzpicture}
\end{document}
```

- **Coordinate polari (angolo:raggio)**:

```tex
    \draw (0,0) -- (45:2);
```

Le coordinate possono essere combinate liberamente in un disegno per ottenere il risultato grafico desiderato.

*Una breve nota sugli scostamenti relativi (relative offsets):

- (0,0) -- ++(1,1) si sposta in (0,0), traccia una linea fino a (1,1) e imposta il nuovo punto corrente su (1,1).
- (0,0) -- +(1,1) traccia una linea fino a (1,1) rispetto a (0,0), ma lascia il punto corrente invariato in (0,0).*

## Disegnare forme semplici

TikZ consente di creare facilmente forme geometriche semplici:

- **Linee e polilinee**:


```tex
    \draw (0,0) -- (1,1) -- (2,0);
```

- **Rettangoli**:

```tex
    \draw (0,0) rectangle (2,1);
```

- **Cerchi ed ellissi**:

```tex
   \draw (1,1) circle (0.5);
    \draw (3,1) ellipse (1 and 0.5);
```

## Colori e modelli di riempimento

I colori e i riempimenti migliorano significativamente la chiarezza visiva. È possibile specificare i colori direttamente o utilizzare nomi predefiniti:

```tex
   \draw[red, thick] (0,0) rectangle (1,1);
   \draw[fill=blue!20] (2,0) circle (0.5);
```

La sintassi `blue!20` indica un colore blu con un'intensità del 20%.

## Stili e spessori delle linee

TikZ consente di modificare gli stili e lo spessore delle linee per migliorare la presentazione grafica:

- **Spessore della linea**:

```tex
   \draw[ultra thick] (0,0) -- (1,1);
   \draw[thin] (1,0) -- (2,1);
```

- **Linee tratteggiate e punteggiate**:

```tex
   \draw[dashed] (0,0) -- (2,2);
   \draw[dotted] (2,0) -- (4,2);
```

## Nodi ed etichette

I nodi consentono di aggiungere facilmente annotazioni testuali:

```tex
   \draw (0,0) -- (1,1) 
```

È possibile posizionare le etichette con precisione rispetto ai propri elementi grafici, migliorandone la leggibilità.

## Percorsi e curve

I percorsi TikZ possono essere linee rette o curve. Le curve vengono create utilizzando una sintassi semplice:

```tex
   \draw (0,0) .. controls (1,2) and (3,-1) .. (4,1);
```

I punti di controllo modellano la curvatura in modo intuitivo.

## Raggruppamento di elementi

Il raggruppamento di elementi grafici semplifica le trasformazioni (come il ridimensionamento e la rotazione):

```tex
\begin{scope}[rotate=45, scale=1.5]
  \draw (0,0) rectangle (1,1);
  \draw (1,1) circle (0.5);
\end{scope}
```

Gli elementi all'interno dello `scope` vengono ruotati e ridimensionati insieme, mantenendo l'allineamento.

---

La padronanza di questi concetti e comandi TikZ fondamentali fornirà una solida base per la creazione di grafiche sofisticate per i tuoi documenti.

## Esempio programmatico per l'elaborazione di disegni TikZ tramite Aspose.TeX

Di seguito viene proposta una guida dettagliata, corredata da un'implementazione del codice, che illustra come gli sviluppatori possano compilare un documento `.tex` contenente disegni TikZ, ottenendo direttamente un output vettoriale (PDF) ad alta fedeltà all'interno di un'applicazione .NET gestita.

```csharp
using System;
using System.IO;
using Aspose.TeX;
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;

namespace AsposeTexTikzDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Definisce le directory di input e di output
            string dataDir = @"C:\DocumentSamples\TikzInput";
            string outputDir = @"C:\DocumentSamples\TikzOutput";

            // Verifica che la directory di output esista
            Directory.CreateDirectory(outputDir);

            // Inizializza le opzioni TeX per un processo standard di elaborazione di documenti LaTeX
            // TeXConfig.ObjectLaTeX configura il motore con i pacchetti incorporati (inclusi tikz/pgf)
            TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
            options.InputWorkingDirectory = new InputFileSystemDirectory(dataDir);
            options.OutputWorkingDirectory = new OutputFileSystemDirectory(outputDir);

            // Imposta il nome del processo, usato per i file di output
            options.JobName = "tikz-fundamentals";

            // Configura le opzioni di salvataggio per il rendering diretto in formato PDF
            options.SaveOptions = new PdfSaveOptions();

            // Crea ed esegue il TeXJob con il file di origine, il dispositivo di output e le opzioni
            Console.WriteLine("Starting TikZ compilation job...");

            TeXJobResult result = new TeXJob(
                Path.Combine(dataDir, "tikz-fundamentals.tex"),
                new PdfDevice(),
                options
            ).Run();

            if (result < TeXJobResult.ErrorMessageIssued)
                Console.WriteLine($"TikZ graphic successfully compiled to PDF at: {outputDir}");
            else
                Console.WriteLine($"Compilation failed with {result}. See the .log file in {outputDir}.");
        }
    }
}
```

**Inoltre, scopri la nostra [applicazione web](https://products.aspose.app/tex/conversion/latex/) gratuita basata sull'[API Aspose.TeX per .NET](https://products.aspose.com/tex/net/) per conversioni TeX rapide e facili.**
