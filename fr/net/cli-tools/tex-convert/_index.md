---
translation: true
template: /templates/_template-net.md
title: Convertisseur de ligne de commande TeX | CLI Aspose.TeX
linktitle: Aspose.TeX Convertir
weight: 80
url: /net/cli-tools/tex-convert/
description: De conversion en ligne de commande d'Aspose.TeX pour convertir des documents TeX/LaTeX facilement et efficacement. Asposez le convertisseur CLI TeX.
keywords: Convertisseur cli tex en pdf, convertisseur cli latex en pdf, convertisseur cli tex
lastmod: "2026-04-03"
---

{{<section overview>}}

## Aperçu

L'outil [Aspose.TeX Convert](https://www.nuget.org/packages/Aspose.TeX.Convert) est une puissante application CLI qui facilite la conversion de documents TeX et LaTeX dans différents formats. Cet outil permet aux développeurs et aux concepteurs de créer des documents qui fonctionnent de manière transparente sur différentes plates-formes et appareils.

## Principales fonctionnalités

- **Formats d'entrée pris en charge** : TeX, LaTeX.
- **Formats de sortie pris en charge** : PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
- **Utilisation flexible** : peut être utilisé à la fois via de simples commandes de ligne de commande et par programme dans votre code C#, compatible avec .NET 6.0/7.0.

## Avantages

L'utilisation de l'outil Aspose.TeX Convert offre plusieurs avantages :

- **Efficacité** : convertissez rapidement des documents TeX/LaTeX en plusieurs formats sans avoir besoin d'un logiciel complexe.
- **Automation** : intégrez la conversion de documents dans vos flux de travail et scripts automatisés.
- **Flexibilité** : Gérez différents formats de documents pour garantir la compatibilité avec différents systèmes et applications.

## Licence

Bien que l'application Aspose.TeX Convert elle-même soit gratuite, la conversion de documents nécessite une [licence](/tex/{{lang.url-fragment}}net/licensing/) Aspose.TeX valide. Vous pouvez acheter une licence ou utiliser Aspose.TeX en mode d'essai à des fins d'évaluation.

## Comment installer le convertisseur de ligne de commande TeX ?

L'outil Aspose.TeX Convert peut être installé globalement ou localement, en fonction des besoins de votre projet. Il est recommandé d'utiliser l'installation locale pour une utilisation spécifique au projet afin d'éviter les conflits de versions.

### Installation globale

Pour installer Aspose.TeX Convert globalement sur votre machine, utilisez la commande suivante :

```bash
dotnet tool install --global Aspose.TeX.Convert
```

Spécifiez l'option `--version` si vous avez besoin d'une version spécifique de l'outil.

### Installation locale

Pour une installation locale dans un projet spécifique, accédez d’abord au répertoire racine de votre projet. Ensuite, exécutez les commandes suivantes :

1. Créez un manifeste d'outil s'il n'est pas déjà présent :

   ```bash
   dotnet nouveau manifeste d'outil
   ```

2. Installez Aspose.TeX Convert localement :

   ```bash
   outil dotnet installer Aspose.TeX.Convert --local
   ```

Encore une fois, vous pouvez spécifier l'option `--version` pour une version spécifique.

### Mise à jour du convertisseur TeX CLI

Pour mettre à jour l'outil Aspose.TeX Convert vers la dernière version, utilisez la commande « dotnet tool update » avec « --global » ou « --local », correspondant à votre type d'installation.

### Désinstallation du convertisseur TeX CLI

Si vous devez désinstaller l'outil, utilisez la commande « dotnet tool uninstall » avec « --global » ou « --local », selon la manière dont l'outil a été installé.

## Usage

### Ligne de commande

Convertissez vos documents à l'aide d'arguments de ligne de commande. Voici les paramètres disponibles :

- `-i, --input [Obligatoire]` : Chemin d'accès au document TeX ou LaTeX d'entrée.
  - Exemple : `--input input.tex`
- `-o, --output [Obligatoire]` : Chemin du document converti.
  - Exemple : `--output output.pdf`
- `-f, --format [Facultatif]` : format du document de sortie.
  - Formats pris en charge : PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
  - Exemple : `--format pdf`
- `-l, --license [Facultatif]` : Chemin d'accès au fichier de licence Aspose.TeX .NET.
  - Exemple : `--license path_to_license.lic`
- `-v, --verbose [Facultatif]` : Activer la sortie détaillée.
  - Exemple : `--verbeux`

Exemple d'utilisation de la ligne de commande :

```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### Comment intégrer CLI LaTeX Converter dans des projets C# ?

L'application Aspose.TeX Convert peut également être intégrée directement dans vos projets .NET à l'aide de la ligne de commande, permettant un accès par programmation aux capacités de conversion TeX dans votre code C#.
**Ajout du convertisseur de ligne de commande LaTeX à votre projet :**

Pour ajouter l'outil Aspose.TeX Convert à votre projet Visual Studio, accédez au répertoire racine de votre projet et exécutez la commande suivante :


```bash
dotnet Aspose.TeX.Convert add
```

Cette commande ajoute la fonctionnalité Aspose.TeX Convert directement dans votre projet, vous permettant d'utiliser les méthodes et propriétés de la bibliothèque via votre code. Ceci est particulièrement utile pour les développeurs cherchant à implémenter des processus de conversion TeX personnalisés directement dans leurs applications.

### Utiliser à partir du code

Voici un exemple d'utilisation des outils CLI Aspose.TeX par programmation dans votre code C# :


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

Pour plus d'informations et des exemples d'utilisation, veuillez visiter la [documentation Aspose.TeX pour .NET](/tex/{{lang.url-fragment}}net/).