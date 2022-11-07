---
translation: true
template: /_templates/_customize-input-net.md
title: Vytvořit vlastní vstup TeX | Řešení .NET API
url: /net/customize-input/
description: ".NET API Řešení pro práci s TeXem. Na příkladu se dozvíte, jak vytvořit vlastní vstup pro soubor TeX pomocí několika řádků kódu C#."
keywords: vlastní vstup tex net api, C# api pro přizpůsobení tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Přizpůsobte vstup
h2: ".NET API Řešení pro přizpůsobení vstupu souborů TeX"
---

{{<section overview>}}
---
p1: "TeX je známý jako sázecí jazyk. Znamená to, že text v dokumentu neformátujete, ale zadáváte prostý text spolu s příkazy. Jak je popsáno v článku [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) v dokumentaci, úloha TeX běží na explicitně specifikovaném souboru TeX. Takže tento soubor zahrneme do vstupu určité úlohy TeX."
p2: "Na této stránce najdete příklad kódu vysvětlující, jak upravit vstup zdrojových souborů TeX s ohledem na to, že vstup by měl odpovídat syntaxi TeXu a v ideálním případě by měl obsahovat pouze příkazy známé enginu."
p3: "K přizpůsobení vstupu souborů .tex potřebujeme:"
p4: "Aspose.TeX for .NET API, což je funkčně bohaté, výkonné a snadno použitelné rozhraní API pro manipulaci a konverzi dokumentů pro platformu C#."
p5: "Otevřete správce balíčků NuGet, vyhledejte Aspose.TeX a nainstalujte. Můžete také použít následující příkaz z konzoly Správce balíčků."
---

{{<section feature1>}}
---
title: "Kroky k přizpůsobení vstupu TeX C#:"
h3: "C# Kód pro přizpůsobení vstupu TeX"
item1: "Použití [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoda [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Třída, vytvoří možnosti TeX motoru pro žádný formát na rozšíření ObjectTeX motoru."
item2: "Pomocí třídy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) zadejte pracovní adresář systému souborů pro vstup."
item3: "Pomocí metody [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) vytvořte přizpůsobený formát."
---