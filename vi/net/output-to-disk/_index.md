---
translation: true
template: /_templates/_output-to-disk-net.md
title: Ghi đầu ra TeX vào đĩa | Giải pháp API .NET
url: /net/output-to-disk/
description: ".NET API Giải pháp để làm việc với TeX. Tìm hiểu ví dụ về cách tạo đầu ra tùy chỉnh cho tệp TeX với một vài dòng mã C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Ghi đầu ra TeX vào đĩa
h2: "Lưu kết quả chuyển đổi tệp TeX dưới dạng đĩa thông qua C# .NET"
---

{{<section overview>}}
---
p1: "TeX được biết đến như một ngôn ngữ sắp chữ có nghĩa là bạn không định dạng văn bản của mình trong tài liệu, nhưng nhập văn bản thuần túy cùng với các lệnh. Như đã biết từ bài viết [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) của Tài liệu, công việc TeX chạy trên tệp TeX được chỉ định rõ ràng. Ở đó, bạn cũng có thể tìm hiểu thông tin về các chế độ tương tác TeX và các nguyên tắc liên quan đến đầu vào và đầu ra của TeX."
p2: "Công dụng chính của TeX là giúp tạo ra văn bản toán học hoặc kỹ thuật. Nhưng khi tệp đã được tạo và bạn không muốn thực hiện thêm bất kỳ thao tác nào trên nó, bạn có thể muốn chuyển đổi nó sang một định dạng khác, phổ biến hơn."
p3: "Trên trang này, bạn sẽ tìm thấy một ví dụ mã giải thích việc sử dụng các thư mục hệ thống tệp cho đầu vào và đầu ra, xuất ra thiết bị XPS, ghi đè tên công việc, ghi đầu ra đầu cuối vào đĩa. Nói một cách dễ hiểu, nó là một sự chuyển đổi với việc ghi kết quả đầu ra vào đĩa. Để chạy hoạt động như vậy, chúng ta cần:"
p4: "Aspose.TeX cho .NET API là một API chuyển đổi và thao tác tài liệu giàu tính năng, mạnh mẽ và dễ sử dụng cho nền tảng C#."
p5: "Mở trình quản lý gói NuGet, tìm kiếm Aspose.TeX và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Bảng điều khiển Trình quản lý Gói."
---

{{<section feature1>}}
---
title: "Các bước để ghi đầu ra đầu cuối vào đĩa C#:"
h3: "Mã C# để chuyển đổi TeX và ghi đầu ra vào đĩa"
item1: "Tạo tùy chọn chuyển đổi dựa trên tiện ích mở rộng công cụ ObjectTeX bằng cách sử dụng [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Phương thức [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Lớp."
item2: "Chỉ định tên công việc nếu bạn không muốn đối số đầu tiên của phương thức khởi tạo TeXJob được sử dụng làm tên công việc."
item3: "Chỉ định một thư mục làm việc của hệ thống tệp cho đầu vào. Sử dụng Lớp [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) cho việc này."
item4: "Chỉ định thư mục làm việc của hệ thống tệp cho đầu ra với sự trợ giúp của các thực thể của Lớp [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Chỉ định rằng đầu ra đầu cuối phải được ghi vào một tệp trong thư mục làm việc đầu ra."
item6: "Chạy công việc [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Phương thức cho [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---