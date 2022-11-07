---
translation: true
template: /_templates/_customize-output-net.md
title: Egyéni kimenet létrehozása TeX | .NET API
url: /net/customize-output/
description: ".NET API megoldás a TeX-szel való együttműködéshez. Olvassa el a példát, hogyan hozhat létre egyedi kimenetet a TeX fájlhoz néhány soros C# kóddal."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: A kimenet testreszabása
h2: ".NET API megoldás a TeX fájlok kimenetének testreszabásához"
---

{{<section overview>}}
---
p1: "A TeX szedőnyelvként ismert. Ez azt jelenti, hogy nem formázza a szöveget a dokumentumban, hanem írja be az egyszerű szöveget a parancsokkal együtt."
p2: "A Dokumentáció [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) cikke megtanítja nekünk, hogy a TeX fájl nem tartalmazhat beszedhető adatokat, csak vezérlőszekvenciákat. . Mégis általában tartalmaz ilyen adatokat, és a célformátumú fájl rendelkezik a beírt szöveggel. A fájl neve is ugyanaz lesz, mint a bemenetként megadott fájl, és ez a fő kimeneti fájl. Az eredeti TeX esetében ez egy DVI formátumú fájl. Mind a bemeneti, mind a kimeneti fájlok nevét a feladat nevének kiterjesztése nélkül hívjuk meg."
p3: "Ezen az oldalon talál egy kódpéldát, amely elmagyarázza egy egyedi TeX formátumú fájl létrehozását, ahol megtekintheti, hogyan szabhatja testre a TeX fájlok kimenetét. A .tex fájlok kimenetének testreszabásához szükségünk van:"
p4: "Aspose.TeX for .NET API, amely funkciókban gazdag, hatékony és könnyen használható dokumentumkezelési és -konverziós API C# platformhoz."
p5: "Nyissa meg a NuGet csomagkezelőt, keresse meg az Aspose.TeX fájlt, és telepítse. A következő parancsot is használhatja a Package Manager konzolból."
---

{{<section feature1>}}
---
title: "A TeX C# kimenet testreszabásának lépései:"
h3: "C# kód a TeX kimenet testreszabásához"
item1: "A [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Osztály, hozzon létre TeX motor opciókat formátum nélkül az ObjectTeX motor bővítésekor."
item2: "Használja az [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) osztályt a fájlrendszer munkakönyvtárának megadásához a bemenethez."
item3: "Használja az [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) osztályt a fájlrendszer munkakönyvtárának megadásához a kimenethez."
item4: "Az új formátum létrehozásához használja a [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) módszert."
item5: Finomítsa a kimenetet.
---