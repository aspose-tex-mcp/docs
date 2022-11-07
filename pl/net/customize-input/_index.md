---
translation: true
template: /_templates/_customize-input-net.md
title: Utwórz niestandardowe wejście TeX | API .NET
url: /net/customize-input/
description: "Rozwiązanie .NET API do pracy z TeX-em. Dowiedz się na przykładzie, jak utworzyć niestandardowe dane wejściowe dla pliku TeX za pomocą kilku linijek kodu C#."
keywords: niestandardowe wejście tex net api, C# api, aby dostosować tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Dostosuj dane wejściowe
h2: "Rozwiązanie .NET API do dostosowywania wprowadzania plików TeX"
---

{{<section overview>}}
---
p1: "TeX jest znany jako język składu. Oznacza to, że nie formatujesz tekstu w dokumencie, ale wprowadzasz zwykły tekst wraz z poleceniami. Jak opisano w artykule [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) dokumentacji, zadanie TeX działa na jawnie określonym pliku TeX. Tak więc dołączamy ten plik do danych wejściowych pewnego zadania TeX."
p2: "Na tej stronie znajdziesz przykład kodu wyjaśniający, jak dostosować dane wejściowe plików źródłowych TeX, biorąc pod uwagę, że dane wejściowe powinny być zgodne ze składnią TeX i, najlepiej, zawierać tylko polecenia znane silnikowi."
p3: "Aby dostosować dane wejściowe plików .tex, potrzebujemy:"
p4: "Aspose.TeX dla .NET API, który jest bogatym w funkcje, wydajnym i łatwym w użyciu interfejsem API do manipulacji i konwersji dokumentów dla platformy C#."
p5: "Otwórz Menedżera pakietów NuGet i wyszukaj Aspose.TeX i zainstaluj. Możesz również użyć następującego polecenia z konsoli Menedżera pakietów."
---

{{<section feature1>}}
---
title: "Kroki, aby dostosować wejście TeX C#:"
h3: "Kod C# do dostosowywania danych wejściowych TeX"
item1: "Używając [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) metody [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Klasa, utwórz opcje silnika TeX bez formatowania po rozszerzeniu silnika ObjectTeX."
item2: "Używając klasy [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) określ katalog roboczy systemu plików dla danych wejściowych."
item3: "Za pomocą metody [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) utwórz dostosowany format."
---