---
translation: true
template: /_templates/_customize-input-net.md
title: Skapa anpassad indata TeX | .NET API
url: /net/customize-input/
description: ".NET API-lösning för att fungera med TeX. Lär dig i exemplet hur du skapar anpassad indata för TeX-fil med några rader C#-kod."
keywords: anpassad indata tex net api, C# api för att anpassa tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Anpassa inmatning
h2: ".NET API-lösning för att anpassa inmatning av TeX-filer"
---

{{<section overview>}}
---
p1: "TeX är känt som ett typsättningsspråk. Det innebär att du inte formaterar din text i dokumentet, utan skriver in den vanliga texten tillsammans med kommandona. Som det beskrivs i artikeln [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) i dokumentationen, körs TeX-jobbet på en explicit specificerad TeX-fil. Så vi inkluderar den här filen i inmatningen av ett visst TeX-jobb."
p2: "På den här sidan hittar du ett kodexempel som förklarar hur man anpassar inmatning av TeX-källfiler med hänsyn till att inmatningen ska följa TeX-syntax och, idealiskt, endast innehålla kommandon som motorn känner till."
p3: "För att anpassa inmatningen av .tex-filer behöver vi:"
p4: "Aspose.TeX för .NET API som är ett funktionsrikt, kraftfullt och lättanvänt API för dokumentmanipulation och konvertering för C#-plattformen."
p5: "Öppna NuGet-pakethanteraren och sök efter Aspose.TeX och installera. Du kan också använda följande kommando från Package Manager Console."
---

{{<section feature1>}}
---
title: "Steg för att anpassa TeX-ingång C#:"
h3: "C#-kod för anpassning av TeX-ingång"
item1: "Använder [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) metoden för [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klass, skapa TeX-motoralternativ utan format vid ObjectTeX-motortillägg."
item2: "Använd klassen [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) och ange en arbetskatalog för filsystemet för inmatningen."
item3: "Med hjälp av metoden [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) skapar du det anpassade formatet."
---