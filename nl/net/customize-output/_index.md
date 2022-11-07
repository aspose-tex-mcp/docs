---
translation: true
template: /_templates/_customize-output-net.md
title: Maak aangepaste uitvoer TeX | .NET API
url: /net/customize-output/
description: ".NET API Oplossing om met TeX te werken. Lees het voorbeeld hoe u aangepaste uitvoer voor een TeX-bestand kunt maken met een paar regels C#-code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Uitvoer aanpassen
h2: ".NET API-oplossing om de uitvoer van TeX-bestanden aan te passen"
---

{{<section overview>}}
---
p1: "TeX staat bekend als een zettaal. Het betekent dat u uw tekst niet opmaakt in het document, maar de platte tekst invoert samen met de opdrachten."
p2: "Het artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) van de documentatie leert ons dat een TeX-bestand geen gegevens mag bevatten die moeten worden gezet, maar alleen reeksen controleren . Toch bevat het meestal dergelijke gegevens, en een bestand in het doelformaat heeft de gezette tekst. Het bestand heeft ook dezelfde naam als het bestand dat is opgegeven als invoer en is het belangrijkste uitvoerbestand. Voor de originele TeX is dit een bestand in DVI-formaat. We noemen de naam van zowel invoer- als uitvoerbestanden zonder de taaknaam uit te breiden."
p3: "Op deze pagina vindt u een codevoorbeeld waarin wordt uitgelegd hoe u een aangepast bestand in TeX-indeling maakt, waarin u kunt zien hoe u de uitvoer van TeX-bestanden kunt aanpassen. Om de uitvoer van .tex-bestanden aan te passen, hebben we het volgende nodig:"
p4: "Aspose.TeX voor .NET API, een veelzijdige, krachtige en gebruiksvriendelijke API voor documentmanipulatie en -conversie voor het C#-platform."
p5: "Open de NuGet-pakketbeheerder en zoek naar Aspose.TeX en installeer. U kunt ook de volgende opdracht gebruiken vanuit de Package Manager Console."
---

{{<section feature1>}}
---
title: "Stappen om TeX-uitvoer C# aan te passen:"
h3: "C#-code voor aanpassing van TeX-uitvoer"
item1: "Met behulp van de [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode van [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse, maak TeX-engine-opties zonder formaat bij ObjectTeX-engine-extensie."
item2: "Gebruik [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class om een ​​bestandssysteemwerkmap voor de invoer op te geven."
item3: "Gebruik [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class om een ​​bestandssysteemwerkmap voor de uitvoer op te geven."
item4: "Gebruik de methode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) om de nieuwe indeling te maken."
item5: Verfijn de uitvoer.
---