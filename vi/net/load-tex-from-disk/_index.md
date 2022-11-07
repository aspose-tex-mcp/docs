---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Tải TeX từ đĩa | Giải pháp API .NET
url: /net/load-tex-from-disk/
description: ".NET API Giải pháp để làm việc với TeX. Tìm hiểu ví dụ về cách tải tệp TeX từ đĩa với một vài dòng mã C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Tải tệp nguồn TeX từ đĩa
h2: "Giải pháp .NET API để tải tệp TeX / LaTeX từ đĩa"
---

{{<section overview>}}
---
p1: "TeX được biết đến như một ngôn ngữ sắp chữ. Nó có nghĩa là bạn không định dạng văn bản của bạn trong tài liệu, nhưng nhập văn bản thuần túy cùng với các lệnh. Như một đầu ra, bạn sẽ nhận được tệp được định dạng có định dạng cần thiết (được chỉ định). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) là lõi trung tâm của hệ thống tập xuất bản (sắp chữ bằng máy tính). Một công việc TeX chạy trên một tệp TeX được chỉ định rõ ràng. Để hiểu thêm về đầu vào và đầu ra của TeX, hãy tìm hiểu [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) của Tài liệu."
p2: "Như đã biết, mục đích chính của TeX là giúp tạo ra văn bản toán học hoặc kỹ thuật. Nhưng trước bất kỳ thao tác nào, tệp phải được tải trước. Tại đây, bạn sẽ tìm thấy các đoạn mã giải thích cách tải tệp nguồn TeX từ đĩa bằng cách sử dụng thư mục hệ thống tệp cho đầu vào và đầu ra, xuất ra thiết bị XPS, ghi đầu ra đầu cuối vào bảng điều khiển."
p3: "Để chạy các ví dụ, chúng tôi cần:"
p4: "Aspose.TeX cho .NET API là một API chuyển đổi và thao tác tài liệu giàu tính năng, mạnh mẽ và dễ sử dụng cho nền tảng C#."
p5: "Mở trình quản lý gói NuGet, tìm kiếm Aspose.TeX và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Bảng điều khiển Trình quản lý Gói."
---

{{<section feature1>}}
---
title: 'Các bước tải TeX từ đĩa C#.'
h3: "Mã C# để tải TeX"
item1: "Tạo các tùy chọn chuyển đổi cho một định dạng tùy chỉnh dựa trên phần mở rộng công cụ ObjectTeX bằng cách sử dụng [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Phương thức [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Lớp."
item2: "Chỉ định một thư mục làm việc của hệ thống tệp cho đầu vào. Sử dụng Lớp [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) cho việc này."
item3: "Chỉ định thư mục làm việc của hệ thống tệp cho đầu ra bằng cách sử dụng Lớp [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Chỉ định bảng điều khiển làm đầu ra đầu ra bằng cách sử dụng Lớp [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "Chỉ định một đầu cuối bộ nhớ làm đầu ra nếu bạn cần. Đối với việc sử dụng này [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) Lớp."
item6: "Chạy công việc [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Phương thức cho [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Tinh chỉnh đầu ra.
---