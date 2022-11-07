---
translation: true
template: /_templates/_output-to-disk-net.md
title: Tulis keluaran TeX ke disk | .NET API Solusi
url: /net/output-to-disk/
description: ".NET API Solusi untuk bekerja dengan TeX. Pelajari pada contoh cara membuat keluaran khusus untuk file TeX dengan beberapa baris kode C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Tulis keluaran TeX ke disk
h2: "Simpan hasil konversi file TeX sebagai disk melalui C# .NET"
---

{{<section overview>}}
---
p1: "TeX dikenal sebagai bahasa pengaturan huruf yang berarti bahwa Anda tidak memformat teks Anda dalam dokumen, tetapi memasukkan teks biasa bersama dengan perintah. Seperti yang diketahui dari artikel [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) dari Dokumentasi, tugas TeX berjalan pada file TeX yang ditentukan secara eksplisit. Di sana Anda juga dapat menemukan informasi tentang mode interaksi TeX dan primitif yang terkait dengan input dan output TeX."
p2: "Kegunaan utama TeX adalah untuk membantu dalam pembuatan teks matematis atau teknis. Tetapi ketika file sudah dibuat dan Anda tidak ingin manipulasi lebih lanjut, Anda mungkin ingin mengonversinya ke format lain yang lebih populer."
p3: "Pada halaman ini, Anda akan menemukan contoh kode yang menjelaskan penggunaan direktori sistem file untuk input dan output, output ke perangkat XPS, mengganti nama pekerjaan, menulis output terminal ke disk. Dengan kata sederhana, ini adalah konversi dengan penulisan output ke disk. Untuk menjalankan operasi seperti itu kita perlu:"
p4: "Aspose.TeX untuk .NET API yang merupakan API konversi dan manipulasi dokumen yang kaya fitur, kuat, dan mudah digunakan untuk platform C#."
p5: "Buka manajer paket NuGet, dan cari Aspose.TeX dan instal. Anda juga dapat menggunakan perintah berikut dari Package Manager Console."
---

{{<section feature1>}}
---
title: "Langkah-langkah untuk menulis keluaran terminal ke disk C#:"
h3: "C# Kode untuk mengkonversi TeX dan menulis output ke disk"
item1: "Buat opsi konversi pada ekstensi mesin ObjectTeX menggunakan [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metode [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Kelas."
item2: "Tentukan nama pekerjaan jika Anda tidak ingin argumen pertama konstruktor TeXJob diambil sebagai nama pekerjaan."
item3: "Tentukan direktori kerja sistem file untuk input. Gunakan Kelas [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) untuk ini."
item4: "Tentukan direktori kerja sistem file untuk output dengan bantuan entitas dari Kelas [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Tentukan bahwa output terminal harus ditulis ke file di direktori kerja output."
item6: "Jalankan pekerjaan [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Metode untuk [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---