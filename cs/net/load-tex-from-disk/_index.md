---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Načítání TeXu z disku | Řešení .NET API
url: /net/load-tex-from-disk/
description: ".NET API Řešení pro práci s TeXem. Na příkladu se dozvíte, jak načíst soubor TeX z disku pomocí několika řádků kódu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Načtěte zdrojové soubory TeXu z disku
h2: ".NET API Řešení pro načítání souborů TeX/LaTeX z disku"
---

{{<section overview>}}
---
p1: "TeX je známý jako sázecí jazyk. Znamená to, že text v dokumentu neformátujete, ale zadáváte prostý text spolu s příkazy. Jako výstup získáte naformátovaný soubor potřebného (specifikovaného) formátu. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) je ústředním jádrem systému sady publikací (počítačová sazba). Úloha TeX běží na explicitně specifikovaném souboru TeX. Chcete-li lépe porozumět vstupu a výstupu TeXu, přečtěte si [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) v dokumentaci."
p2: "Jak je známo, hlavním účelem TeXu je pomáhat vytvářet matematické nebo technické texty. Ale před jakoukoli manipulací by měl být soubor nejprve načten. Zde najdete úryvky kódu vysvětlující, jak načíst zdrojové soubory TeXu z disku pomocí adresářů souborového systému pro vstup a výstup, výstup na zařízení XPS, zápis terminálového výstupu do konzole."
p3: "Pro spuštění příkladů potřebujeme:"
p4: "Aspose.TeX for .NET API, což je funkčně bohaté, výkonné a snadno použitelné rozhraní API pro manipulaci a konverzi dokumentů pro platformu C#."
p5: "Otevřete správce balíčků NuGet, vyhledejte Aspose.TeX a nainstalujte. Můžete také použít následující příkaz z konzoly Správce balíčků."
---

{{<section feature1>}}
---
title: Kroky k načtení TeXu z disku C#.
h3: "C# Kód pro načtení TeXu"
item1: "Vytvořte možnosti převodu pro vlastní formát na rozšíření modulu ObjectTeX pomocí [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoda [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Třída."
item2: "Zadejte pracovní adresář systému souborů pro vstup. K tomu použijte třídu [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item3: "Určete pracovní adresář systému souborů pro výstup pomocí třídy [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Určete konzolu jako výstupní terminál pomocí třídy [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "V případě potřeby zadejte jako výstupní svorku paměť. K tomu použijte třídu [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Spusťte úlohu [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metoda pro [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Upřesněte výstup.
---