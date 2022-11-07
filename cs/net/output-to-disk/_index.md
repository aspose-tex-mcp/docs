---
translation: true
template: /_templates/_output-to-disk-net.md
title: Zapsat výstup TeX na disk | Řešení .NET API
url: /net/output-to-disk/
description: ".NET API Řešení pro práci s TeXem. Na příkladu se dozvíte, jak vytvořit vlastní výstup pro soubor TeX pomocí několika řádků kódu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Zapište výstup z TeXu na disk
h2: "Uložte výsledek převodu souborů TeX jako disk přes C# .NET"
---

{{<section overview>}}
---
p1: "TeX je známý jako sázecí jazyk, což znamená, že text v dokumentu neformátujete, ale zadáváte prostý text spolu s příkazy. Jak je známo z článku [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) v dokumentaci, úloha TeX běží na explicitně specifikovaném souboru TeX. Můžete zde také najít informace o režimech interakce TeX a primitivech souvisejících se vstupem a výstupem TeXu."
p2: "Hlavním využitím TeXu je pomoc s tvorbou matematického nebo technického psaní textu. Ale když je soubor již vytvořen a nechcete s ním dále manipulovat, možná jej budete chtít převést do jiného, ​​populárnějšího formátu."
p3: "Na této stránce najdete příklad kódu vysvětlující použití adresářů systému souborů pro vstup a výstup, výstup na zařízení XPS, přepsání názvu úlohy, zápis výstupu terminálu na disk. Jednoduše řečeno jde o konverzi se zápisem výstupu na disk. K provedení takové operace potřebujeme:"
p4: "Aspose.TeX for .NET API, což je funkčně bohaté, výkonné a snadno použitelné rozhraní API pro manipulaci a konverzi dokumentů pro platformu C#."
p5: "Otevřete správce balíčků NuGet, vyhledejte Aspose.TeX a nainstalujte. Můžete také použít následující příkaz z konzoly Správce balíčků."
---

{{<section feature1>}}
---
title: "Kroky k zápisu výstupu terminálu na disk C#:"
h3: "C# Kód pro konverzi TeXu a zápis výstupu na disk"
item1: "Vytvořte možnosti převodu na rozšíření enginu ObjectTeX pomocí [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoda [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Třída."
item2: "Pokud nechcete, aby byl první argument konstruktoru TeXJob považován za název úlohy, zadejte název úlohy."
item3: "Zadejte pracovní adresář systému souborů pro vstup. K tomu použijte třídu [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item4: "Určete pracovní adresář systému souborů pro výstup pomocí entit třídy [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Určete, že výstup terminálu musí být zapsán do souboru ve výstupním pracovním adresáři."
item6: "Spusťte úlohu [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metoda pro [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---