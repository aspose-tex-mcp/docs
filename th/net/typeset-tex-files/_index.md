---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: ฟังก์ชันการเรียงพิมพ์ TeX | .NET API
url: /net/typeset-tex-files/
description: ".NET API โซลูชันเพื่อทำงานกับ TeX เรียนรู้เกี่ยวกับตัวอย่างวิธีสร้าง TeX typesets ด้วยโค้ด C# สองสามบรรทัด"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: เรียงพิมพ์ไฟล์ TeX
h2: "พิมพ์ไฟล์ TeX โดยใช้รูปแบบ TeX ที่กำหนดเอง C# .NET"
---

{{<section overview>}}
---
p1: "TeX เป็นที่รู้จักในฐานะหนึ่งในภาษามาร์กอัปข้อมูลและ/หรือภาษาการเรียงพิมพ์ในเวลาเดียวกัน หมายความว่าคุณไม่ได้จัดรูปแบบข้อความของคุณในเอกสาร แต่ป้อนข้อความธรรมดาพร้อมกับคำสั่ง คุณจะได้รับไฟล์ที่จัดรูปแบบตามรูปแบบที่ต้องการ (ระบุ) [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) เป็นแกนกลางของระบบชุดสิ่งพิมพ์ (การเรียงพิมพ์ด้วยคอมพิวเตอร์)"
p2: "เพื่อให้เข้าใจการเรียงพิมพ์ TeX มากขึ้น โปรดเรียนรู้ [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) ของเอกสารประกอบ และในหน้านี้ คุณจะพบข้อมูลโค้ดที่อธิบายวิธีพิมพ์ไฟล์ TeX โดยใช้รูปแบบ TeX ที่กำหนดเอง"
p3: "ในการรันตัวอย่างเราต้องการ:"
p4: "Aspose.TeX สำหรับ .NET API ซึ่งเป็น API การจัดการและการแปลงเอกสารที่มีคุณลักษณะหลากหลาย มีประสิทธิภาพ และใช้งานง่ายสำหรับแพลตฟอร์ม C#"
p5: "เปิดตัวจัดการแพ็คเกจ NuGet และค้นหา Aspose.TeX และติดตั้ง คุณสามารถใช้คำสั่งต่อไปนี้จาก Package Manager Console"
---

{{<section feature1>}}
---
title: ขั้นตอนในการเรียงพิมพ์ TeX โดยใช้ C#
h3: "รหัส C# สำหรับการเรียงพิมพ์ TeX"
item1: "สร้างผู้ให้บริการรูปแบบโดยใช้คลาส [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)"
item2: "สร้างตัวเลือกการแปลงสำหรับรูปแบบที่กำหนดเองตามส่วนขยายเอ็นจิน ObjectTeX โดยใช้ [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) วิธีการของ [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) คลาส"
item3: "ระบุไดเร็กทอรีการทำงานของอินพุต ถ้าอินพุตหลักไม่ได้ระบุเป็นสตรีม ใช้คลาส [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) สำหรับสิ่งนี้"
item4: "ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับเอาต์พุต ใช้คลาส [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) สำหรับสิ่งนี้"
item5: "เรียกใช้งาน [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) วิธีการสำหรับ [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)"
item6: ปรับแต่งผลลัพธ์
---