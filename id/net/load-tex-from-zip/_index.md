---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Memuat TeX dari ZIP | .NET API Solusi
url: /net/load-tex-from-zip/
description: ".NET API Solusi untuk bekerja dengan TeX. Pelajari pada contoh cara memuat file TeX dari ZIP dengan beberapa baris kode C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Muat file sumber TeX dari ZIP
h2: ".NET API Solution untuk memuat file TeX dari arsip ZIP"
---

{{<section overview>}}
---
p1: "TeX dikenal sebagai bahasa penyusunan huruf. Ini berarti bahwa Anda tidak memformat teks Anda dalam dokumen, tetapi memasukkan teks biasa bersama dengan perintah. Sebagai output, Anda akan mendapatkan file yang diformat dengan format yang dibutuhkan (ditentukan). Untuk lebih memahami input dan output TeX, pelajari [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) dari Dokumentasi."
p2: "Seperti diketahui, tujuan utama dari TeX adalah untuk membantu membuat tulisan teks matematis atau teknis. Tetapi sebelum manipulasi apa pun, file tersebut harus dimuat terlebih dahulu. Di sini Anda akan menemukan potongan kode yang menjelaskan cara memuat file sumber TeX dari ZIP menggunakan direktori ZIP untuk masukan dan keluaran, keluaran ke perangkat PDF, menulis keluaran terminal ke konsol."
p3: "Untuk memuat file .tex kita perlu:"
p4: "Aspose.TeX untuk .NET API yang merupakan API konversi dan manipulasi dokumen yang kaya fitur, kuat, dan mudah digunakan untuk platform C#."
p5: "Buka manajer paket NuGet, dan cari Aspose.TeX dan instal. Anda juga dapat menggunakan perintah berikut dari Package Manager Console."
---

{{<section feature1>}}
---
title: "Langkah-langkah untuk memuat TeX dari arsip ZIP C#:"
h3: "Kode C# untuk memuat TeX"
item1: "Buka aliran pada arsip ZIP untuk menggunakannya sebagai direktori kerja input."
item2: "Buka aliran pada arsip ZIP untuk menggunakannya sebagai direktori kerja keluaran."
item3: "Buat opsi konversi untuk format ObjectTeX default pada ekstensi mesin ObjectTeX menggunakan [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metode [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Kelas."
item4: "Tentukan direktori kerja arsip ZIP untuk input atau/dan tentukan jalur di dalam arsip. Gunakan konstruktor Kelas [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) untuk ini."
item5: "Tentukan direktori kerja arsip ZIP untuk output atau/dan tentukan jalur di dalam arsip. Gunakan konstruktor Kelas [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) untuk ini."
item6: "Tentukan konsol sebagai terminal output menggunakan [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class."
item7: "Tentukan opsi penyimpanan menggunakan Kelas [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Jalankan pekerjaan [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metode untuk [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Perbaiki outputnya.
---