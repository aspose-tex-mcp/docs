---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: Funkcjonalność składu TeXa | .NET API
url: /net/typeset-tex-files/
description: "Rozwiązanie .NET API do pracy z TeX-em. Dowiedz się na przykładzie, jak tworzyć składy TeX za pomocą kilku linijek kodu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Składanie plików TeX
h2: "Złóż plik TeX przy użyciu niestandardowego formatu TeX C# .NET"
---

{{<section overview>}}
---
p1: "TeX jest znany jako jeden z języków znaczników danych i/lub jednocześnie jako język składu. Oznacza to, że nie formatujesz tekstu w dokumencie, ale wprowadzasz zwykły tekst wraz z poleceniami. Jako wynik otrzymasz sformatowany plik o wymaganym (określonym) formacie. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) to centralny rdzeń systemu zbiorów publikacji (skład komputerowy)."
p2: "Aby lepiej zrozumieć skład tekstu TeX, zapoznaj się z [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) w dokumentacji. Na tej stronie znajdziesz fragmenty kodu wyjaśniające, jak złożyć plik TeX przy użyciu niestandardowego formatu TeX."
p3: "Do uruchomienia przykładów potrzebujemy:"
p4: "Aspose.TeX dla .NET API, który jest bogatym w funkcje, wydajnym i łatwym w użyciu interfejsem API do manipulacji i konwersji dokumentów dla platformy C#."
p5: "Otwórz Menedżera pakietów NuGet i wyszukaj Aspose.TeX i zainstaluj. Możesz również użyć następującego polecenia z konsoli Menedżera pakietów."
---

{{<section feature1>}}
---
title: Kroki składania TeXa za pomocą C#.
h3: "Kod C# do składu TeX"
item1: "Utwórz dostawcę formatu przy użyciu klasy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Utwórz opcje konwersji dla niestandardowego formatu w rozszerzeniu silnika ObjectTeX za pomocą [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metoda [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasa."
item3: "Określ wejściowy katalog roboczy, jeśli główne dane wejściowe nie są dostarczane jako strumień. W tym celu użyj klasy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item4: "Określ katalog roboczy systemu plików dla danych wyjściowych. W tym celu użyj klasy [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Uruchom zadanie [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metoda dla [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Popraw wyniki.
---