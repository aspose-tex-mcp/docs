---
translation: true
template: /templates/_template-net.md
title: Convertitore della riga di comando tex | Aspose.TeX Strumenti CLI
linktitle: Aspose.TeX converti
weight: 80
url: /net/cli-tools/tex-convert/
description: Potente strumento di convertitore di comando da Aspose.TeX per convertire i documenti Tex/Latex in modo semplice ed efficiente. ASPUTI CLI TEX CONVERTER.
keywords: Convertitore CLI da Tex a PDF, convertitore CLI in LaTeX a PDF, CLI Tex Converter
lastmod: "2025-06-13"
---

{{<section overview>}}

## Panoramica

Lo strumento [Aspose.Tex Convert](https://www.nuget.org/packages/Aspose.TeX.Convert) è una potente applicazione CLI che facilita la conversione di documenti TEX e LaTeX in vari formati. Questo strumento consente a sviluppatori e designer di creare documenti che funzionano perfettamente su piattaforme e dispositivi diversi.

## Caratteristiche chiave

- **Formati di input supportati**: tex, LaTeX.
- **Formati di output supportati**: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
- **Utilizzo flessibile**: può essere utilizzato sia tramite comandi di riga di comando semplici sia a livello di programmazione nel codice C#, compatibile con .NET 6.0/7.0.

## Benefici

L'uso dello strumento Aspose.TeX Convert offre diversi vantaggi:

- **Efficienza**: convertire rapidamente i documenti TEX/Latex in più formati senza la necessità di software complessi.
- **Automation**: integrare la conversione dei documenti nei flussi di lavoro e script automatizzati.
- **Flessibilità**: gestire vari formati di documenti per garantire la compatibilità con diversi sistemi e applicazioni.

## Licenze

Mentre l'applicazione Aspose.TeX converti stessa è gratuita, la conversione dei documenti richiede un ASPUILE.Tex [licenza](/tex/{{lang.url-fragment}}net/licensing/) valido. È possibile acquistare una licenza o utilizzare Aspose.Tex in modalità di prova per scopi di valutazione.

## Come installare il convertitore di linea di comando TEX?

Lo strumento di convertire ASPOSE.TEX può essere installato a livello globale o localmente, a seconda delle esigenze del progetto. Si consiglia di utilizzare l'installazione locale per l'uso specifico del progetto per evitare i conflitti di versione.

### Installazione globale

Per installare Aspose.Tex Converti a livello globale sulla macchina, usa il comando seguente:


```bash
dotnet tool install --global Aspose.TeX.Convert
```

Specificare l'opzione `-Version` se hai bisogno di una versione specifica dello strumento.

### Installazione locale

Per l'installazione locale all'interno di un progetto specifico, in primo luogo, vai alla directory principale del progetto. Quindi, esegui i seguenti comandi:


1. Crea un strumento-manifesta se non già presente:

   ```bash
   dotnet new tool-manifest
   ```

2. Installa aspose.tex converti localmente:

   ```bash
   dotnet tool install Aspose.TeX.Convert --local
   ```

Ancora una volta, è possibile specificare l'opzione `-Version` per una versione specifica.

### Aggiornamento del convertitore CLI Tex

Per aggiornare lo strumento Aspose.TeX Convert all'ultima versione, utilizzare il comando `dotnet utensile `con` --global` o `--local`, corrispondente al tipo di installazione.

### Disinstallazione del convertitore CLI Tex

Se è necessario disinstallare lo strumento, utilizzare il comando `DotNet Strumento di disinstallazione` con `--global` o`--local`, a seconda di come è stato installato lo strumento.

## Utilizzo

### Riga di comando

Converti i documenti usando gli argomenti della riga di comando. Ecco i parametri disponibili:


- `-I,--Input [richiesto]`: percorso verso il documento input tex o LaTeX.
  - Example: `--input input.tex`
- `-o, --output [richiesto]`: percorso per il documento convertito.
  - Example: `--output output.pdf`
- `-f,-Format [opzionale]`: formato del documento di output.
  - Supported formats: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
  - Example: `--format pdf`
- `-L,-LICENSE [Opzionale]`: percorso verso il file di licenza Aspose.TeX .NET.
  - Example: `--license path_to_license.lic`
- `-v, -verbose [opzionale]`: abilita l'output verboso.
  - Example: `--verbose`

Esempio di utilizzo della linea di comando:


```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### Come integrare il convertitore CLI Latex in progetti C#?

L'applicazione Aspose.TeX Convert può anche essere integrata direttamente nei progetti .NET utilizzando la riga di comando, consentendo l'accesso programmatico alle funzionalità di conversione TEX all'interno del codice C#.

**Aggiunta del convertitore della riga di comando in LaTeX al progetto:**

Per aggiungere lo strumento Aspose.TeX Convert al tuo progetto Visual Studio, vai alla directory principale del progetto ed esegui il seguente comando:

```bash
dotnet Aspose.TeX.Convert add
```

Questo comando aggiunge la funzionalità Aspose.TeX Convert direttamente nel progetto, consentendo di utilizzare i metodi e le proprietà della libreria tramite il codice. Ciò è particolarmente utile per gli sviluppatori che desiderano implementare i processi di conversione TEX personalizzati direttamente all'interno delle loro applicazioni.

### Utilizzare dal codice

Ecco un esempio di utilizzo degli strumenti CLI Aspose.TeX a livello di programmazione nel codice C#:


```csharp
using Aspose.TeX.MicroApps.Convert;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        // Initialize convert options
        var options = new ConvertOptions
        {
            // Required: Specify the input document path
            InputDocument = "input.tex",
            
            // Required: Specify the output document path
            OutputFilePath = "output.pdf",
            
            // Optional: Specify the output format
            ToFormat = "pdf"
        };

        // Conditional: Apply license if you have one
        if (isLicensed)
        {
            options.LicenseFile = "path_to_license.lic";
        }

        // Execute the conversion task
        await ConvertTasks.Create(options).Execute();
    }
}
```

Per ulteriori informazioni e esempi di utilizzo, visitare la documentazione [Aspose.TeX per .NET](/tex/{{lang.url-fragment}}net/).