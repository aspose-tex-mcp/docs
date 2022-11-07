---
translation: true
template: /_templates/_output-to-disk-net.md
title: Skriv TeX-utgång till disk | .NET API-lösning
url: /net/output-to-disk/
description: ".NET API-lösning för att fungera med TeX. Lär dig i exemplet hur du skapar anpassad utdata för TeX-fil med några rader C#-kod."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Skriv TeX-utgång till disk
h2: "Spara resultatet av TeX-filkonverteringen som disk via C# .NET"
---

{{<section overview>}}
---
p1: "TeX är känt som ett typsättningsspråk vilket innebär att du inte formaterar din text i dokumentet, utan skriver in ren text tillsammans med kommandona. Som det är känt från artikeln [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) i dokumentationen, körs TeX-jobbet på en explicit specificerad TeX-fil. Där kan du också få information om TeX-interaktionslägen och primitiver relaterade till TeX-inmatning och -utgång."
p2: "Den huvudsakliga användningen av TeX är att hjälpa till med att skapa matematisk eller teknisk textskrivning. Men när filen redan är skapad och du inte vill ha några ytterligare manipulationer på den, kanske du vill konvertera den till ett annat, mer populärt format."
p3: "På den här sidan hittar du ett kodexempel som förklarar användning av filsystemkataloger för inmatning och utmatning, utmatning till XPS-enhet, åsidosättande av jobbnamnet, skrivning av terminalutdata till disk. Med enkla ord är det en konvertering med skrivning av utdata till disken. För att köra en sådan operation behöver vi:"
p4: "Aspose.TeX för .NET API som är ett funktionsrikt, kraftfullt och lättanvänt API för dokumentmanipulation och konvertering för C#-plattformen."
p5: "Öppna NuGet-pakethanteraren och sök efter Aspose.TeX och installera. Du kan också använda följande kommando från Package Manager Console."
---

{{<section feature1>}}
---
title: "Steg för att skriva terminalutgång till disk C#:"
h3: "C#-kod för att konvertera TeX och skriva utdata till disken"
item1: "Skapa konverteringsalternativ med ObjectTeX-motortillägg med [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoden [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klass."
item2: "Ange ett jobbnamn om du inte vill att det första argumentet för TeXJob-konstruktorn ska tas som ett jobbnamn."
item3: "Ange en arbetskatalog för filsystemet för inmatningen. Använd klassen [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) för detta."
item4: "Ange en arbetskatalog för filsystemet för utdata med hjälp av entiteterna i klassen [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Ange att terminalutgången måste skrivas till en fil i utgångens arbetskatalog."
item6: "Kör jobbmetoden [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) för [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---