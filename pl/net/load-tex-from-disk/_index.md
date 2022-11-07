---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Ładowanie TeXa z dysku | API .NET
url: /net/load-tex-from-disk/
description: "Rozwiązanie .NET API do pracy z TeX-em. Dowiedz się na przykładzie, jak załadować plik TeX z dysku za pomocą kilku linijek kodu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Załaduj pliki źródłowe TeX z dysku
h2: "Rozwiązanie .NET API do ładowania plików TeX/LaTeX z dysku"
---

{{<section overview>}}
---
p1: "TeX jest znany jako język składu. Oznacza to, że nie formatujesz tekstu w dokumencie, ale wprowadzasz zwykły tekst wraz z poleceniami. Jako wynik otrzymasz sformatowany plik o wymaganym (określonym) formacie. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) to centralny rdzeń systemu zbiorów publikacji (skład komputerowy). Zadanie TeX działa na jawnie określonym pliku TeX. Aby lepiej zrozumieć wejścia i wyjścia TeX, zapoznaj się z [*We/Wy*](https://docs.aspose.com/tex/net/tex-io/) dokumentacji."
p2: "Jak wiadomo, głównym celem TeX-a jest pomoc w pisaniu tekstów matematycznych lub technicznych. Ale przed jakimikolwiek manipulacjami plik należy najpierw załadować. Tutaj znajdziesz fragmenty kodu wyjaśniające, jak załadować pliki źródłowe TeXa z dysku za pomocą katalogów systemu plików dla wejścia i wyjścia, wyjścia do urządzenia XPS, zapisania wyjścia terminala do konsoli."
p3: "Do uruchomienia przykładów potrzebujemy:"
p4: "Aspose.TeX dla .NET API, który jest bogatym w funkcje, wydajnym i łatwym w użyciu interfejsem API do manipulacji i konwersji dokumentów dla platformy C#."
p5: "Otwórz Menedżera pakietów NuGet i wyszukaj Aspose.TeX i zainstaluj. Możesz również użyć następującego polecenia z konsoli Menedżera pakietów."
---

{{<section feature1>}}
---
title: Kroki ładowania TeX z dysku C#.
h3: "Kod C# do ładowania TeX"
item1: "Utwórz opcje konwersji dla niestandardowego formatu w rozszerzeniu silnika ObjectTeX za pomocą [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoda [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasa."
item2: "Określ katalog roboczy systemu plików dla danych wejściowych. W tym celu użyj klasy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item3: "Określ katalog roboczy systemu plików dla danych wyjściowych przy użyciu klasy [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Określ konsolę jako terminal wyjściowy, używając klasy [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "W razie potrzeby określ terminal pamięci jako terminal wyjściowy. W tym celu użyj klasy [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Uruchom zadanie [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metoda dla [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Popraw wyniki.
---