---
translation: true
template: /_templates/_customize-input-net.md
title: Tạo đầu vào tùy chỉnh TeX | API .NET
url: /net/customize-input/
description: ".NET API Giải pháp để làm việc với TeX. Tìm hiểu ví dụ về cách tạo đầu vào tùy chỉnh cho tệp TeX với một vài dòng mã C#."
keywords: 'đầu vào tùy chỉnh tex net api, C# api để tùy chỉnh tex'
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Tùy chỉnh đầu vào
h2: ".NET API Giải pháp để tùy chỉnh đầu vào của các tệp TeX"
---

{{<section overview>}}
---
p1: "TeX được biết đến như một ngôn ngữ sắp chữ. Nó có nghĩa là bạn không định dạng văn bản của bạn trong tài liệu, nhưng nhập văn bản thuần túy cùng với các lệnh. Như được mô tả trong bài viết [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) của Tài liệu, công việc TeX chạy trên tệp TeX được chỉ định rõ ràng. Vì vậy, chúng tôi đưa tệp này vào đầu vào của một công việc TeX nhất định."
p2: "Trên trang này, bạn sẽ tìm thấy một ví dụ mã giải thích cách tùy chỉnh đầu vào của tệp nguồn TeX có tính đến việc đầu vào phải tuân theo cú pháp TeX và lý tưởng là chỉ chứa các lệnh mà engine đã biết."
p3: "Để tùy chỉnh đầu vào tệp .tex, chúng tôi cần:"
p4: "Aspose.TeX cho .NET API là một API chuyển đổi và thao tác tài liệu giàu tính năng, mạnh mẽ và dễ sử dụng cho nền tảng C#."
p5: "Mở trình quản lý gói NuGet, tìm kiếm Aspose.TeX và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Bảng điều khiển Trình quản lý Gói."
---

{{<section feature1>}}
---
title: "Các bước để tùy chỉnh đầu vào TeX C#:"
h3: "Mã C# cho tùy chỉnh đầu vào TeX"
item1: "Sử dụng [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Phương thức [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Lớp, tạo các tùy chọn công cụ TeX để không có định dạng dựa trên phần mở rộng công cụ ObjectTeX."
item2: "Sử dụng Lớp [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), chỉ định thư mục làm việc của hệ thống tệp cho đầu vào."
item3: "Với sự trợ giúp của Phương thức [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), hãy tạo định dạng tùy chỉnh."
---