---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Memuat TeX dari disk | .NET API Solusi
url: /net/load-tex-from-disk/
description: ".NET API Solusi untuk bekerja dengan TeX. Pelajari pada contoh cara memuat file TeX dari disk dengan beberapa baris kode C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Muat file sumber TeX dari disk
h2: ".NET API Solution untuk memuat file TeX/LaTeX dari disk"
---

{{<section overview>}}
---
p1: "TeX dikenal sebagai bahasa penyusunan huruf. Ini berarti bahwa Anda tidak memformat teks Anda dalam dokumen, tetapi memasukkan teks biasa bersama dengan perintah. Sebagai output, Anda akan mendapatkan file yang diformat dengan format yang dibutuhkan (ditentukan). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) adalah inti utama dari sistem set publikasi (pengaturan huruf komputer). Pekerjaan TeX berjalan pada file TeX yang ditentukan secara eksplisit. Untuk lebih memahami input dan output TeX, pelajari [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) dari Dokumentasi."
p2: "Seperti diketahui, tujuan utama dari TeX adalah untuk membantu membuat tulisan teks matematis atau teknis. Tetapi sebelum manipulasi apa pun, file tersebut harus dimuat terlebih dahulu. Di sini Anda akan menemukan potongan kode yang menjelaskan cara memuat file sumber TeX dari disk menggunakan direktori sistem file untuk input dan output, mengeluarkan ke perangkat XPS, menulis output terminal ke konsol."
p3: "Untuk menjalankan contoh yang kita butuhkan:"
p4: "Aspose.TeX untuk .NET API yang merupakan API konversi dan manipulasi dokumen yang kaya fitur, kuat, dan mudah digunakan untuk platform C#."
p5: "Buka manajer paket NuGet, dan cari Aspose.TeX dan instal. Anda juga dapat menggunakan perintah berikut dari Package Manager Console."
---

{{<section feature1>}}
---
title: Langkah-langkah untuk memuat TeX dari disk C#.
h3: "Kode C# untuk memuat TeX"
item1: "Buat opsi konversi untuk format khusus pada ekstensi mesin ObjectTeX menggunakan [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metode [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Kelas."
item2: "Tentukan direktori kerja sistem file untuk input. Gunakan Kelas [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) untuk ini."
item3: "Tentukan direktori kerja sistem file untuk output menggunakan [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class."
item4: "Tentukan konsol sebagai terminal output menggunakan [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class."
item5: "Tentukan terminal memori sebagai terminal keluaran jika Anda membutuhkannya. Untuk ini gunakan [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) Kelas."
item6: "Jalankan pekerjaan [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metode untuk [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Perbaiki outputnya.
---