---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: TeX-zetfunctie | .NET-API-oplossing
url: /net/typeset-tex-files/
description: ".NET API Oplossing om met TeX te werken. Leer in het voorbeeld hoe u TeX-typesets maakt met een paar regels C#-code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Gezet TeX-bestanden
h2: "Typ een TeX-bestand met een aangepast TeX-formaat C# .NET"
---

{{<section overview>}}
---
p1: "TeX staat bekend als een van de opmaaktalen voor gegevens en/of tegelijkertijd als zettaal. Het betekent dat u uw tekst niet opmaakt in het document, maar de platte tekst invoert samen met de opdrachten. Als uitvoer krijgt u het opgemaakte bestand van het benodigde (opgegeven) formaat. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) is de centrale kern van het publicatiesetsysteem (computertypesetting)."
p2: "Lees de [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) van de documentatie om meer inzicht te krijgen in TeX-typesetting. En op deze pagina vindt u codefragmenten die uitleggen hoe u een TeX-bestand typt met een aangepast TeX-formaat."
p3: "Om de voorbeelden uit te voeren hebben we nodig:"
p4: "Aspose.TeX voor .NET API, een veelzijdige, krachtige en gebruiksvriendelijke API voor documentmanipulatie en -conversie voor het C#-platform."
p5: "Open de NuGet-pakketbeheerder en zoek naar Aspose.TeX en installeer. U kunt ook de volgende opdracht gebruiken vanuit de Package Manager Console."
---

{{<section feature1>}}
---
title: Stappen om TeX in te stellen met C#.
h3: "C# Code voor het zetten van TeX"
item1: "Maak de indelingsprovider met behulp van de klasse [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Maak conversie-opties voor een aangepast formaat bij ObjectTeX-engine-extensie met behulp van [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode van [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse."
item3: "Geef de invoerwerkdirectory op als de hoofdinvoer niet als een stroom wordt geleverd. Gebruik hiervoor de [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) klasse."
item4: "Geef een werkmap van het bestandssysteem op voor de uitvoer. Gebruik hiervoor de [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class hiervoor."
item5: "Voer de taak [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Methode uit voor [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Verfijn de uitvoer.
---