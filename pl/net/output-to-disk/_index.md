---
translation: true
template: /_templates/_output-to-disk-net.md
title: Zapisz wyjście TeX na dysk | API .NET
url: /net/output-to-disk/
description: "Rozwiązanie .NET API do pracy z TeX-em. Dowiedz się na przykładzie, jak utworzyć niestandardowe wyjście dla pliku TeX za pomocą kilku linijek kodu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Zapisz wyjście TeX na dysk
h2: "Zapisz wynik konwersji pliku TeX jako dysk za pomocą C# .NET"
---

{{<section overview>}}
---
p1: "TeX jest znany jako język składu, co oznacza, że ​​nie formatujesz tekstu w dokumencie, ale wprowadzasz zwykły tekst wraz z poleceniami. Jak wiadomo z artykułu [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) w Dokumentacji, zadanie TeX działa na jawnie określonym pliku TeX. Można tam również znaleźć informacje na temat trybów interakcji TeX-owych i prymitywów związanych z wejściem i wyjściem TeX-a."
p2: "Głównym zastosowaniem TeXa jest pomoc w tworzeniu tekstów matematycznych lub technicznych. Ale kiedy plik jest już utworzony i nie chcesz na nim żadnych dalszych manipulacji, możesz przekonwertować go na inny, bardziej popularny format."
p3: "Na tej stronie znajdziesz przykład kodu wyjaśniający użycie katalogów systemu plików dla wejścia i wyjścia, wyjście do urządzenia XPS, nadpisanie nazwy zadania, zapisanie wyjścia terminala na dysk. W prostych słowach jest to konwersja z zapisem wyjścia na dysk. Do przeprowadzenia takiej operacji potrzebujemy:"
p4: "Aspose.TeX dla .NET API, który jest bogatym w funkcje, wydajnym i łatwym w użyciu interfejsem API do manipulacji i konwersji dokumentów dla platformy C#."
p5: "Otwórz Menedżera pakietów NuGet i wyszukaj Aspose.TeX i zainstaluj. Możesz również użyć następującego polecenia z konsoli Menedżera pakietów."
---

{{<section feature1>}}
---
title: "Kroki, aby zapisać dane wyjściowe terminala na dysku C#:"
h3: "Kod C# do konwersji TeXa i zapisywania danych wyjściowych na dysk"
item1: "Utwórz opcje konwersji w rozszerzeniu silnika ObjectTeX przy użyciu metody [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) metody [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasa."
item2: "Podaj nazwę zadania, jeśli nie chcesz, aby pierwszy argument konstruktora TeXJob był traktowany jako nazwa zadania."
item3: "Określ katalog roboczy systemu plików dla danych wejściowych. W tym celu użyj klasy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item4: "Określ katalog roboczy systemu plików dla danych wyjściowych za pomocą jednostek klasy [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Określ, że dane wyjściowe terminala muszą być zapisane do pliku w wyjściowym katalogu roboczym."
item6: "Uruchom zadanie [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metoda dla [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---