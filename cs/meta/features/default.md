---
meta: true
translation: true
deploy: false
---

{{<section faqcreatecustomtex>}}
---
qs[1].name: "Co je šablona LaTeX?"
qs[1].text: "Šablona je uložená sada vlastností, nastavení nebo struktury, kterou lze použít na nově vytvořený dokument a ušetřit tak čas. Pro LaTeX na může být soubor, který obsahuje informace o formátu stránky, fontech, třídě dokumentu, obsažených balíčcích atd."
qs[2].name: "Jak mohu používat šablony LaTeX?"
qs[2].text: "Pokud nepoužíváte žádný další software a šablona je pouze soubor .tex, stačí ji otevřít a začít pracovat. Mějte na paměti, že změny neukládáte přímo do tohoto dokumentu, ale použijete možnost Uložit jako."
qs[3].name: "Jak nastavit typ dokumentu LaTeX?"
qs[3].text: "Chcete-li zadat typ dokumentu v LaTeXu, jako je článek, kniha nebo prezentace, použijte příkaz `documentclass{article}`."
qs[4].name: "Jak vytvořit vlastní formát TeX?"
qs[4].text: "Chcete-li vytvořit vlastní formát TeX pomocí řešení Aspose.TeX API, musíte vytvořit možnosti enginu TeX. Poté zadejte pracovní adresář systému souborů pro vstup a výstup a vytvořte formát pomocí metody *TeXJob.CreateFormat()*."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqcustominput>}}
---
qs[1].name: "Jak se dostanu do TeXu?"
qs[1].text: "Chcete-li zadat jakýkoli vstup do souboru TeX, použijte příkazy `input` a `include`. Například příkaz `input<název souboru>` přidá soubor se zadaným názvem do souboru TeX."
qs[2].name: "Jak vytvořím soubor TeX?"
qs[2].text: "Za tímto účelem vytvořte možnosti TeX motoru bez formátu na rozšíření *ObjectTeX* pomocí metody *ConsoleAppOptions()* třídy *TeXOptions Class*."
qs[3].name: "Jak pracovat se vstupem TeXového souboru?"
qs[3].text: "Chcete-li manipulovat se vstupem TeXu pomocí řešení Aspose.TeX API, použijte vstupní třídy [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) jmenný prostor."
qs[4].name: "Jak upravit vstup souboru TeX?"
qs[4].text: "Chcete-li upravit vstup souboru TeX pomocí tohoto řešení API, musíte vytvořit možnosti enginu TeX. Poté zadejte pracovní adresář systému souborů pro vstup pomocí třídy *InputFileSystemDirectory*."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqcustomoutput>}}
---
qs[1].name: "Jak vytvořím soubor LaTeX?"
qs[1].text: "Řešení Aspose.TeX vám umožňuje vytvořit soubor LaTeX online. Stačí použít jednu z [meziplatformních aplikací](https://products.aspose.app/tex/applications): LaTeX Equation Editor, LaTeX Editor nebo LaTeX Table Generator. Umožňují vám generovat soubory během několika okamžiků."
qs[2].name: "Jak pracovat s výstupem TeXového souboru?"
qs[2].text: "Chcete-li manipulovat s výstupem TeXu pomocí řešení Aspose.TeX API, použijte výstupní třídy [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) jmenný prostor."
qs[3].name: "Jak zobrazím výstup LaTeXu?"
qs[3].text: "Pro zobrazení souborů TeX/LaTeX online existují bezplatné aplikace [Viewer](https://products.aspose.app/tex/viewer). S nimi budete muset pouze nahrát soubory a získat výsledek na obrazovce během okamžiku."
qs[4].name: "Jak upravit výstup souboru TeX?"
qs[4].text: "Chcete-li upravit výstup souboru TeX pomocí tohoto řešení API, musíte vytvořit možnosti enginu TeX. Poté zadejte pracovní adresář systému souborů pro vstup pomocí třídy *OutputFileSystemDirectory*."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqloadfromdisc>}}
---
qs[1].name: "Jak mohu číst soubory TeX online?"
qs[1].text: "Pro čtení souborů TeX online existuje bezplatná aplikace [Viewer](https://products.aspose.app/tex/viewer). S ním budete muset pouze nahrát soubory a získat výsledek na obrazovce během okamžiku. Můžete také použít [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics), který vám také umožní zobrazit a přidat LaTeXový kód souboru."
qs[2].name: "Jak otevřu soubor LaTeX ve Wordu?"
qs[2].text: "Nejjednodušší způsob, jak toho dosáhnout, je převést LaTeX na Word pomocí našeho webového [Converter](https://products.aspose.app/tex/conversion/latex). Poté budete moci používat obsah vašeho souboru v MS Word."
qs[3].name: "Jak načtu TeX soubor z disku?"
qs[3].text: "Nejprve vytvořte možnosti převodu pomocí *ConsoleAppOptions()*. Poté zadejte pracovní adresář systému souborů pro vstup a výstup. Zadejte konzolu jako výstupní terminál a spusťte úlohu."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqloadfromzip>}}
---
qs[1].name: "Jaké třídy se používají k načtení souboru TeX ze ZIP?"
qs[1].text: "Chcete-li manipulovat s výstupem/vstupem souborů TeX načtených ze ZIP, použijte třídy ZipDirectory třídy [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) jmenný prostor."
qs[2].name: "Jak nainstaluji balíček TeX?"
qs[2].text: "Za tímto účelem otevřete správce balíčků NuGet a vyhledejte Aspose.TeX a nainstalujte nebo použijte následující příkaz z konzoly správce balíčků."
qs[3].name: "Jak načtu soubor TeX ze ZIP?"
qs[3].text: "Otevřete stream v archivu ZIP pro vstup a výstup. Poté vytvořte možnosti převodu pomocí *ConsoleAppOptions()*. Dále zadejte pracovní adresář ZIP archivu pro vstup a výstup. Zadejte konzolu jako výstupní terminál, definujte možnosti uložení a spusťte úlohu."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqloadlicense>}}
---
qs[1].name: "Jaký je rozdíl mezi TeXem a LaTeXem?"
qs[1].text: "TeX je značkovací nebo sázecí jazyk, kdy LaTeX je nejznámější balík TeXu, který obsahuje mnoho užitečných nástrojů pro publikaci."
qs[2].name: "Jak načíst TeX licenci?"
qs[2].text: "Chcete-li načíst licenci TeX pomocí tohoto řešení API, musíte inicializovat licenční objekt pomocí třídy *Licence*. Poté nastavte licenci pomocí metody *SetLicense()*."
qs[3].name: "Jak spravovat licence s tímto řešením API?"
qs[3].text: "K licencování komponenty použijte entity třídy [*Licence*](https://reference.aspose.com/tex/net/aspose.tex/license/)."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqoutputtodisk>}}
---
qs[1].name: "Mohu transformovat soubory TeX do PDF?"
qs[1].text: "Ano, toto řešení API takovou funkcionalitu podporuje. Budete potřebovat jmenný prostor *Aspose.TeX.Presentation.Pdf*, který poskytuje třídy pro sazbu souborů TeX do PDF."
qs[2].name: "Mohu zapsat výstup z TeXu na disk?"
qs[2].text: "Toto řešení API takovou funkcionalitu zahrnuje. K tomu použijte třídu *OutputFileSystemDirectory*, která implementuje metodu běžného souborového systému pro získání datového proudu souborů, do kterého se bude zapisovat."
qs[3].name: "Jak zapsat výstup z TeXu na disk?"
qs[3].text: "Nejprve vytvořte možnosti převodu pomocí *ConsoleAppOptions()*. Dále zadejte pracovní adresář systému souborů pro vstup a výstup. Všimněte si, že výstup terminálu musí být zapsán do souboru ve výstupním pracovním adresáři a spustit úlohu."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqoutputtozip>}}
---
qs[1].name: "Jak zobrazím výstup TeX?"
qs[1].text: "Chcete-li otevřít a zobrazit obsah souboru TeX online, použijte multiplatformní [TeX Viewer](https://products.aspose.app/tex/viewer/tex). Umožní vám také uložit soubor jako obrázek."
qs[2].name: "Mohu zapsat výstup z TeXu do archivu ZIP?"
qs[2].text: "Ano, toto řešení API takovou funkcionalitu podporuje. Budete potřebovat *OutputZipDirectoryClass*, který implementuje metodu pro získání datového proudu souborů pro zápis, když je pracovním adresářem archiv ZIP."
qs[3].name: "Jak zapsat výstup z TeXu do archivu ZIP?"
qs[3].text: "Vytvořte instanci třídy *TeXOptions Class*. Poté zadejte pracovní adresář ZIP archivu pro výstup a konzolu jako výstupní terminál. Zadejte možnosti uložení a spusťte převod. Nakonec zapište výstup do ZIP pomocí třídy *OutputZipDirectory*."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqtypesettex>}}
---
qs[1].name: "Co je sazba v LaTeXu?"
qs[1].text: "LaTeX podporuje různé sázecí funkce užitečné pro autory dokumentů nazývané balíčky. V těchto balíčcích najdete pokročilé nástroje pro matematické vzorce, kreslení grafiky, vytváření tabulek a šablon atd."
qs[2].name: "Je LaTeX sázecí software?"
qs[2].text: "Ano, LaTeX je sázecí software a je široce používán pro vytváření různých typů propracovaných dokumentů, jako jsou vědecké práce, články, semestrální práce, knihy a mnoho dalších."
qs[3].name: "Jak vysázet soubory TeX?"
qs[3].text: "Chcete-li vysázet soubory TeX pomocí řešení Aspose.TeX API, musíte nejprve vytvořit poskytovatele formátu. Vytvořte možnosti převodu pro vlastní formát pomocí rozšíření ObjectTeX engine. Poté zadejte pracovní adresář systému souborů pro vstup a výstup a vytvořte formát pomocí metody *TeXJob.CreateFormat()*."
---

{{<import path="/meta/schemas.md" section="faq">}} 

