---
translation: true
template: /_templates/_customize-input-net.md
title: Aangepaste invoer maken TeX | .NET API
url: /net/customize-input/
description: ".NET API Oplossing om met TeX te werken. Leer in het voorbeeld hoe u aangepaste invoer voor een TeX-bestand kunt maken met een paar regels C#-code."
keywords: aangepaste invoer tex net api, C# api om tex aan te passen
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Invoer aanpassen
h2: ".NET API-oplossing om de invoer van TeX-bestanden aan te passen"
---

{{<section overview>}}
---
p1: "TeX staat bekend als een zettaal. Het betekent dat u uw tekst niet opmaakt in het document, maar de platte tekst invoert samen met de opdrachten. Zoals beschreven in het artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) van de documentatie, wordt TeX-taak uitgevoerd op een expliciet gespecificeerd TeX-bestand. We nemen dit bestand dus op in de invoer van een bepaalde TeX-taak."
p2: "Op deze pagina vindt u een codevoorbeeld waarin wordt uitgelegd hoe u de invoer van TeX-bronbestanden kunt aanpassen, rekening houdend met het feit dat de invoer de TeX-syntaxis moet volgen en idealiter alleen opdrachten moet bevatten die bekend zijn bij de engine."
p3: "Om de invoer van .tex-bestanden aan te passen, hebben we het volgende nodig:"
p4: "Aspose.TeX voor .NET API, een veelzijdige, krachtige en gebruiksvriendelijke API voor documentmanipulatie en -conversie voor het C#-platform."
p5: "Open de NuGet-pakketbeheerder en zoek naar Aspose.TeX en installeer. U kunt ook de volgende opdracht gebruiken vanuit de Package Manager Console."
---

{{<section feature1>}}
---
title: "Stappen om TeX-invoer C# aan te passen:"
h3: "C#-code voor aanpassing van TeX-invoer"
item1: "Met behulp van [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode van [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse, maak TeX-engine-opties zonder formaat bij ObjectTeX-engine-extensie."
item2: "Gebruik [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class om een ​​bestandssysteemwerkmap voor de invoer op te geven."
item3: "Maak met behulp van de [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) Methode het aangepaste formaat."
---