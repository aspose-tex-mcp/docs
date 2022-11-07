---
translation: true
template: /_templates/_customize-output-net.md
title: สร้างเอาต์พุตแบบกำหนดเอง TeX | .NET API โซลูชั่น
url: /net/customize-output/
description: ".NET API โซลูชันเพื่อทำงานกับ TeX อ่านตัวอย่างวิธีสร้างเอาต์พุตที่กำหนดเองสำหรับไฟล์ TeX ด้วยโค้ด C# สองสามบรรทัด"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: ปรับแต่งเอาต์พุต
h2: ".NET API Solution เพื่อปรับแต่งเอาต์พุตของไฟล์ TeX"
---

{{<section overview>}}
---
p1: "TeX เรียกว่าภาษาเรียงพิมพ์ หมายความว่าคุณไม่ได้จัดรูปแบบข้อความของคุณในเอกสาร แต่ป้อนข้อความธรรมดาพร้อมกับคำสั่ง"
p2: "บทความ [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) ของเอกสารประกอบสอนเราว่าไฟล์ TeX อาจไม่มีข้อมูลในการเรียงพิมพ์แต่มีเพียงลำดับการควบคุม . โดยปกติแล้วจะมีข้อมูลดังกล่าว และไฟล์ในรูปแบบเป้าหมายจะมีข้อความเรียงพิมพ์ ไฟล์จะมีชื่อเดียวกันกับไฟล์ที่ระบุเป็นอินพุตและเป็นไฟล์เอาต์พุตหลัก สำหรับ TeX ดั้งเดิม นี่คือไฟล์ในรูปแบบ DVI เราจะเรียกชื่อไฟล์ทั้งอินพุตและเอาต์พุตโดยไม่ขยายชื่องาน"
p3: "ในหน้านี้ คุณจะพบตัวอย่างโค้ดที่อธิบายการสร้างไฟล์รูปแบบ TeX แบบกำหนดเอง ซึ่งคุณสามารถดูวิธีปรับแต่งเอาต์พุตของไฟล์ TeX ได้ ในการปรับแต่งเอาต์พุตไฟล์ .tex เราต้องการ:"
p4: "Aspose.TeX สำหรับ .NET API ซึ่งเป็น API การจัดการและการแปลงเอกสารที่มีคุณลักษณะหลากหลาย มีประสิทธิภาพ และใช้งานง่ายสำหรับแพลตฟอร์ม C#"
p5: "เปิดตัวจัดการแพ็คเกจ NuGet และค้นหา Aspose.TeX และติดตั้ง คุณสามารถใช้คำสั่งต่อไปนี้จาก Package Manager Console"
---

{{<section feature1>}}
---
title: "ขั้นตอนในการปรับแต่ง TeX output C#:"
h3: "รหัส C# สำหรับการปรับแต่งเอาต์พุต TeX"
item1: "ด้วยความช่วยเหลือของ [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) วิธีการของ [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) คลาส สร้างตัวเลือกเอ็นจิน TeX สำหรับไม่มีรูปแบบตามส่วนขยายเอ็นจิ้น ObjectTeX"
item2: "ใช้ [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) คลาสเพื่อระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับอินพุต"
item3: "ใช้ [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class เพื่อระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับเอาต์พุต"
item4: "ในการสร้างรูปแบบใหม่ ให้ใช้ [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) Method"
item5: ปรับแต่งผลลัพธ์
---