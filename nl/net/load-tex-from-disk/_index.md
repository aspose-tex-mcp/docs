---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: TeX laden vanaf een schijf | .NET API
url: /net/load-tex-from-disk/
description: ".NET API Oplossing om met TeX te werken. Leer in het voorbeeld hoe u een TeX-bestand van schijf laadt met een paar regels C#-code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Laad TeX-bronbestanden van schijf
h2: ".NET API-oplossing om TeX/LaTeX-bestanden van schijf te laden"
---

{{<section overview>}}
---
p1: "TeX staat bekend als een zettaal. Het betekent dat u uw tekst niet opmaakt in het document, maar de platte tekst invoert samen met de opdrachten. Als uitvoer krijgt u het opgemaakte bestand van het benodigde (opgegeven) formaat. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) is de centrale kern van het publicatiesetsysteem (computertypesetting). Een TeX-taak wordt uitgevoerd op een expliciet gespecificeerd TeX-bestand. Om meer inzicht te krijgen in de invoer en uitvoer van TeX, leest u de [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) van de documentatie."
p2: "Zoals bekend is het belangrijkste doel van TeX om te helpen bij het maken van wiskundige of technische teksten. Maar vóór enige manipulatie moet het bestand eerst worden geladen. Hier vindt u codefragmenten die uitleggen hoe u TeX-bronbestanden van schijf laadt met behulp van bestandssysteemmappen voor invoer en uitvoer, uitvoer naar XPS-apparaat, terminaluitvoer naar console schrijven."
p3: "Om de voorbeelden uit te voeren hebben we nodig:"
p4: "Aspose.TeX voor .NET API, een veelzijdige, krachtige en gebruiksvriendelijke API voor documentmanipulatie en -conversie voor het C#-platform."
p5: "Open de NuGet-pakketbeheerder en zoek naar Aspose.TeX en installeer. U kunt ook de volgende opdracht gebruiken vanuit de Package Manager Console."
---

{{<section feature1>}}
---
title: Stappen om TeX te laden vanaf een schijf C#.
h3: "C#-code voor het laden van TeX"
item1: "Maak conversie-opties voor een aangepast formaat bij ObjectTeX-engine-extensie met behulp van [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Methode van [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasse."
item2: "Geef een werkmap van het bestandssysteem op voor de invoer. Gebruik hiervoor de [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) klasse."
item3: "Specificeer een werkmap van het bestandssysteem voor de uitvoer met behulp van [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class."
item4: "Specificeer de console als de uitvoerterminal met [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class."
item5: "Specificeer indien nodig een geheugenterminal als uitvoerterminal. Gebruik hiervoor [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) Class."
item6: "Voer de taak [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Methode uit voor [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Verfijn de uitvoer.
---