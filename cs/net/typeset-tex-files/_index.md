---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: Funkce sazby TeX C# | .NET API
url: /net/typeset-tex-files/
description: ".NET API Řešení pro práci s TeXem. Naučte se na příkladu, jak vytvořit sazbu TeX pomocí několika řádků kódu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Sazba souborů TeX
h2: "Nastavte soubor TeX pomocí vlastního formátu TeX C# .NET"
---

{{<section overview>}}
---
p1: "TeX je známý jako jeden z datových značkovacích jazyků a/nebo sazebních jazyků zároveň. Znamená to, že text v dokumentu neformátujete, ale zadáváte prostý text spolu s příkazy. Jako výstup získáte naformátovaný soubor potřebného (specifikovaného) formátu. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) je ústředním jádrem systému sady publikací (počítačová sazba)."
p2: "Chcete-li lépe porozumět sazbě TeXu, přečtěte si [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) v dokumentaci. A na této stránce najdete úryvky kódu vysvětlující, jak vysázet soubor TeX pomocí vlastního formátu TeX."
p3: "Pro spuštění příkladů potřebujeme:"
p4: "Aspose.TeX for .NET API, což je funkčně bohaté, výkonné a snadno použitelné rozhraní API pro manipulaci a konverzi dokumentů pro platformu C#."
p5: "Otevřete správce balíčků NuGet, vyhledejte Aspose.TeX a nainstalujte. Můžete také použít následující příkaz z konzoly Správce balíčků."
---

{{<section feature1>}}
---
title: Kroky k sazbě TeXu pomocí C#.
h3: "C# Kód pro sazbu TeXu"
item1: "Vytvořte poskytovatele formátu pomocí třídy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Vytvořte možnosti převodu pro vlastní formát na rozšíření modulu ObjectTeX pomocí [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoda [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Třída."
item3: "Pokud hlavní vstup není poskytován jako proud, zadejte pracovní adresář vstupu. K tomu použijte třídu [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item4: "Zadejte pracovní adresář systému souborů pro výstup. K tomu použijte třídu [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Spusťte úlohu [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metoda pro [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Upřesněte výstup.
---