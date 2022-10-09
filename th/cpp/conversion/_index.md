---
translation: true
template: /_templates/_conversion-cpp.md
title: การแปลงไฟล์ TeX (LaTeX) | C++
url: /cpp/conversion/
keywords: เท็กซ์คอนเวอร์เตอร์ cpp api, เท็กซ์คอนเวอร์เตอร์ c++ api
description: โซลูชันการแปลง TeX (LaTeX) C++ API แปลงไฟล์ LaTeX เป็น PDF, XPS และรูปภาพ รวมถึง PNG, JPEG, TIFF, BMP ด้วยโค้ด C++ สองสามบรรทัด
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: แปลง TeX และ LaTeX
h2: "โซลูชัน TeX converter API สำหรับ C ++"
---

{{<section overview>}}
---
p1: "Aspose.TeX เป็น API ของระบบ Object TeX สำหรับรายละเอียดของไฟล์ Tex นี่คือ [บทนำ Tex](https://docs.aspose.com/tex/cpp/what-is-tex/) นักพัฒนาสามารถแปลงรูปแบบ TeX เป็น PDF, XPS, PNG, JPG, BMP และ TIFF ได้อย่างง่ายดายโดยการรวม API สำหรับ C++ ด้านล่างนี้คือตัวอย่างโค้ดบางส่วนที่โปรแกรมเมอร์สามารถปรับปรุงและรวมเข้ากับโซลูชัน LaTex ได้"
p2: "โซลูชัน API สำหรับ Java ที่นี่ให้คุณแปลงไฟล์ TeX และ LaTeX โดยทางโปรแกรม แต่คุณอาจพบว่ามีประโยชน์ในการดูและลองใช้ [ตัวแปลงข้ามแพลตฟอร์ม](https://products.aspose.app/tex/conversion) ที่พัฒนาบนเนทีฟเหล่านี้ API คุณยังสามารถค้นหา [applications](https://products.aspose.app/tex/applications) เพื่อสร้างและแก้ไขไฟล์ TeX ตาราง กราฟิก เพื่อรวมไฟล์ให้อยู่ในรูปแบบ PDF เป็นต้น"
---

{{<section feature1>}}
---
title: "แปลง LaTeX เป็นรูปภาพ, XPS, PDF, SVG C++"
h3: "ตัวอย่างโค้ด C++ การแปลง TeX เป็นรูปภาพ, XPS, PDF หรือ SVG"
item1: "API รองรับ BMP, JPEG, PDF, SVG, TIFF, XPS และ PNG เป็นรูปแบบเอาต์พุต ขั้นตอนถัดไปในการแปลงไฟล์ TeX เป็นรูปภาพ, PDF, XPS หรือ SVG:"
item2: "สร้างอินสแตนซ์ของ [*TeXOptions Class*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options)"
item3: "กำหนดประเภทและขนาดของรูปภาพโดยใช้ [*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device)"
item4: "ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับเอาต์พุต/อินพุตโดยใช้ [*OutputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)"
item5: "เริ่มต้นตัวเลือกสำหรับการบันทึกโดยใช้ [*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [*JpegSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) หรือ [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options) ซึ่งเป็นค่าเริ่มต้น ไม่จำเป็นต้องตั้งค่า"
item6: "เรียกใช้การแปลงโดยใช้วิธีการเรียกใช้ของ [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) สำหรับ [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) หรือ [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device)"
item7: "Aspose.TeX สำหรับ C++ ทำงานได้ดีในสภาพแวดล้อมการพัฒนาใดๆ ที่สนับสนุน C++ แต่ขอแนะนำให้ใช้ข้อกำหนดถัดไป:"
item8: Microsoft Visual Studio 2015 หรือใหม่กว่า
item9: เดสก์ท็อป Microsoft Windows (7, 8, 10)
item10: ระบบปฏิบัติการเซิร์ฟเวอร์ (2008, 2012) เป็นต้น
item11: ระบบ Linux (Ubuntu-16.04 หรือใหม่กว่า)
---


