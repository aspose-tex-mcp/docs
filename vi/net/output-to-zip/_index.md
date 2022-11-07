---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX sang ZIP | Giải pháp API .NET
url: /net/output-to-zip/
description: ".NET API Giải pháp để làm việc với TeX. Chức năng chuyển đổi TeX sang ZIP cho phép bạn lưu tệp TeX của mình dưới dạng tệp lưu trữ phổ biến nhất. C# ví dụ về chức năng này."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Ghi đầu ra vào ZIP
h2: "Lưu kết quả chuyển đổi tệp TeX dưới dạng ZIP qua C# .NET"
---

{{<section overview>}}
---
p1: "TeX được biết đến là một trong những ngôn ngữ đánh dấu dữ liệu. Nó là cốt lõi chính của hệ thống ấn phẩm (sắp chữ máy tính). Có vấn đề nếu coi [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) là một định dạng tệp, vì nó là một ngôn ngữ lập trình. Và mặt khác, nó là một công cụ thông dịch hiểu ngôn ngữ này. Dù sao, trong ngắn hạn, mục đích chính của nó là giúp tạo ra văn bản toán học hoặc kỹ thuật. Nhưng khi tệp đã được tạo và bạn không muốn thực hiện thêm bất kỳ thao tác nào trên nó, bạn có thể muốn chuyển đổi nó sang một định dạng khác, phổ biến hơn."
p2: "Giải pháp API Aspose.TeX trong số các tính năng khác cho phép chuyển đổi các tệp TeX và sau đó lưu kết quả dưới dạng tệp nén ZIP. Tại đây, bạn sẽ tìm thấy một đoạn mã về cách chuyển đổi TeX sang PDF và lưu đầu ra của kết quả thành zip. Bộ chuyển đổi API chuyển đổi TeX bằng bất kỳ ngôn ngữ nào được C# hỗ trợ. API bạn thấy ở đây cũng có thể được sử dụng để tạo ứng dụng đa nền tảng của riêng bạn hoặc được tích hợp vào dự án .NET của bạn. [*Trình chuyển đổi đa nền tảng*](https://products.aspose.app/tex/conversion/tex) như vậy cũng có trong hệ sinh thái Aspose. Nhưng để chạy các ví dụ, chúng tôi cần:"
p3: "Aspose.TeX cho .NET API là một API chuyển đổi và thao tác tài liệu giàu tính năng, mạnh mẽ và dễ sử dụng cho nền tảng C#."
p4: "Mở trình quản lý gói NuGet, tìm kiếm Aspose.TeX và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Bảng điều khiển Trình quản lý Gói."
---

{{<section feature1>}}
---
title: 'Các bước sử dụng thư mục ZIP cho tệp TeX đầu ra C#.'
h3: "Mã C# để sử dụng thư mục ZIP cho đầu ra"
item1: "Tạo phiên bản của [*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "Chỉ định thư mục làm việc của kho lưu trữ ZIP cho đầu ra bằng thuộc tính [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)."
item3: "Chỉ định bảng điều khiển làm đầu ra đầu ra bằng cách sử dụng Lớp [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item4: "Xác định các tùy chọn để lưu bằng Lớp [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item5: "Chạy chuyển đổi bằng phương thức [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) cho [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: Tinh chỉnh đầu ra.
item7: "Để hoàn thiện tệp nén ZIP đầu ra, hãy sử dụng Lớp [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
---