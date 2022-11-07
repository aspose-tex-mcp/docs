---
translation: true
template: /_templates/_customize-output-net.md
title: Tạo đầu ra tùy chỉnh TeX | API .NET
url: /net/customize-output/
description: ".NET API Giải pháp để làm việc với TeX. Đọc ví dụ về cách tạo đầu ra tùy chỉnh cho tệp TeX với một vài dòng mã C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Tùy chỉnh đầu ra
h2: "Giải pháp .NET API để tùy chỉnh đầu ra của tệp TeX"
---

{{<section overview>}}
---
p1: "TeX được biết đến như một ngôn ngữ sắp chữ. Nó có nghĩa là bạn không định dạng văn bản của bạn trong tài liệu, nhưng nhập văn bản thuần túy cùng với các lệnh."
p2: "Bài viết [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) của Documentation cho chúng ta biết rằng một tệp TeX có thể không chứa bất kỳ dữ liệu nào để sắp chữ mà chỉ chứa các chuỗi điều khiển . Tuy nhiên, nó thường chứa những dữ liệu như vậy và một tệp ở định dạng đích có văn bản sắp chữ. Tệp cũng sẽ có cùng tên với tệp được chỉ định làm đầu vào và là tệp đầu ra chính. Đối với TeX gốc, đây là tệp ở định dạng DVI. Chúng tôi sẽ gọi tên của cả tệp đầu vào và đầu ra mà không cần mở rộng tên công việc."
p3: "Trên trang này, bạn sẽ tìm thấy một ví dụ mã giải thích việc tạo tệp định dạng TeX tùy chỉnh, nơi bạn có thể xem cách tùy chỉnh đầu ra của tệp TeX. Để tùy chỉnh đầu ra tệp .tex, chúng tôi cần:"
p4: "Aspose.TeX cho .NET API là một API chuyển đổi và thao tác tài liệu giàu tính năng, mạnh mẽ và dễ sử dụng cho nền tảng C#."
p5: "Mở trình quản lý gói NuGet, tìm kiếm Aspose.TeX và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Bảng điều khiển Trình quản lý Gói."
---

{{<section feature1>}}
---
title: "Các bước để tùy chỉnh đầu ra TeX C#:"
h3: "Mã C# cho tùy chỉnh đầu ra TeX"
item1: "Với sự trợ giúp của [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Phương thức [*TeXOptions*](https://reference.asposeLớp.com/tex/net/aspose.tex/texoptions/), tạo các tùy chọn công cụ TeX không có định dạng dựa trên phần mở rộng công cụ ObjectTeX."
item2: "Sử dụng lớp [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) để chỉ định thư mục làm việc của hệ thống tệp cho đầu vào."
item3: "Sử dụng lớp [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) để chỉ định thư mục làm việc của hệ thống tệp cho đầu ra."
item4: "Để tạo định dạng mới, hãy sử dụng phương thức [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Tinh chỉnh đầu ra.
---