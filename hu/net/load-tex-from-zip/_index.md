---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: TeX betöltése ZIP-ből | .NET API megoldás
url: /net/load-tex-from-zip/
description: ".NET API megoldás a TeX-szel való együttműködéshez. Ismerje meg a példát, hogyan tölthet be egy TeX fájlt ZIP-ből néhány soros C# kóddal."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX forrásfájlok betöltése ZIP-ből
h2: ".NET API megoldás a TeX fájlok ZIP archívumból való betöltésére"
---

{{<section overview>}}
---
p1: "A TeX szedőnyelvként ismert. Ez azt jelenti, hogy nem formázza a szöveget a dokumentumban, hanem írja be az egyszerű szöveget a parancsokkal együtt. Kimenetként megkapja a szükséges (megadott) formátumú formázott fájlt. A TeX bemenet és kimenet jobb megértéséhez tanulja meg a [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) dokumentumot."
p2: "Mint ismeretes, a TeX fő célja a matematikai vagy technikai szövegírás létrehozásának elősegítése. De minden manipuláció előtt először be kell tölteni a fájlt. Itt olyan kódrészleteket talál, amelyek elmagyarázzák, hogyan tölthet be TeX-forrásfájlokat ZIP-ből ZIP-könyvtárak használatával a bemeneti és kimeneti célokra, a kimenetet PDF-eszközre, a terminálkimenetet a konzolra írva."
p3: "A .tex fájlok betöltéséhez szükségünk van:"
p4: "Aspose.TeX for .NET API, amely funkciókban gazdag, hatékony és könnyen használható dokumentumkezelési és -konverziós API C# platformhoz."
p5: "Nyissa meg a NuGet csomagkezelőt, keresse meg az Aspose.TeX fájlt, és telepítse. A következő parancsot is használhatja a Package Manager konzolból."
---

{{<section feature1>}}
---
title: "A TeX betöltésének lépései ZIP-archívumból C#:"
h3: "C# kód a TeX betöltéséhez"
item1: "Nyissa meg az adatfolyamot a ZIP-archívumban, hogy bemeneti munkakönyvtárként használja."
item2: "Nyissa meg az adatfolyamot a ZIP-archívumban, hogy kimeneti munkakönyvtárként használja."
item3: "Hozzon létre konverziós beállításokat az alapértelmezett ObjectTeX formátumhoz az ObjectTeX motorbővítménynél a [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Osztály."
item4: "Adjon meg egy ZIP-archívum munkakönyvtárat a bemenethez és/és adjon meg egy elérési utat az archívumban. Ehhez használja az [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) osztály konstruktorait."
item5: "Adjon meg egy ZIP-archívum munkakönyvtárat a kimenethez és/és adjon meg egy elérési utat az archívumban. Ehhez használja az [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) osztály konstruktorait."
item6: "Adja meg a konzolt kimeneti terminálként az [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) osztály használatával."
item7: "Határozza meg a mentési beállításokat a [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) osztály segítségével."
item8: "Futtassa a feladatot [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Method for [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Finomítsa a kimenetet.
---