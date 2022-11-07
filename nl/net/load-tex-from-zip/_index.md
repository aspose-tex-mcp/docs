---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: TeX laden vanuit ZIP | .NET API-oplossing
url: /net/load-tex-from-zip/
description: ".NET API Oplossing om met TeX te werken. Leer aan de hand van het voorbeeld hoe u een TeX-bestand uit ZIP laadt met een paar regels C#-code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Laad TeX-bronbestanden vanuit ZIP
h2: ".NET API-oplossing om TeX-bestanden uit ZIP-archief te laden"
---

{{<section overview>}}
---
p1: "TeX staat bekend als een zettaal. Het betekent dat u uw tekst niet opmaakt in het document, maar de platte tekst invoert samen met de opdrachten. Als uitvoer krijgt u het opgemaakte bestand van het benodigde (opgegeven) formaat. Om meer inzicht te krijgen in de invoer en uitvoer van TeX, leest u de [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) van de documentatie."
p2: "Zoals bekend is het belangrijkste doel van TeX om te helpen bij het maken van wiskundige of technische teksten. Maar vóór enige manipulatie moet het bestand eerst worden geladen. Hier vindt u codefragmenten die uitleggen hoe u TeX-bronbestanden uit ZIP kunt laden met ZIP-directory's voor invoer en uitvoer, uitvoer naar PDF-apparaat, terminaluitvoer naar console schrijven."
p3: "Om .tex-bestanden te laden, hebben we nodig:"
p4: "Aspose.TeX voor .NET API, een veelzijdige, krachtige en gebruiksvriendelijke API voor documentmanipulatie en -conversie voor het C#-platform."
p5: "Open de NuGet-pakketbeheerder en zoek naar Aspose.TeX en installeer. U kunt ook de volgende opdracht gebruiken vanuit de Package Manager Console."
---

{{<section feature1>}}
---
title: "Stappen om TeX te laden vanuit een ZIP-archief C#:"
h3: "C#-code voor het laden van TeX"
item1: "Open de stream in het ZIP-archief om deze als invoerwerkmap te gebruiken."
item2: "Open de stream in het ZIP-archief om deze als uitvoerwerkmap te gebruiken."
item3: "Maak conversie-opties voor standaard ObjectTeX-indeling bij ObjectTeX-engine-extensie met behulp van [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode van [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse."
item4: "Specificeer een ZIP archief werkmap voor de invoer of/en specificeer een pad binnen het archief. Gebruik hiervoor constructors van de [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) Class."
item5: "Specificeer een ZIP-archiefwerkmap voor de uitvoer en/of specificeer een pad binnen het archief. Gebruik hiervoor constructors van de [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) Class."
item6: "Specificeer de console als de uitvoerterminal met [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class."
item7: "Definieer de opslagopties met [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) Class."
item8: "Voer de taak [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Methode uit voor [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Verfijn de uitvoer.
---