---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX till ZIP | .NET API-lösning
url: /net/output-to-zip/
description: ".NET API för att fungera med TeX. TeX till ZIP-konverteringsfunktioner låter dig spara din TeX-fil som det mest populära arkivet. C# exempel."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Skriv utdata till ZIP
h2: "Spara resultatet av TeX-filkonverteringen som ZIP via C# .NET"
---

{{<section overview>}}
---
p1: "TeX är känt som ett av datamarkeringsspråken. Det är huvudkärnan i publikationsuppsättningssystemet (datortypsättning). Det är tveksamt att betrakta [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) som ett filformat, eftersom det är ett programmeringsspråk. Och å andra sidan är det en tolkmotor som förstår detta språk. Hur som helst, kort sagt, dess huvudsakliga syfte är att hjälpa till med skapandet av matematisk eller teknisk textskrivning. Men när filen redan är skapad och du inte vill ha några ytterligare manipulationer på den, kanske du vill konvertera den till ett annat, mer populärt format."
p2: "Aspose.TeX API-lösning bland de olika andra funktionerna tillåter konvertering av TeX-filer och sedan spara resultatet som ZIP-arkiv. Här hittar du ett kodavsnitt om hur du konverterar TeX till PDF och sparar resultatet av resultatet till zip. API-omvandlaren omvandlar TeX med vilket språk som helst som stöds av C#. API:et du ser här kan också användas för att skapa din egen plattformsoberoende applikation eller integreras i ditt .NET-projekt. Sådana [*plattformskonverterare*](https://products.aspose.app/tex/conversion/tex) finns också i Asposes ekosystem. Men för att köra exemplen behöver vi:"
p3: "Aspose.TeX för .NET API som är ett funktionsrikt, kraftfullt och lättanvänt API för dokumentmanipulation och konvertering för C#-plattformen."
p4: "Öppna NuGet-pakethanteraren och sök efter Aspose.TeX och installera. Du kan också använda följande kommando från Package Manager Console."
---

{{<section feature1>}}
---
title: Steg för att använda ZIP-kataloger för utdata TeX-fil C#.
h3: "C#-kod för att använda ZIP-kataloger för utdata"
item1: "Skapa instansen av [*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "Ange en ZIP-arkivarbetskatalog för utdata med egenskapen [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)."
item3: "Ange konsolen som utgångsterminal med klassen [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item4: "Definiera alternativen för att spara med [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) Klass."
item5: "Kör konvertering med metoden [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) för [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: Förfina utgången.
item7: "Använd klassen [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) för att slutföra ZIP-arkivet."
---