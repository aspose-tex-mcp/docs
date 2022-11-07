---
translation: true
template: /_templates/_output-to-disk-net.md
title: Schrijf TeX-uitvoer naar schijf | .NET API
url: /net/output-to-disk/
description: ".NET API Oplossing om met TeX te werken. Leer in het voorbeeld hoe u aangepaste uitvoer voor een TeX-bestand kunt maken met een paar regels C#-code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Schrijf TeX-uitvoer naar schijf
h2: "Sla het resultaat van de TeX-bestandsconversie op als schijf via C# .NET"
---

{{<section overview>}}
---
p1: "TeX staat bekend als een zettaal, wat betekent dat u uw tekst niet opmaakt in het document, maar de platte tekst invoert samen met de opdrachten. Zoals bekend is uit het artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) van de documentatie, wordt de TeX-taak uitgevoerd op een expliciet gespecificeerd TeX-bestand. Daar kunt u ook informatie vinden over TeX-interactiemodi en primitieven met betrekking tot TeX-invoer en -uitvoer."
p2: "Het belangrijkste gebruik van TeX is om te helpen bij het maken van wiskundige of technische teksten. Maar als het bestand al is gemaakt en u er geen verdere manipulaties aan wilt, wilt u het misschien converteren naar een ander, populairder formaat."
p3: "Op deze pagina vindt u een codevoorbeeld waarin wordt uitgelegd hoe u bestandssysteemmappen gebruikt voor invoer en uitvoer, uitvoer naar een XPS-apparaat, de taaknaam overschrijft en terminaluitvoer naar schijf schrijft. In eenvoudige bewoordingen is het een conversie met het schrijven van de uitvoer naar de schijf. Om een ​​dergelijke operatie uit te voeren, hebben we nodig:"
p4: "Aspose.TeX voor .NET API, een veelzijdige, krachtige en gebruiksvriendelijke API voor documentmanipulatie en -conversie voor het C#-platform."
p5: "Open de NuGet-pakketbeheerder en zoek naar Aspose.TeX en installeer. U kunt ook de volgende opdracht gebruiken vanuit de Package Manager Console."
---

{{<section feature1>}}
---
title: "Stappen om terminaluitvoer naar schijf C# te schrijven:"
h3: "C# Code voor het converteren van TeX en het schrijven van de uitvoer naar de schijf"
item1: "Maak conversie-opties bij ObjectTeX-engine-extensie met behulp van [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode van [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse."
item2: "Geef een taaknaam op als u niet wilt dat het eerste argument van de TeXJob-constructor als taaknaam wordt gebruikt."
item3: "Geef een werkmap van het bestandssysteem op voor de invoer. Gebruik hiervoor de [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) klasse."
item4: "Specificeer een bestandssysteemwerkmap voor de uitvoer met behulp van de entiteiten van de [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class."
item5: "Geef op dat de terminaluitvoer moet worden geschreven naar een bestand in de uitvoerwerkdirectory."
item6: "Voer de taak [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Methode uit voor [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---