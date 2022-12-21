---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX do ZIP C# | Řešení .NET API
url: /net/output-to-zip/
description: ".NET API Řešení pro práci s TeXem. Funkce konverze TeX do ZIP vám umožňuje uložit soubor TeX jako nejoblíbenější archiv. C# příklady této funkce."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Zapište výstup do ZIP
h2: "Uložte výsledek převodu souborů TeX jako ZIP přes C# .NET"
---

{{<section overview>}}
---
p1: "TeX je známý jako jeden z datových značkovacích jazyků. Je hlavním jádrem systému publikační sady (počítačová sazba). Je sporné považovat [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) za souborový formát, protože se jedná o programovací jazyk. A na druhou stranu je to překladač, který tomuto jazyku rozumí. Každopádně jeho hlavním účelem je zkrátka pomoci s tvorbou matematického nebo technického psaní textu. Ale když je soubor již vytvořen a nechcete s ním dále manipulovat, možná jej budete chtít převést do jiného, ​​populárnějšího formátu."
p2: "Řešení Aspose.TeX API mezi různými dalšími funkcemi umožňuje konverzi souborů TeX a následné uložení výsledku jako ZIP archiv. Zde najdete úryvek kódu, jak převést TeX do PDF a uložit výstup výsledku do zipu. API převodník transformuje TeX pomocí libovolného jazyka podporovaného C#. Rozhraní API, které zde vidíte, lze také použít k vytvoření vlastní aplikace pro více platforem nebo k integraci do vašeho projektu .NET. Takové [*meziplatformní konvertory*](https://products.aspose.app/tex/conversion/tex) jsou také přítomny v ekosystému Aspose. K provedení příkladů však potřebujeme:"
p3: "Aspose.TeX for .NET API, což je funkčně bohaté, výkonné a snadno použitelné rozhraní API pro manipulaci a konverzi dokumentů pro platformu C#."
p4: "Otevřete správce balíčků NuGet, vyhledejte Aspose.TeX a nainstalujte. Můžete také použít následující příkaz z konzoly Správce balíčků."
---

{{<section feature1>}}
---
title: Kroky k použití adresářů ZIP pro výstupní soubor TeX C#.
h3: "C# Kód pro použití ZIP adresářů pro výstup"
item1: "Vytvořte instanci [*Třídy TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "Určete pracovní adresář ZIP archivu pro výstup pomocí vlastnosti [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)."
item3: "Určete konzolu jako výstupní terminál pomocí třídy [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item4: "Definujte možnosti ukládání pomocí třídy [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item5: "Spusťte převod pomocí metody [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) pro [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: Upřesněte výstup.
item7: "K finalizaci výstupního archivu ZIP použijte třídu [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
---