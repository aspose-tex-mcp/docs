---
translation: true
template: /_templates/_customize-output-net.md
title: Skapa anpassad utdata TeX | .NET API-lösning
url: /net/customize-output/
description: ".NET API-lösning för att fungera med TeX. Läs exemplet hur man skapar anpassad utdata för TeX-fil med några rader C#-kod."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Anpassa utdata
h2: ".NET API-lösning för att anpassa utdata av TeX-filer"
---

{{<section overview>}}
---
p1: "TeX är känt som ett typsättningsspråk. Det innebär att du inte formaterar din text i dokumentet, utan skriver in den vanliga texten tillsammans med kommandona."
p2: "Artikeln [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) i dokumentationen lär oss att en TeX-fil inte får innehålla några data att typsätta utan endast styrsekvenser . Ändå innehåller den vanligtvis sådana data, och en fil i målformatet har den typade texten. Filen kommer också att ha samma namn som filen som anges som indata och är den huvudsakliga utdatafilen. För original TeX är detta en fil i DVI-format. Vi kommer att anropa namnet på både inmatnings- och utdatafiler utan att utöka jobbnamnet."
p3: "På den här sidan hittar du ett kodexempel som förklarar att skapa en anpassad TeX-formatfil där du kan se hur du anpassar utdata från TeX-filer. För att anpassa .tex-filers utdata behöver vi:"
p4: "Aspose.TeX för .NET API som är ett funktionsrikt, kraftfullt och lättanvänt API för dokumentmanipulation och konvertering för C#-plattformen."
p5: "Öppna NuGet-pakethanteraren och sök efter Aspose.TeX och installera. Du kan också använda följande kommando från Package Manager Console."
---

{{<section feature1>}}
---
title: "Steg för att anpassa TeX-utgång C#:"
h3: "C#-kod för anpassning av TeX-utgång"
item1: "Med hjälp av metoden [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) för [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klass, skapa TeX-motoralternativ utan format vid ObjectTeX-motortillägg."
item2: "Använd [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class för att ange en filsystems arbetskatalog för indata."
item3: "Använd [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class för att ange en filsystems arbetskatalog för utdata."
item4: "För att skapa det nya formatet använd metoden [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Förfina utgången.
---