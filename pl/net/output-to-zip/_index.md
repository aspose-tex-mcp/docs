---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX do ZIP | Rozwiązanie API .NET
url: /net/output-to-zip/
description: "Rozwiązanie .NET API do pracy z TeX-em. Konwersji TeX do ZIP pozwala zapisać plik TeX jako najpopularniejsze archiwum. C# przykłady tej funkcjonalności."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Zapisz dane wyjściowe do ZIP
h2: "Zapisz wynik konwersji pliku TeX jako ZIP za pomocą C# .NET"
---

{{<section overview>}}
---
p1: "TeX jest znany jako jeden z języków znaczników danych. Jest to główny rdzeń systemu zbiorów publikacji (skład komputerowy). Wątpliwe jest traktowanie [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) jako formatu pliku, ponieważ jest to język programowania. Z drugiej strony jest to silnik tłumacza, który rozumie ten język. Zresztą, w skrócie, jego głównym celem jest pomoc w tworzeniu matematycznego lub technicznego pisania tekstów. Ale kiedy plik jest już utworzony i nie chcesz na nim żadnych dalszych manipulacji, możesz przekonwertować go na inny, bardziej popularny format."
p2: "Rozwiązanie Aspose.TeX API wśród różnych innych funkcji umożliwia konwersję plików TeX, a następnie zapisanie wyniku jako archiwum ZIP. Tutaj znajdziesz fragment kodu, jak przekonwertować TeX na PDF i zapisać wynik wyniku w formacie zip. Konwerter API przekształca TeX przy użyciu dowolnego języka obsługiwanego przez C#. Widoczny tutaj interfejs API może być również używany do tworzenia własnej aplikacji wieloplatformowej lub integracji z projektem .NET. Takie [*konwertery międzyplatformowe*](https://products.aspose.app/tex/conversion/tex) są również obecne w ekosystemie Aspose. Ale do uruchomienia przykładów potrzebujemy:"
p3: "Aspose.TeX dla .NET API, który jest bogatym w funkcje, wydajnym i łatwym w użyciu interfejsem API do manipulacji i konwersji dokumentów dla platformy C#."
p4: "Otwórz Menedżera pakietów NuGet i wyszukaj Aspose.TeX i zainstaluj. Możesz również użyć następującego polecenia z konsoli Menedżera pakietów."
---

{{<section feature1>}}
---
title: Kroki korzystania z katalogów ZIP do wyjściowego pliku TeX C#.
h3: "Kod C# do używania katalogów ZIP do wyjścia"
item1: "Utwórz wystąpienie [*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "Określ katalog roboczy archiwum ZIP dla danych wyjściowych za pomocą właściwości [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)."
item3: "Określ konsolę jako terminal wyjściowy przy użyciu klasy [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item4: "Zdefiniuj opcje zapisywania przy użyciu klasy [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item5: "Uruchom konwersję za pomocą metody [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) dla [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: Popraw wyniki.
item7: "Aby sfinalizować wyjściowe archiwum ZIP, użyj klasy [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
---