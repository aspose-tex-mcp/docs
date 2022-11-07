---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Ładowanie TeXa z ZIP | Rozwiązanie API .NET
url: /net/load-tex-from-zip/
description: "Rozwiązanie .NET API do pracy z TeX-em. Dowiedz się na przykładzie, jak załadować plik TeX z ZIP za pomocą kilku linijek kodu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Załaduj pliki źródłowe TeX z ZIP
h2: "Rozwiązanie .NET API do ładowania plików TeX z archiwum ZIP"
---

{{<section overview>}}
---
p1: "TeX jest znany jako język składu. Oznacza to, że nie formatujesz tekstu w dokumencie, ale wprowadzasz zwykły tekst wraz z poleceniami. Jako wynik otrzymasz sformatowany plik o wymaganym (określonym) formacie. Aby lepiej zrozumieć wejścia i wyjścia TeX, zapoznaj się z [*We/Wy*](https://docs.aspose.com/tex/net/tex-io/) dokumentacji."
p2: "Jak wiadomo, głównym celem TeX-a jest pomoc w pisaniu tekstów matematycznych lub technicznych. Ale przed jakimikolwiek manipulacjami plik należy najpierw załadować. Tutaj znajdziesz fragmenty kodu wyjaśniające, jak załadować pliki źródłowe TeX z ZIP za pomocą katalogów ZIP dla wejścia i wyjścia, wyjścia do urządzenia PDF, zapisania wyjścia terminala do konsoli."
p3: "Aby wczytać pliki .tex potrzebujemy:"
p4: "Aspose.TeX dla .NET API, który jest bogatym w funkcje, wydajnym i łatwym w użyciu interfejsem API do manipulacji i konwersji dokumentów dla platformy C#."
p5: "Otwórz Menedżera pakietów NuGet i wyszukaj Aspose.TeX i zainstaluj. Możesz również użyć następującego polecenia z konsoli Menedżera pakietów."
---

{{<section feature1>}}
---
title: "Kroki, aby załadować TeX z archiwum ZIP C#:"
h3: "Kod C# do ładowania TeX"
item1: "Otwórz strumień w archiwum ZIP, aby użyć go jako wejściowego katalogu roboczego."
item2: "Otwórz strumień w archiwum ZIP, aby użyć go jako wyjściowego katalogu roboczego."
item3: "Utwórz opcje konwersji dla domyślnego formatu ObjectTeX w rozszerzeniu silnika ObjectTeX za pomocą [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoda [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasa."
item4: "Określ katalog roboczy archiwum ZIP dla danych wejściowych lub/i określ ścieżkę wewnątrz archiwum. W tym celu użyj konstruktorów klasy [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/)."
item5: "Określ katalog roboczy archiwum ZIP dla danych wyjściowych lub/i określ ścieżkę wewnątrz archiwum. W tym celu użyj konstruktorów klasy [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
item6: "Określ konsolę jako terminal wyjściowy, używając klasy [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item7: "Zdefiniuj opcje zapisywania za pomocą klasy [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Uruchom zadanie [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metoda dla [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Popraw wyniki.
---