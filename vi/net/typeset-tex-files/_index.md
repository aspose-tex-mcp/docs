---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: Chức năng sắp chữ TeX | API .NET
url: /net/typeset-tex-files/
description: ".NET API Giải pháp để làm việc với TeX. Tìm hiểu ví dụ về cách tạo bộ chữ TeX với một vài dòng mã C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Tệp TeX tập hợp
h2: "Nhập tệp TeX bằng định dạng TeX tùy chỉnh C# .NET"
---

{{<section overview>}}
---
p1: "TeX được biết đến như một trong những ngôn ngữ đánh dấu dữ liệu và / hoặc ngôn ngữ sắp chữ cùng một lúc. Nó có nghĩa là bạn không định dạng văn bản của bạn trong tài liệu, nhưng nhập văn bản thuần túy cùng với các lệnh. Như một đầu ra, bạn sẽ nhận được tệp được định dạng có định dạng cần thiết (được chỉ định). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) là lõi trung tâm của hệ thống tập xuất bản (sắp chữ bằng máy tính)."
p2: "Để hiểu thêm về cách sắp chữ TeX, hãy tìm hiểu [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) của Tài liệu. Và trên trang này, bạn sẽ tìm thấy các đoạn mã giải thích cách sắp chữ một tệp TeX bằng cách sử dụng định dạng TeX tùy chỉnh."
p3: "Để chạy các ví dụ, chúng tôi cần:"
p4: "Aspose.TeX cho .NET API là một API chuyển đổi và thao tác tài liệu giàu tính năng, mạnh mẽ và dễ sử dụng cho nền tảng C#."
p5: "Mở trình quản lý gói NuGet, tìm kiếm Aspose.TeX và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Bảng điều khiển Trình quản lý Gói."
---

{{<section feature1>}}
---
title: 'Các bước để sắp chữ TeX bằng C#.'
h3: "Mã C# để sắp chữ TeX"
item1: "Tạo trình cung cấp định dạng bằng cách sử dụng Lớp [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Tạo các tùy chọn chuyển đổi cho một định dạng tùy chỉnh dựa trên phần mở rộng công cụ ObjectTeX bằng cách sử dụng [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Phương thức [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Lớp."
item3: "Chỉ định thư mục làm việc đầu vào nếu đầu vào chính không được cung cấp dưới dạng luồng. Sử dụng Lớp [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) cho việc này."
item4: "Chỉ định một thư mục làm việc của hệ thống tệp cho đầu ra. Sử dụng Lớp [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) cho việc này."
item5: "Chạy công việc [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Phương thức cho [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Tinh chỉnh đầu ra.
---