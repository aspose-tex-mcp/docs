---
translation: true
template: /_templates/_output-to-disk-net.md
title: เขียนเอาต์พุต TeX ไปยังดิสก์ | .NET API โซลูชั่น
url: /net/output-to-disk/
description: ".NET API โซลูชันเพื่อทำงานกับ TeX เรียนรู้เกี่ยวกับตัวอย่างวิธีสร้างเอาต์พุตที่กำหนดเองสำหรับไฟล์ TeX ด้วยโค้ด C# สองสามบรรทัด"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: เขียนเอาต์พุต TeX ไปยังดิสก์
h2: "บันทึกผลลัพธ์ของการแปลงไฟล์ TeX เป็นดิสก์ผ่าน C# .NET"
---

{{<section overview>}}
---
p1: "TeX เป็นที่รู้จักในฐานะภาษาการเรียงพิมพ์ ซึ่งหมายความว่าคุณไม่ได้จัดรูปแบบข้อความของคุณในเอกสาร แต่ป้อนข้อความธรรมดาพร้อมกับคำสั่ง ตามที่ทราบจากบทความ [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) ของเอกสารประกอบ งาน TeX จะทำงานบนไฟล์ TeX ที่ระบุอย่างชัดเจน คุณยังอาจพบข้อมูลเกี่ยวกับโหมดการโต้ตอบ TeX และพื้นฐานที่เกี่ยวข้องกับอินพุตและเอาต์พุต TeX ได้อีกด้วย"
p2: "การใช้งานหลักของ TeX คือการช่วยสร้างการเขียนข้อความทางคณิตศาสตร์หรือทางเทคนิค แต่เมื่อไฟล์ถูกสร้างขึ้นแล้วและคุณไม่ต้องการให้มีการปรับเปลี่ยนใด ๆ เพิ่มเติม คุณอาจต้องการแปลงไฟล์ให้เป็นรูปแบบอื่นที่เป็นที่นิยมมากขึ้น"
p3: "ในหน้านี้ คุณจะพบตัวอย่างโค้ดที่อธิบายการใช้ไดเร็กทอรีระบบไฟล์สำหรับอินพุตและเอาต์พุต เอาต์พุตไปยังอุปกรณ์ XPS แทนที่ชื่องาน การเขียนเอาต์พุตเทอร์มินัลไปยังดิสก์ พูดง่ายๆ ก็คือ มันคือการแปลงที่มีการเขียนเอาต์พุตไปยังดิสก์ ในการเรียกใช้การดำเนินการดังกล่าว เราต้องการ:"
p4: "Aspose.TeX สำหรับ .NET API ซึ่งเป็น API การจัดการและการแปลงเอกสารที่มีคุณลักษณะหลากหลาย มีประสิทธิภาพ และใช้งานง่ายสำหรับแพลตฟอร์ม C#"
p5: "เปิดตัวจัดการแพ็คเกจ NuGet และค้นหา Aspose.TeX และติดตั้ง คุณสามารถใช้คำสั่งต่อไปนี้จาก Package Manager Console"
---

{{<section feature1>}}
---
title: "ขั้นตอนในการเขียนเอาต์พุตเทอร์มินัลไปยังดิสก์ C#:"
h3: "รหัส C# สำหรับแปลง TeX และเขียนเอาต์พุตไปยังดิสก์"
item1: "สร้างตัวเลือกการแปลงตามส่วนขยายเอ็นจิ้น ObjectTeX โดยใช้ [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) วิธีการของ [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) คลาส"
item2: "ระบุชื่องานถ้าคุณไม่ต้องการให้อาร์กิวเมนต์แรกของ TeXJob คอนสตรัคเตอร์ถูกใช้เป็นชื่องาน"
item3: "ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับอินพุต ใช้คลาส [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) สำหรับสิ่งนี้"
item4: "ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับเอาต์พุตด้วยความช่วยเหลือของเอนทิตีของคลาส [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)"
item5: "ระบุว่าต้องเขียนเอาต์พุตเทอร์มินัลไปยังไฟล์ในไดเร็กทอรีการทำงานของเอาต์พุต"
item6: "เรียกใช้งาน [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) วิธีการสำหรับ [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)"
---