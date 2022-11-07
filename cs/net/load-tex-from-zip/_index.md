---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Načítání TeXu ze ZIP | Řešení .NET API
url: /net/load-tex-from-zip/
description: ".NET API Řešení pro práci s TeXem. Na příkladu se dozvíte, jak načíst soubor TeX ze ZIP pomocí několika řádků kódu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Načtěte zdrojové soubory TeX ze ZIP
h2: ".NET API Řešení pro načítání souborů TeX ze ZIP archivu"
---

{{<section overview>}}
---
p1: "TeX je známý jako sázecí jazyk. Znamená to, že text v dokumentu neformátujete, ale zadáváte prostý text spolu s příkazy. Jako výstup získáte naformátovaný soubor potřebného (specifikovaného) formátu. Chcete-li lépe porozumět vstupu a výstupu TeXu, přečtěte si [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) v dokumentaci."
p2: "Jak je známo, hlavním účelem TeXu je pomáhat vytvářet matematické nebo technické texty. Ale před jakoukoli manipulací by měl být soubor nejprve načten. Zde najdete úryvky kódu vysvětlující, jak načíst zdrojové soubory TeX ze ZIP pomocí adresářů ZIP pro vstup a výstup, výstup do zařízení PDF, zápis terminálového výstupu do konzole."
p3: "K načtení souborů .tex potřebujeme:"
p4: "Aspose.TeX for .NET API, což je funkčně bohaté, výkonné a snadno použitelné rozhraní API pro manipulaci a konverzi dokumentů pro platformu C#."
p5: "Otevřete správce balíčků NuGet, vyhledejte Aspose.TeX a nainstalujte. Můžete také použít následující příkaz z konzoly Správce balíčků."
---

{{<section feature1>}}
---
title: "Kroky k načtení TeXu z archivu ZIP C#:"
h3: "C# Kód pro načtení TeXu"
item1: "Otevřete stream v archivu ZIP a použijte jej jako vstupní pracovní adresář."
item2: "Otevřete stream v archivu ZIP a použijte jej jako výstupní pracovní adresář."
item3: "Vytvořte možnosti převodu pro výchozí formát ObjectTeX na rozšíření modulu ObjectTeX pomocí [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoda [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Třída."
item4: "Zadejte pracovní adresář archivu ZIP pro vstup nebo/a zadejte cestu uvnitř archivu. K tomu použijte konstruktory třídy [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/)."
item5: "Zadejte pracovní adresář archivu ZIP pro výstup nebo/a zadejte cestu uvnitř archivu. K tomu použijte konstruktory třídy [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
item6: "Určete konzolu jako výstupní terminál pomocí třídy [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item7: "Definujte možnosti ukládání pomocí třídy [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Spusťte úlohu [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metoda pro [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Upřesněte výstup.
---