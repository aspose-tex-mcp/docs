---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: TeX betöltése lemezről | .NET API megoldás
url: /net/load-tex-from-disk/
description: ".NET API megoldás a TeX-szel való együttműködéshez. Ismerje meg a példát, hogyan tölthet be egy TeX fájlt a lemezről néhány soros C# kóddal."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Töltsön be TeX forrásfájlokat a lemezről
h2: ".NET API megoldás a TeX/LaTeX fájlok lemezről való betöltésére"
---

{{<section overview>}}
---
p1: "A TeX szedőnyelvként ismert. Ez azt jelenti, hogy nem formázza a szöveget a dokumentumban, hanem írja be az egyszerű szöveget a parancsokkal együtt. Kimenetként megkapja a szükséges (megadott) formátumú formázott fájlt. A [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) a kiadványkészlet-rendszer (számítógépes szedés) központi magja. Egy TeX-feladat egy kifejezetten meghatározott TeX-fájlon fut. A TeX bemenet és kimenet jobb megértéséhez tanulja meg a [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) dokumentumot."
p2: "Mint ismeretes, a TeX fő célja a matematikai vagy technikai szövegírás létrehozásának elősegítése. De minden manipuláció előtt először be kell tölteni a fájlt. Itt olyan kódrészleteket talál, amelyek elmagyarázzák, hogyan lehet a TeX forrásfájlokat betölteni a lemezről a fájlrendszer-könyvtárak használatával a bemenetre és a kimenetre, az XPS-eszközre történő kimenetre, a terminál kimenetének a konzolra való írására."
p3: "A példák futtatásához szükségünk van:"
p4: "Aspose.TeX for .NET API, amely funkciókban gazdag, hatékony és könnyen használható dokumentumkezelési és -konverziós API C# platformhoz."
p5: "Nyissa meg a NuGet csomagkezelőt, keresse meg az Aspose.TeX fájlt, és telepítse. A következő parancsot is használhatja a Package Manager konzolból."
---

{{<section feature1>}}
---
title: A TeX C# lemezről való betöltésének lépései.
h3: "C# kód a TeX betöltéséhez"
item1: "Hozzon létre konverziós beállításokat egyéni formátumhoz az ObjectTeX motorbővítménynél a [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Osztály."
item2: "Adja meg a fájlrendszer munkakönyvtárát a bemenethez. Ehhez használja az [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) osztályt."
item3: "Adja meg a fájlrendszer munkakönyvtárát a kimenethez az [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) osztály használatával."
item4: "Adja meg a konzolt kimeneti terminálként az [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) osztály használatával."
item5: "Ha szükséges, adjon meg egy memóriaterminált kimeneti csatlakozóként. Ehhez használja az [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) osztályt."
item6: "Futtassa a feladatot [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Method for [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Finomítsa a kimenetet.
---