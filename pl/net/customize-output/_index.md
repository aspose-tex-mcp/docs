---
translation: true
template: /_templates/_customize-output-net.md
title: Utwórz własne wyjście TeX | API .NET
url: /net/customize-output/
description: "Rozwiązanie .NET API do pracy z TeX-em. Przeczytaj przykład, jak utworzyć niestandardowe wyjście dla pliku TeX za pomocą kilku linijek kodu C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Dostosuj wyjście
h2: "Rozwiązanie .NET API do dostosowywania danych wyjściowych plików TeX"
---

{{<section overview>}}
---
p1: "TeX jest znany jako język składu. Oznacza to, że nie formatujesz tekstu w dokumencie, ale wprowadzasz zwykły tekst wraz z poleceniami."
p2: "Artykuł [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) w dokumentacji uczy nas, że plik TeX może nie zawierać żadnych danych do złożenia, a jedynie sekwencje sterujące . Jednak zazwyczaj zawiera takie dane, a plik w formacie docelowym zawiera tekst składu. Plik będzie miał również taką samą nazwę jak plik określony jako wejściowy i będzie głównym plikiem wyjściowym. Dla oryginalnego TeX-a jest to plik w formacie DVI. Wywołamy nazwy plików wejściowych i wyjściowych bez rozszerzania nazwy zadania."
p3: "Na tej stronie znajdziesz przykład kodu wyjaśniający tworzenie niestandardowego pliku formatu TeX, w którym możesz zobaczyć, jak dostosować wyjście plików TeX. Aby dostosować wyjście plików .tex, potrzebujemy:"
p4: "Aspose.TeX dla .NET API, który jest bogatym w funkcje, wydajnym i łatwym w użyciu interfejsem API do manipulacji i konwersji dokumentów dla platformy C#."
p5: "Otwórz Menedżera pakietów NuGet i wyszukaj Aspose.TeX i zainstaluj. Możesz również użyć następującego polecenia z konsoli Menedżera pakietów."
---

{{<section feature1>}}
---
title: "Kroki, aby dostosować wyjście TeX C#:"
h3: "Kod C# do dostosowywania danych wyjściowych TeX"
item1: "Z pomocą metody [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) metody [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasa, utwórz opcje silnika TeX dla braku formatu w rozszerzeniu silnika ObjectTeX."
item2: "Użyj klasy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), aby określić katalog roboczy systemu plików dla danych wejściowych."
item3: "Użyj klasy [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), aby określić katalog roboczy systemu plików dla danych wyjściowych."
item4: "Aby utworzyć nowy format, użyj metody [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Popraw wyniki.
---