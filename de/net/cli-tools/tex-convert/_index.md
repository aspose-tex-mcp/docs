---
translation: true
template: /templates/_template-net.md
title: TeX-Befehlszeilenkonverter | Aspose.TeX CLI-Tools
linktitle: Aspose.TeX-Konvertierung
weight: 80
url: /net/cli-tools/tex-convert/
description: Leistungsstarkes Befehlszeilen-Konverter-Tool von Aspose.TeX zum einfachen und effizienten Konvertieren von TeX/LaTeX-Dokumenten. Aspose CLI TeX-Konverter.
keywords: Tex-zu-PDF-CLI-Konverter, Latex-zu-PDF-CLI-Konverter, Cli-Tex-Konverter
lastmod: "2026-04-03"
---

{{<section overview>}}

## Überblick

Das Tool [Aspose.TeX Convert](https://www.nuget.org/packages/Aspose.TeX.Convert) ist eine leistungsstarke CLI-Anwendung, die die Konvertierung von TeX- und LaTeX-Dokumenten in verschiedene Formate erleichtert. Mit diesem Tool können Entwickler und Designer Dokumente erstellen, die nahtlos auf verschiedenen Plattformen und Geräten funktionieren.

## Hauptmerkmale

- **Unterstützte Eingabeformate**: TeX, LaTeX.
- **Unterstützte Ausgabeformate**: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
- **Flexible Nutzung**: Kann sowohl über einfache Befehlszeilenbefehle als auch programmgesteuert in Ihrem C#-Code verwendet werden, kompatibel mit .NET 6.0/7.0.

## Vorteile

Die Verwendung des Aspose.TeX Convert-Tools bietet mehrere Vorteile:

- **Effizienz**: Konvertieren Sie TeX/LaTeX-Dokumente schnell in mehrere Formate, ohne dass komplexe Software erforderlich ist.
- **Automatisierung**: Integrieren Sie die Dokumentenkonvertierung in Ihre automatisierten Arbeitsabläufe und Skripte.
- **Flexibilität**: Verarbeiten Sie verschiedene Dokumentformate, um die Kompatibilität mit verschiedenen Systemen und Anwendungen sicherzustellen.

## Lizenzierung

Während die Nutzung der Aspose.TeX Convert-Anwendung selbst kostenlos ist, ist für die Konvertierung von Dokumenten eine gültige Aspose.TeX-[Lizenz](/tex/{{lang.url-fragment}}net/licensing/) erforderlich. Sie können eine Lizenz erwerben oder Aspose.TeX zu Testzwecken im Testmodus verwenden.

## Wie installiere ich den TeX-Befehlszeilenkonverter?

Das Aspose.TeX Convert-Tool kann je nach den Anforderungen Ihres Projekts entweder global oder lokal installiert werden. Zur Vermeidung von Versionskonflikten empfiehlt es sich, für den projektspezifischen Einsatz die lokale Installation zu nutzen.

### Globale Installation

Um Aspose.TeX Convert global auf Ihrem Computer zu installieren, verwenden Sie den folgenden Befehl:


```bash
dotnet tool install --global Aspose.TeX.Convert
```

Geben Sie die Option „--version“ an, wenn Sie eine bestimmte Version des Tools benötigen.

### Lokale Installation

Navigieren Sie für die lokale Installation innerhalb eines bestimmten Projekts zunächst zum Stammverzeichnis Ihres Projekts. Führen Sie dann die folgenden Befehle aus:

1. Erstellen Sie ein Tool-Manifest, falls noch nicht vorhanden:

   ```bash
   Dotnet neues Tool-Manifest
   ```

2. Installieren Sie Aspose.TeX Convert lokal:

   ```bash
   Dotnet-Tool installiert Aspose.TeX.Convert --local
   ```



Auch hier können Sie die Option „--version“ für eine bestimmte Version angeben.

### Aktualisieren des TeX CLI-Konverters

Um das Aspose.TeX Convert-Tool auf die neueste Version zu aktualisieren, verwenden Sie den Befehl „dotnet tool update“ mit entweder „--global“ oder „--local“, entsprechend Ihrem Installationstyp.

### Deinstallation des TeX CLI-Konverters

Wenn Sie das Tool deinstallieren müssen, verwenden Sie den Befehl „dotnet tool uninstall“ mit entweder „--global“ oder „--local“, je nachdem, wie das Tool installiert wurde.

## Verwendung

### Befehlszeile

Konvertieren Sie Ihre Dokumente mithilfe von Befehlszeilenargumenten. Hier sind die verfügbaren Parameter:

- `-i, --input [Erforderlich]`: Pfad zum Eingabe-TeX- oder LaTeX-Dokument.
  - Beispiel: `--input input.tex`
- `-o, --output [Erforderlich]`: Pfad für das konvertierte Dokument.
  - Beispiel: `--output ausgabe.pdf`
- `-f, --format [Optional]`: Ausgabedokumentformat.
  - Unterstützte Formate: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
  - Beispiel: „--format pdf“.
- `-l, --license [Optional]`: Pfad zur Aspose.TeX .NET-Lizenzdatei.
  - Beispiel: `--license path_to_license.lic`
- `-v, --verbose [Optional]`: Aktiviert die ausführliche Ausgabe.
  - Beispiel: „--verbose“.

Beispiel für die Verwendung einer Befehlszeile:


```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### Wie integriere ich den CLI-LaTeX-Konverter in C#-Projekte?

Die Aspose.TeX Convert-Anwendung kann über die Befehlszeile auch direkt in Ihre .NET-Projekte integriert werden und ermöglicht so den programmgesteuerten Zugriff auf TeX-Konvertierungsfunktionen in Ihrem C#-Code.
**Hinzufügen des LaTeX-Befehlszeilenkonverters zu Ihrem Projekt:**

Um das Aspose.TeX Convert-Tool zu Ihrem Visual Studio-Projekt hinzuzufügen, wechseln Sie in das Stammverzeichnis Ihres Projekts und führen Sie den folgenden Befehl aus:


```bash
dotnet Aspose.TeX.Convert add
```

Dieser Befehl fügt die Aspose.TeX Convert-Funktionalität direkt in Ihr Projekt ein, sodass Sie die Methoden und Eigenschaften der Bibliothek über Ihren Code verwenden können. Dies ist besonders nützlich für Entwickler, die benutzerdefinierte TeX-Konvertierungsprozesse direkt in ihren Anwendungen implementieren möchten.

### Aus Code verwenden

Hier ist ein Beispiel für die programmgesteuerte Verwendung der Aspose.TeX-CLI-Tools in Ihrem C#-Code:


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

Weitere Informationen und Anwendungsbeispiele finden Sie in der [Aspose.TeX for .NET-Dokumentation](/tex/{{lang.url-fragment}}net/).