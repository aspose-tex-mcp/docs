---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Laddar TeX från ZIP | .NET API-lösning
url: /net/load-tex-from-zip/
description: ".NET API-lösning för att fungera med TeX. Lär dig i exemplet hur man laddar en TeX-fil från ZIP med några rader C#-kod."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Ladda TeX-källfiler från ZIP
h2: ".NET API Lösning för att ladda TeX-filer från ZIP-arkiv"
---

{{<section overview>}}
---
p1: "TeX är känt som ett typsättningsspråk. Det innebär att du inte formaterar din text i dokumentet, utan skriver in den vanliga texten tillsammans med kommandona. Som en utgång får du den formaterade filen med det önskade (specificerade) formatet. För att få mer förståelse för TeX-inmatning och -utgång, läs [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) i dokumentationen."
p2: "Som det är känt är huvudsyftet med TeX att hjälpa till att skapa matematisk eller teknisk textskrivning. Men innan några manipulationer bör filen först laddas. Här hittar du kodsnuttar som förklarar hur man laddar TeX-källfiler från ZIP med hjälp av ZIP-kataloger för in- och utmatning, utmatning till PDF-enhet, skrivning av terminalutdata till konsolen."
p3: "För att ladda .tex-filer behöver vi:"
p4: "Aspose.TeX för .NET API som är ett funktionsrikt, kraftfullt och lättanvänt API för dokumentmanipulation och konvertering för C#-plattformen."
p5: "Öppna NuGet-pakethanteraren och sök efter Aspose.TeX och installera. Du kan också använda följande kommando från Package Manager Console."
---

{{<section feature1>}}
---
title: "Steg för att ladda TeX från ett ZIP-arkiv C#:"
h3: "C#-kod för att ladda TeX"
item1: "Öppna strömmen i ZIP-arkivet för att använda den som arbetskatalog för inmatning."
item2: "Öppna strömmen i ZIP-arkivet för att använda den som arbetskatalog för utdata."
item3: "Skapa konverteringsalternativ för standard ObjectTeX-format med ObjectTeX-motortillägg med [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metod för [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klass."
item4: "Ange en ZIP-arkivarbetskatalog för inmatningen eller/och ange en sökväg inuti arkivet. Använd konstruktörer av klassen [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) för detta."
item5: "Ange en ZIP-arkivarbetskatalog för utdata eller/och ange en sökväg inuti arkivet. Använd konstruktörer av klassen [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) för detta."
item6: "Ange konsolen som utgångsterminal med [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class."
item7: "Definiera sparalternativen med [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) Klass."
item8: "Kör jobbmetoden [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) för [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Förfina utgången.
---