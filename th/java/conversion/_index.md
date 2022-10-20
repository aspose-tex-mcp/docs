---
translation: true
template: /_templates/_conversion-java.md
title: การแปลงไฟล์ TeX (LaTeX) | Java
url: /java/conversion/
description: โซลูชัน Java API การแปลง TeX (LaTeX) แปลงไฟล์ LaTeX เป็น PDF, XPS และรูปภาพ รวมถึง PNG, JPEG, TIFF, BMP ด้วยโค้ด Java สองสามบรรทัด
keywords: เท็กซ์คอนเวอร์ชั่น api java, เท็กซ์คอนเวอร์เตอร์จาวาอินทิเกรต
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: แปลง TeX และ LaTeX
h2: "โซลูชัน TeX converter API สำหรับ Java"
---

{{<section overview>}}
---
p1: "Aspose.TeX เป็น API ของระบบ Object TeX สำหรับรายละเอียดของไฟล์ Tex นี่คือ [บทนำ Tex](https://docs.aspose.com/tex/cpp/what-is-tex/) นักพัฒนาสามารถแปลงรูปแบบ TeX เป็น PDF, XPS, PNG, JPG, BMP และ TIFF ได้อย่างง่ายดายโดยการรวม API สำหรับ Java ด้านล่างนี้คือตัวอย่างโค้ดบางส่วนที่โปรแกรมเมอร์สามารถปรับปรุงและรวมเข้ากับโซลูชัน Tex ได้"
p2: "โซลูชัน API สำหรับ Java ที่นี่ให้คุณแปลงไฟล์ TeX และ LaTeX โดยทางโปรแกรม แต่คุณอาจพบว่ามีประโยชน์ในการดูและลองใช้ [ตัวแปลงข้ามแพลตฟอร์ม](https://products.aspose.app/tex/conversion) ที่พัฒนาบนเนทีฟเหล่านี้ API คุณยังสามารถค้นหา [applications](https://products.aspose.app/tex/applications) เพื่อสร้างและแก้ไขไฟล์ TeX ตาราง กราฟิก เพื่อรวมไฟล์ให้อยู่ในรูปแบบ PDF เป็นต้น"
---

{{<section feature1>}}
---
title: "แปลง LaTeX เป็นรูปภาพ, XPS, PDF, SVG ด้วย Java"
h3: "ตัวอย่างโค้ด Java การแปลง TeX เป็นรูปภาพ, XPS, PDF หรือ SVG"
item1: "API รองรับ BMP, JPEG, PDF, SVG, TIFF, XPS และ PNG เป็นรูปแบบเอาต์พุต ขั้นตอนถัดไปในการแปลงไฟล์ TeX เป็นรูปภาพ, PDF, XPS หรือ SVG:"
item2: "สร้างอินสแตนซ์ของ [คลาส TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions)"
item3: "ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับเอาต์พุต/อินพุตโดยใช้ [*OutputWorkingDirectory*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory- )/[*InputWorkingDirectory*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-)"
item4: "เริ่มต้นตัวเลือกสำหรับการบันทึกโดยใช้ [*BmpSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/BmpSaveOptions), [*PngSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PngSaveOptions), [*TiffSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/TiffSaveOptions) [*JpegSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/JpegSaveOptions) หรือ [*PdfSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions), [*SvgSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgSaveOptions), [*XpsSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsSaveOptions) ซึ่งเป็นค่าเริ่มต้น ไม่จำเป็นต้องตั้งค่า"
item5: "เรียกใช้การแปลงโดยใช้วิธี Rum ของ [*TeXJob()*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob) สำหรับ [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/ImageDevice) หรือ [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice), [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice), [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice), [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice)"
item6: "Aspose.TeX สำหรับ Java ทำงานได้ดีในสภาพแวดล้อมการพัฒนาใดๆ ที่สนับสนุน Java แต่ขอแนะนำให้ใช้ข้อกำหนดถัดไป:"
item7: เดสก์ท็อป Microsoft Windows (7, 8, 10)
item8: ระบบ Linux (Ubuntu-16.04 หรือใหม่กว่า)
item9: Mac OS X.
item10: J2SE 8.0 (1.8) หรือสูงกว่า (เช่น Java 10) Java Version
---

