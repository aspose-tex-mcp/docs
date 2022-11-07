---
translation: true
template: /_templates/_customize-output-net.md
title: Vytvořit vlastní výstup TeX | Řešení .NET API
url: /net/customize-output/
description: ".NET API Řešení pro práci s TeXem. Přečtěte si příklad, jak vytvořit vlastní výstup pro soubor TeX s několika řádky kódu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Přizpůsobte výstup
h2: ".NET API Řešení pro přizpůsobení výstupu souborů TeX"
---

{{<section overview>}}
---
p1: "TeX je známý jako sázecí jazyk. Znamená to, že text v dokumentu neformátujete, ale zadáváte prostý text spolu s příkazy."
p2: "Článek [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) v Dokumentaci nás učí, že TeXový soubor nemusí obsahovat žádná data k sazbě, ale pouze kontrolní sekvence. . Obvykle však taková data obsahuje a soubor v cílovém formátu má vysázený text. Soubor bude mít také stejný název jako soubor zadaný jako vstupní a je hlavním výstupním souborem. Pro původní TeX je to soubor ve formátu DVI. Budeme volat název vstupního i výstupního souboru bez rozšíření názvu úlohy."
p3: "Na této stránce najdete příklad kódu vysvětlující vytvoření vlastního souboru formátu TeX, kde můžete vidět, jak upravit výstup souborů TeX. K přizpůsobení výstupu souborů .tex potřebujeme:"
p4: "Aspose.TeX for .NET API, což je funkčně bohaté, výkonné a snadno použitelné rozhraní API pro manipulaci a konverzi dokumentů pro platformu C#."
p5: "Otevřete správce balíčků NuGet, vyhledejte Aspose.TeX a nainstalujte. Můžete také použít následující příkaz z konzoly Správce balíčků."
---

{{<section feature1>}}
---
title: "Kroky k přizpůsobení výstupu TeX C#:"
h3: "C# Kód pro přizpůsobení výstupu TeX"
item1: "S pomocí metody [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) metody [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Třída, vytvoří možnosti enginu TeX pro žádný formát na rozšíření enginu ObjectTeX."
item2: "Pomocí třídy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) zadejte pracovní adresář systému souborů pro vstup."
item3: "Pomocí třídy [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) zadejte pracovní adresář systému souborů pro výstup."
item4: "K vytvoření nového formátu použijte metodu [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Upřesněte výstup.
---