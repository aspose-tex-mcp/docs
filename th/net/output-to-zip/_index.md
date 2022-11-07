---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX เป็น ZIP | .NET API โซลูชั่น
url: /net/output-to-zip/
description: ".NET API โซลูชันเพื่อทำงานกับ TeX ฟังก์ชันการแปลง TeX เป็น ZIP ช่วยให้คุณบันทึกไฟล์ TeX เป็นไฟล์เก็บถาวรยอดนิยมได้ ตัวอย่าง C# ของฟังก์ชันนี้"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: เขียนเอาต์พุตไปยัง ZIP
h2: "บันทึกผลลัพธ์ของการแปลงไฟล์ TeX เป็น ZIP ผ่าน C# .NET"
---

{{<section overview>}}
---
p1: "TeX เป็นที่รู้จักว่าเป็นหนึ่งในภาษามาร์กอัปข้อมูล เป็นแกนหลักของระบบชุดสิ่งพิมพ์ (การเรียงพิมพ์ด้วยคอมพิวเตอร์) การพิจารณา [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) เป็นรูปแบบไฟล์ที่น่าสงสัย เนื่องจากเป็นภาษาโปรแกรม และในทางกลับกัน มันเป็นเครื่องมือล่ามที่เข้าใจภาษานี้ อย่างไรก็ตาม ในระยะสั้น จุดประสงค์หลักของมันคือเพื่อช่วยในการสร้างการเขียนข้อความทางคณิตศาสตร์หรือทางเทคนิค แต่เมื่อไฟล์ถูกสร้างขึ้นแล้วและคุณไม่ต้องการให้มีการปรับเปลี่ยนใด ๆ เพิ่มเติม คุณอาจต้องการแปลงไฟล์ให้เป็นรูปแบบอื่นที่เป็นที่นิยมมากขึ้น"
p2: "โซลูชัน Aspose.TeX API ท่ามกลางคุณสมบัติอื่น ๆ ที่แตกต่างกันช่วยให้สามารถแปลงไฟล์ TeX แล้วบันทึกผลลัพธ์เป็นไฟล์ ZIP ที่นี่คุณจะพบข้อมูลโค้ดเกี่ยวกับวิธีการแปลง TeX เป็น PDF และบันทึกผลลัพธ์ของผลลัพธ์เป็น zip ตัวแปลง API แปลง TeX โดยใช้ภาษาใด ๆ ที่ C# รองรับ API ที่คุณเห็นที่นี่ยังสามารถใช้เพื่อสร้างแอปพลิเคชันข้ามแพลตฟอร์มของคุณเองหรือรวมเข้ากับโปรเจ็กต์ .NET ของคุณได้ [*ตัวแปลงข้ามแพลตฟอร์ม*](https://products.aspose.app/tex/conversion/tex) ดังกล่าวก็มีอยู่ในระบบนิเวศ Aspose ด้วย แต่เพื่อเรียกใช้ตัวอย่างเราต้องการ:"
p3: "Aspose.TeX สำหรับ .NET API ซึ่งเป็น API การจัดการและการแปลงเอกสารที่มีคุณลักษณะหลากหลาย มีประสิทธิภาพ และใช้งานง่ายสำหรับแพลตฟอร์ม C#"
p4: "เปิดตัวจัดการแพ็คเกจ NuGet และค้นหา Aspose.TeX และติดตั้ง คุณสามารถใช้คำสั่งต่อไปนี้จาก Package Manager Console"
---

{{<section feature1>}}
---
title: ขั้นตอนในการใช้ไดเร็กทอรี ZIP สำหรับเอาต์พุตไฟล์ TeX C#
h3: "รหัส C# สำหรับใช้ไดเรกทอรี ZIP สำหรับเอาต์พุต"
item1: "สร้างอินสแตนซ์ของ [*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)"
item2: "ระบุไดเร็กทอรีการทำงานของไฟล์ ZIP สำหรับเอาต์พุตโดยใช้คุณสมบัติ [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)"
item3: "ระบุคอนโซลเป็นเทอร์มินัลเอาต์พุตโดยใช้คลาส [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)"
item4: "กำหนดตัวเลือกสำหรับการบันทึกโดยใช้คลาส [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)"
item5: "เรียกใช้การแปลงโดยใช้วิธีการ [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) สำหรับ [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: ปรับแต่งผลลัพธ์
item7: "ในการสรุปไฟล์ ZIP เอาต์พุต ให้ใช้คลาส [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)"
---