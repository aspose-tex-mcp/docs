---
translation: true
template: /_templates/_output-to-disk-net.md
title: TeX kimenet írása lemezre | .NET API megoldás
url: /net/output-to-disk/
description: ".NET API megoldás a TeX-szel való együttműködéshez. Ismerje meg a példát, hogyan hozhat létre egyedi kimenetet a TeX-fájlhoz néhány soros C# kóddal."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Írja a TeX kimenetet a lemezre
h2: "Mentse el a TeX fájlkonverzió eredményét lemezre C# .NET-en keresztül"
---

{{<section overview>}}
---
p1: "A TeX betűszedő nyelvként ismert, ami azt jelenti, hogy nem formázza a szöveget a dokumentumban, hanem az egyszerű szöveget írja be a parancsokkal együtt. Amint az a Dokumentáció [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) cikkéből ismert, a TeX-feladat egy kifejezetten meghatározott TeX-fájlon fut. Itt is tájékozódhat a TeX interakciós módokról és a TeX bemeneti és kimeneti primitívumairól."
p2: "A TeX fő felhasználási területe a matematikai vagy technikai szövegírás létrehozásának segítése. De ha a fájl már létrejött, és nem kíván további manipulációkat végezni rajta, érdemes lehet konvertálni egy másik, népszerűbb formátumba."
p3: "Ezen az oldalon talál egy kódpéldát, amely elmagyarázza a fájlrendszer-könyvtárak használatát a bemenethez és a kimenethez, az XPS-eszközre történő kimenetet, a feladat nevének felülbírálását, a terminál kimenetének lemezre írását. Egyszerűen fogalmazva, ez egy átalakítás a kimenet lemezre írásával. Egy ilyen művelet végrehajtásához szükségünk van:"
p4: "Aspose.TeX for .NET API, amely funkciókban gazdag, hatékony és könnyen használható dokumentumkezelési és -konverziós API C# platformhoz."
p5: "Nyissa meg a NuGet csomagkezelőt, keresse meg az Aspose.TeX fájlt, és telepítse. A következő parancsot is használhatja a Package Manager konzolból."
---

{{<section feature1>}}
---
title: "A terminál kimenetének C# lemezre írásának lépései:"
h3: "C# kód a TeX konvertálásához és a kimenet lemezre írásához"
item1: "Hozzon létre konverziós beállításokat az ObjectTeX motorbővítménynél a [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Osztály."
item2: "Adjon meg egy jobnevet, ha nem szeretné, hogy a TeXJob konstruktor első argumentuma jobnévként legyen."
item3: "Adja meg a fájlrendszer munkakönyvtárát a bemenethez. Ehhez használja az [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) osztályt."
item4: "Adjon meg egy fájlrendszer munkakönyvtárat a kimenethez az [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) osztály entitásai segítségével."
item5: "Adja meg, hogy a terminál kimenetét a kimeneti munkakönyvtárban lévő fájlba kell írni."
item6: "Futtassa a feladatot [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Method for [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---