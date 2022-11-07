---
translation: true
template: /_templates/_create-custom-tex-net.md
title: Skräddarsydda TeX-filer | .NET API-lösning
url: /net/create-custom-tex/
description: ".NET API-lösning för att fungera med TeX. Inkluderar funktionalitet för att skapa anpassade TeX-format. C# exempel på funktionalitet för att anpassa TeX."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Skapa anpassat TeX-format
h2: "Skapa en fil i anpassat TeX-format via C# .NET"
---

{{<section overview>}}
---
p1: "TeX är känt som ett av datamarkeringsspråken. Det är huvudkärnan i publikationsuppsättningssystemet (datortypsättning). Det är tveksamt att betrakta [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) som ett filformat, eftersom det är ett programmeringsspråk. Och å andra sidan är det en tolkmotor som förstår detta språk. Hur som helst, kort sagt, dess huvudsakliga syfte är att hjälpa till med skapandet av matematisk eller teknisk textskrivning. Många olika paket har skapats på basis av ΤeΧ. De syftar till att göra det lättare att bearbeta dokumenten, särskilt när de har formler eller matematiska ekvationer."
p2: "Aspose.TeX API-lösning bland de olika andra funktionerna gör det möjligt att skapa dina egna presenterade TeX-filer. Här hittar du information som förklarar hur du skapar filer i ett sådant anpassat format. En sådan fil kommer att ha de anpassade motoralternativen. För detta behöver vi:"
p3: "Aspose.TeX för .NET API som är ett funktionsrikt, kraftfullt och lättanvänt API för dokumentmanipulation och konvertering för C#-plattformen."
p4: "Öppna NuGet-pakethanteraren och sök efter Aspose.TeX och installera. Du kan också använda följande kommando från Package Manager Console."
---

{{<section feature1>}}
---
title: Steg för att skapa en anpassad TeX-fil C#.
h3: "C#-kod för att anpassa TeX-filer"
item1: "Använder [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) metoden för [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klass, skapa TeX-motoralternativ utan format vid ObjectTeX-motortillägg."
item2: "Använd klassen [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) och ange en arbetskatalog för filsystemet för inmatningen."
item3: "Använd [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class för att ange en filsystems arbetskatalog för utdata."
item4: "Skapa formatet med metoden [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Förfina utgången.
---