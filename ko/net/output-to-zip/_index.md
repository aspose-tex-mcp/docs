---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX에서 ZIP으로 | .NET API 솔루션
url: /net/output-to-zip/
description: "TeX와 함께 작동하는 .NET API 솔루션. TeX에서 ZIP으로의 변환 기능을 사용하면 TeX 파일을 가장 인기 있는 아카이브로 저장할 수 있습니다. 이 기능의 C# 예제입니다."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: ZIP에 출력 쓰기
h2: "C# .NET을 통해 TeX 파일 변환 결과를 ZIP으로 저장"
---

{{<section overview>}}
---
p1: "TeX는 데이터 마크업 언어 중 하나로 알려져 있습니다. 출판 세트 시스템(컴퓨터 조판)의 핵심입니다. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/)를 프로그래밍 언어이기 때문에 파일 형식으로 간주하는 것은 의문입니다. 한편, 이 언어를 이해하는 것은 인터프리터 엔진입니다. 어쨌든, 간단히 말해서, 그것의 주요 목적은 수학적 또는 기술적 텍스트 작성을 돕는 것입니다. 그러나 파일이 이미 생성되어 더 이상 조작하지 않으려면 파일을 더 널리 사용되는 다른 형식으로 변환할 수 있습니다."
p2: "다른 기능 중 Aspose.TeX API 솔루션을 사용하면 TeX 파일을 변환한 다음 그 결과를 ZIP 아카이브로 저장할 수 있습니다. 여기에서 TeX를 PDF로 변환하고 결과의 출력을 zip으로 저장하는 방법에 대한 코드 스니펫을 찾을 수 있습니다. API 변환기는 C#에서 지원하는 모든 언어를 사용하여 TeX를 변환합니다. 여기에서 볼 수 있는 API를 사용하여 자체 플랫폼 간 응용 프로그램을 만들거나 .NET 프로젝트에 통합할 수도 있습니다. 이러한 [*교차 플랫폼 변환기*](https://products.aspose.app/tex/conversion/tex)도 Aspose 생태계에 존재합니다. 그러나 예제를 실행하려면 다음이 필요합니다."
p3: "Aspose.TeX for .NET API는 C# 플랫폼을 위한 기능이 풍부하고 강력하며 사용하기 쉬운 문서 조작 및 변환 API입니다."
p4: "NuGet 패키지 관리자를 열고 Aspose.TeX를 검색하여 설치합니다. 패키지 관리자 콘솔에서 다음 명령을 사용할 수도 있습니다."
---

{{<section feature1>}}
---
title: 출력 TeX 파일에 ZIP 디렉토리를 사용하는 단계 C#.
h3: "출력에 ZIP 디렉토리를 사용하기 위한 C# 코드"
item1: "[*TeXOptions 클래스*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)의 인스턴스를 만듭니다."
item2: "[*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) 속성을 사용하여 출력에 대한 ZIP 아카이브 작업 디렉터리를 지정합니다."
item3: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) 클래스를 사용하여 콘솔을 출력 터미널로 지정합니다."
item4: "[*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) 클래스를 사용하여 저장 옵션을 정의합니다."
item5: "[*PdfDevice*](https://reference.aspose.com/tex/)에 대한 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 메서드를 사용하여 변환 실행 net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: 출력을 수정합니다.
item7: "출력 ZIP 아카이브를 완료하려면 [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) 클래스를 사용하십시오."
---