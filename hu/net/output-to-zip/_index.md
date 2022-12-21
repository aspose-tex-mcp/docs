---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX-ből ZIP-be | .NET API megoldás
url: /net/output-to-zip/
description: ".NET API a TeX-szel való együttműködéshez. A TeX-ből ZIP-be konvertáló lehetővé teszi a TeX-fájl elmentését a legnépszerűbb archívumként. C# példák."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: A kimenet írása ZIP-be
h2: "Mentse el a TeX fájlkonverzió eredményét ZIP formátumban C# .NET-en keresztül"
---

{{<section overview>}}
---
p1: "A TeX az egyik adatjelölő nyelvként ismert. Ez a kiadványkészlet-rendszer (számítógépes szedés) fő magja. Kérdéses, hogy a [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) fájlformátumot tekintsük, mert ez egy programozási nyelv. Másrészt pedig egy tolmácsmotor, amely megérti ezt a nyelvet. Amúgy röviden, fő célja a matematikai vagy műszaki szövegírás létrehozásának segítése. De ha a fájl már létrejött, és nem kíván további manipulációkat végezni rajta, érdemes lehet konvertálni egy másik, népszerűbb formátumba."
p2: "Az Aspose.TeX API megoldás a különböző egyéb szolgáltatások mellett lehetővé teszi a TeX fájlok konvertálását, majd az eredmény ZIP archívumként történő mentését. Itt talál egy kódrészletet arról, hogyan lehet a TeX-et PDF-be konvertálni, és az eredmény kimenetét zip-be menteni. Az API konverter átalakítja a TeX-et a C# által támogatott bármely nyelv használatával. Az itt látható API saját, többplatformos alkalmazás létrehozására is használható, vagy integrálható a .NET-projektbe. Ilyen [*cross-platform converter*](https://products.aspose.app/tex/conversion/tex) az Aspose ökoszisztémában is jelen vannak. De a példák futtatásához szükségünk van:"
p3: "Aspose.TeX for .NET API, amely funkciókban gazdag, hatékony és könnyen használható dokumentumkezelési és -konverziós API C# platformhoz."
p4: "Nyissa meg a NuGet csomagkezelőt, keresse meg az Aspose.TeX fájlt, és telepítse. A következő parancsot is használhatja a Package Manager konzolból."
---

{{<section feature1>}}
---
title: A ZIP-könyvtárak használatának lépései a C# kimeneti TeX-fájlhoz.
h3: "C# kód a ZIP könyvtárak használatához a kimenethez"
item1: "Hozza létre a  példányát [*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "Adjon meg egy ZIP archív munkakönyvtárat a kimenethez az [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) tulajdonság használatával."
item3: "Adja meg a konzolt kimeneti terminálként az [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) osztály használatával."
item4: "Határozza meg a mentési beállításokat a [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) osztály használatával."
item5: "Futtassa az átalakítást a [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) módszerrel a  számára [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: Finomítsa a kimenetet.
item7: "A kimeneti ZIP-archívum véglegesítéséhez használja az [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) osztályt."
---