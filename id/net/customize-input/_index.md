---
translation: true
template: /_templates/_customize-input-net.md
title: Buat TeX masukan khusus | .NET API
url: /net/customize-input/
description: ".NET API Solusi untuk bekerja dengan TeX. Pelajari contoh cara membuat input khusus untuk file TeX dengan beberapa baris kode C#."
keywords: masukan kustom tex net api, C# api untuk menyesuaikan teks
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Sesuaikan masukan
h2: ".NET API Solution untuk menyesuaikan input file TeX"
---

{{<section overview>}}
---
p1: "TeX dikenal sebagai bahasa penyusunan huruf. Ini berarti bahwa Anda tidak memformat teks Anda dalam dokumen, tetapi memasukkan teks biasa bersama dengan perintah. Seperti yang dijelaskan dalam artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) dari Dokumentasi, tugas TeX berjalan pada file TeX yang ditentukan secara eksplisit. Jadi, kami menyertakan file ini dalam input pekerjaan TeX tertentu."
p2: "Pada halaman ini Anda akan menemukan contoh kode yang menjelaskan cara menyesuaikan input file sumber TeX dengan mempertimbangkan bahwa input harus mengikuti sintaks TeX dan, idealnya, hanya berisi perintah yang diketahui oleh mesin."
p3: "Untuk menyesuaikan input file .tex kita perlu:"
p4: "Aspose.TeX untuk .NET API yang merupakan API konversi dan manipulasi dokumen yang kaya fitur, kuat, dan mudah digunakan untuk platform C#."
p5: "Buka manajer paket NuGet, dan cari Aspose.TeX dan instal. Anda juga dapat menggunakan perintah berikut dari Package Manager Console."
---

{{<section feature1>}}
---
title: "Langkah-langkah untuk menyesuaikan input TeX C#:"
h3: "Kode C# untuk kustomisasi input TeX"
item1: "Menggunakan [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metode [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class, buat opsi mesin TeX tanpa format pada ekstensi mesin ObjectTeX."
item2: "Menggunakan Kelas [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), tentukan direktori kerja sistem file untuk input."
item3: "Dengan bantuan Metode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), buat format yang disesuaikan."
---