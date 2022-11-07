---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: TeX typsättning funktionalitet | .NET API
url: /net/typeset-tex-files/
description: ".NET API-lösning för att fungera med TeX. Lär dig i exemplet hur du skapar TeX-typuppsättningar med några rader C#-kod."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Typuppsättning TeX-filer
h2: "Skriv in en TeX-fil med ett anpassat TeX-format C# .NET"
---

{{<section overview>}}
---
p1: "TeX är känt som ett av datamarkeringsspråken och/eller ett typsättningsspråk samtidigt. Det innebär att du inte formaterar din text i dokumentet, utan skriver in den vanliga texten tillsammans med kommandona. Som en utgång får du den formaterade filen med det önskade (specificerade) formatet. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) är den centrala kärnan i publiceringssetsystemet (datortypsättning)."
p2: "För att få mer förståelse för TeX-typsättning läs [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) i dokumentationen. Och på den här sidan hittar du kodavsnitt som förklarar hur man sätter in en TeX-fil med ett anpassat TeX-format."
p3: "För att köra exemplen behöver vi:"
p4: "Aspose.TeX för .NET API som är ett funktionsrikt, kraftfullt och lättanvänt API för dokumentmanipulation och konvertering för C#-plattformen."
p5: "Öppna NuGet-pakethanteraren och sök efter Aspose.TeX och installera. Du kan också använda följande kommando från Package Manager Console."
---

{{<section feature1>}}
---
title: Steg för att sätta in TeX med C#.
h3: "C#-kod för typsättning av TeX"
item1: "Skapa formatleverantören med klassen [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Skapa konverteringsalternativ för ett anpassat format med ObjectTeX-motortillägg med [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoden för [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klass."
item3: "Ange ingångsarbetskatalogen om huvudingången inte tillhandahålls som en ström. Använd klassen [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) för detta."
item4: "Ange en arbetskatalog för filsystemet för utdata. Använd klassen [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) för detta."
item5: "Kör jobbmetoden [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) för [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Förfina utgången.
---