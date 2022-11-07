---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Laddar TeX från en disk | .NET API-lösning
url: /net/load-tex-from-disk/
description: ".NET API-lösning för att fungera med TeX. Lär dig i exemplet hur man laddar en TeX-fil från disk med några rader C#-kod."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Ladda TeX-källfiler från disken
h2: ".NET API Lösning för att ladda TeX/LaTeX-filer från disk"
---

{{<section overview>}}
---
p1: "TeX är känt som ett typsättningsspråk. Det innebär att du inte formaterar din text i dokumentet, utan skriver in den vanliga texten tillsammans med kommandona. Som en utgång får du den formaterade filen med det önskade (specificerade) formatet. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) är den centrala kärnan i publiceringssetsystemet (datortypsättning). Ett TeX-jobb körs på en uttryckligen specificerad TeX-fil. För att få mer förståelse för TeX-inmatning och -utgång, läs [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) i dokumentationen."
p2: "Som det är känt är huvudsyftet med TeX att hjälpa till att skapa matematisk eller teknisk textskrivning. Men innan några manipulationer bör filen först laddas. Här hittar du kodsnuttar som förklarar hur man laddar TeX-källfiler från disk med filsystemkataloger för in- och utmatning, utmatning till XPS-enhet, skrivning av terminalutdata till konsolen."
p3: "För att köra exemplen behöver vi:"
p4: "Aspose.TeX för .NET API som är ett funktionsrikt, kraftfullt och lättanvänt API för dokumentmanipulation och konvertering för C#-plattformen."
p5: "Öppna NuGet-pakethanteraren och sök efter Aspose.TeX och installera. Du kan också använda följande kommando från Package Manager Console."
---

{{<section feature1>}}
---
title: Steg för att ladda TeX från en disk C#.
h3: "C#-kod för att ladda TeX"
item1: "Skapa konverteringsalternativ för ett anpassat format med ObjectTeX-motortillägg med [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoden för [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klass."
item2: "Ange en arbetskatalog för filsystemet för inmatningen. Använd klassen [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) för detta."
item3: "Ange en arbetskatalog för filsystemet för utdata med klassen [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Ange konsolen som utgångsterminal med [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class."
item5: "Ange en minnesterminal som en utgångsterminal om du behöver. För detta använd [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) Klass."
item6: "Kör jobbmetoden [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) för [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Förfina utgången.
---