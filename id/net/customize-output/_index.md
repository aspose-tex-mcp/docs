---
translation: true
template: /_templates/_customize-output-net.md
title: Buat TeX keluaran khusus | .NET API
url: /net/customize-output/
description: ".NET API Solusi untuk bekerja dengan TeX. Baca contoh cara membuat keluaran khusus untuk file TeX dengan beberapa baris kode C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Sesuaikan keluaran
h2: ".NET API Solution untuk menyesuaikan output file TeX"
---

{{<section overview>}}
---
p1: "TeX dikenal sebagai bahasa penyusunan huruf. Ini berarti bahwa Anda tidak memformat teks Anda dalam dokumen, tetapi memasukkan teks biasa bersama dengan perintah."
p2: "Artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) dari Dokumentasi mengajarkan kita bahwa file TeX mungkin tidak berisi data apa pun untuk mengeset tetapi hanya mengontrol urutan . Namun biasanya berisi data seperti itu, dan file dalam format target memiliki teks yang diset. File juga akan memiliki nama yang sama dengan file yang ditentukan sebagai input dan merupakan file output utama. Untuk TeX asli, ini adalah file dalam format DVI. Kami akan memanggil nama file input dan output tanpa memperpanjang nama pekerjaan."
p3: "Di halaman ini, Anda akan menemukan contoh kode yang menjelaskan pembuatan file format TeX khusus di mana Anda dapat melihat cara menyesuaikan output file TeX. Untuk menyesuaikan output file .tex kita perlu:"
p4: "Aspose.TeX untuk .NET API yang merupakan API konversi dan manipulasi dokumen yang kaya fitur, kuat, dan mudah digunakan untuk platform C#."
p5: "Buka manajer paket NuGet, dan cari Aspose.TeX dan instal. Anda juga dapat menggunakan perintah berikut dari Package Manager Console."
---

{{<section feature1>}}
---
title: "Langkah-langkah untuk menyesuaikan keluaran TeX C#:"
h3: "Kode C# untuk kustomisasi keluaran TeX"
item1: "Dengan bantuan Metode [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class, buat opsi mesin TeX tanpa format pada ekstensi mesin ObjectTeX."
item2: "Gunakan Kelas [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) untuk menentukan direktori kerja sistem file untuk input."
item3: "Gunakan Kelas [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) untuk menentukan direktori kerja sistem file untuk output."
item4: "Untuk membuat format baru, gunakan Metode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Perbaiki outputnya.
---