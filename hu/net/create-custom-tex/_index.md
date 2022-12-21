---
translation: true
template: /_templates/_create-custom-tex-net.md
title: Egyedi TeX fájlok | .NET API megoldás
url: /net/create-custom-tex/
description: ".NET API a TeX-szel való együttműködéshez. Tartalmazza az egyéni TeX formátumok létrehozásának funkcióját. C# példák a TeX testreszabásához szükséges."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Hozzon létre egyéni TeX formátumot
h2: "Készítsen egyedi TeX formátumú fájlt C# .NET-en keresztül"
---

{{<section overview>}}
---
p1: "A TeX az egyik adatjelölő nyelvként ismert. Ez a kiadványkészlet-rendszer (számítógépes szedés) fő magja. Kérdéses, hogy a [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) fájlformátumot tekintsük, mert ez egy programozási nyelv. Másrészt pedig egy tolmácsmotor, amely megérti ezt a nyelvet. Amúgy röviden, fő célja a matematikai vagy műszaki szövegírás létrehozásának segítése. Sok különböző csomagot hoztak létre a ΤeΧ alapján. Céljuk, hogy megkönnyítsék a dokumentumok feldolgozását, különösen, ha képletekkel vagy matematikai egyenletekkel rendelkeznek."
p2: "Az Aspose.TeX API megoldás a különböző egyéb szolgáltatások mellett lehetővé teszi saját kiemelt TeX fájlok létrehozását. Itt olyan információkat talál, amelyek elmagyarázzák, hogyan hozhat létre ilyen testreszabott formátumú fájlokat. Egy ilyen fájl testreszabott motorbeállításokkal rendelkezik. Ehhez szükségünk van:"
p3: "Aspose.TeX for .NET API, amely funkciókban gazdag, hatékony és könnyen használható dokumentumkezelési és -konverziós API C# platformhoz."
p4: "Nyissa meg a NuGet csomagkezelőt, keresse meg az Aspose.TeX fájlt, és telepítse. A következő parancsot is használhatja a Package Manager konzolból."
---

{{<section feature1>}}
---
title: Egyéni C# TeX-fájl létrehozásának lépései.
h3: "C# kód a TeX fájlok testreszabásához"
item1: "A [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions)  módszerének használata [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Osztály, hozzon létre TeX motor opciókat formátum nélkül az ObjectTeX motor bővítésekor."
item2: "Az [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) osztály használatával adja meg a fájlrendszer munkakönyvtárát a bemenethez."
item3: "Használja az [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) osztályt a fájlrendszer munkakönyvtárának megadásához a kimenethez."
item4: "Hozza létre a formátumot a [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) módszerrel."
item5: Finomítsa a kimenetet.
---