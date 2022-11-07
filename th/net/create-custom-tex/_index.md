---
translation: true
template: /_templates/_create-custom-tex-net.md
title: ไฟล์ TeX แบบกำหนดเอง | .NET API โซลูชั่น
url: /net/create-custom-tex/
description: ".NET API โซลูชันเพื่อทำงานกับ TeX รวมฟังก์ชันการทำงานเพื่อสร้างรูปแบบ TeX ที่กำหนดเอง ตัวอย่างฟังก์ชัน C# เพื่อปรับแต่ง TeX"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: สร้างรูปแบบ TeX แบบกำหนดเอง
h2: "สร้างไฟล์รูปแบบ TeX ที่กำหนดเองผ่าน C# .NET"
---

{{<section overview>}}
---
p1: "TeX เป็นที่รู้จักว่าเป็นหนึ่งในภาษามาร์กอัปข้อมูล เป็นแกนหลักของระบบชุดสิ่งพิมพ์ (การเรียงพิมพ์ด้วยคอมพิวเตอร์) การพิจารณา [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) เป็นรูปแบบไฟล์ที่น่าสงสัย เนื่องจากเป็นภาษาโปรแกรม และในทางกลับกัน มันเป็นเครื่องมือล่ามที่เข้าใจภาษานี้ อย่างไรก็ตาม ในระยะสั้น จุดประสงค์หลักของมันคือเพื่อช่วยในการสร้างการเขียนข้อความทางคณิตศาสตร์หรือทางเทคนิค แพ็กเก็ตที่แตกต่างกันจำนวนมากถูกสร้างขึ้นบนพื้นฐานของ ΤeΧ มีจุดมุ่งหมายเพื่อให้ง่ายต่อการประมวลผลเอกสาร โดยเฉพาะอย่างยิ่งเมื่อมีสูตรหรือสมการทางคณิตศาสตร์"
p2: "โซลูชัน Aspose.TeX API ท่ามกลางคุณสมบัติอื่น ๆ ช่วยให้คุณสร้างไฟล์ TeX ที่โดดเด่นของคุณเองได้ ที่นี่คุณจะพบข้อมูลที่อธิบายวิธีสร้างไฟล์ที่มีรูปแบบที่กำหนดเองดังกล่าว ไฟล์ดังกล่าวจะมีตัวเลือกเอ็นจิ้นที่ปรับแต่งเอง สำหรับสิ่งนี้เราต้องการ:"
p3: "Aspose.TeX สำหรับ .NET API ซึ่งเป็น API การจัดการและการแปลงเอกสารที่มีคุณลักษณะหลากหลาย มีประสิทธิภาพ และใช้งานง่ายสำหรับแพลตฟอร์ม C#"
p4: "เปิดตัวจัดการแพ็คเกจ NuGet และค้นหา Aspose.TeX และติดตั้ง คุณสามารถใช้คำสั่งต่อไปนี้จาก Package Manager Console"
---

{{<section feature1>}}
---
title: ขั้นตอนในการสร้างไฟล์ TeX แบบกำหนดเอง C#
h3: "รหัส C# เพื่อปรับแต่งไฟล์ TeX"
item1: "การใช้ [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) วิธีการของ [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) คลาส สร้างตัวเลือกเอ็นจิน TeX สำหรับไม่มีรูปแบบตามส่วนขยายเอ็นจิ้น ObjectTeX"
item2: "ใช้ [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) คลาส ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับอินพุต"
item3: "ใช้ [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class เพื่อระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับเอาต์พุต"
item4: "สร้างรูปแบบโดยใช้วิธี [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)"
item5: ปรับแต่งผลลัพธ์
---