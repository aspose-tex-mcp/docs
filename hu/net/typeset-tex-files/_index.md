---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: TeX szedés funkció | .NET API
url: /net/typeset-tex-files/
description: ".NET API megoldás a TeX-szel való együttműködéshez. Ismerje meg a példát, hogyan hozhat létre TeX-típuskészleteket néhány soros C# kóddal."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX fájlok gépelése
h2: "Gépeljen be egy TeX fájlt egyéni TeX formátumú C# .NET használatával"
---

{{<section overview>}}
---
p1: "A TeX az egyik adatjelölő nyelvként és/vagy egyidejűleg szedőnyelvként ismert. Ez azt jelenti, hogy nem formázza a szöveget a dokumentumban, hanem írja be az egyszerű szöveget a parancsokkal együtt. Kimenetként megkapja a szükséges (megadott) formátumú formázott fájlt. A [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) a kiadványkészlet-rendszer (számítógépes szedés) központi magja."
p2: "A TeX-szedés jobb megértéséhez tanulja meg a Dokumentáció [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) részét. Ezen az oldalon pedig olyan kódrészleteket talál, amelyek elmagyarázzák, hogyan kell TeX fájlokat begépelni egyéni TeX formátum használatával."
p3: "A példák futtatásához szükségünk van:"
p4: "Aspose.TeX for .NET API, amely funkciókban gazdag, hatékony és könnyen használható dokumentumkezelési és -konverziós API C# platformhoz."
p5: "Nyissa meg a NuGet csomagkezelőt, keresse meg az Aspose.TeX fájlt, és telepítse. A következő parancsot is használhatja a Package Manager konzolból."
---

{{<section feature1>}}
---
title: A TeX beírásának lépései C# használatával.
h3: "C# kód a TeX betűszedéséhez"
item1: "Hozza létre a formátumszolgáltatót az [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) osztály használatával."
item2: "Hozzon létre konverziós beállításokat egyéni formátumhoz az ObjectTeX motorbővítménynél a [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Osztály."
item3: "Adja meg a bemeneti munkakönyvtárat, ha a fő bemenet nem adatfolyamként van megadva. Ehhez használja az [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) osztályt."
item4: "Adja meg a fájlrendszer munkakönyvtárát a kimenethez. Ehhez használja az [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) osztályt."
item5: "Futtassa a feladatot [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Method for [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Finomítsa a kimenetet.
---