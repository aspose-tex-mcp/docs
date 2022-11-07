---
translation: true
template: /_templates/_output-to-disk-net.md
title: TeX 출력을 디스크에 쓰기 | .NET API 솔루션
url: /net/output-to-disk/
description: "TeX와 함께 작동하는 .NET API 솔루션. 몇 줄의 C# 코드로 TeX 파일에 대한 사용자 지정 출력을 만드는 방법을 예제에서 알아보세요."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX 출력을 디스크에 쓰기
h2: "C# .NET을 통해 TeX 파일 변환 결과를 디스크로 저장"
---

{{<section overview>}}
---
p1: "TeX는 문서의 텍스트 형식을 지정하지 않고 명령과 함께 일반 텍스트를 입력하는 것을 의미하는 조판 언어로 알려져 있습니다. 문서의 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 기사에서 알 수 있듯이 TeX 작업은 명시적으로 지정된 TeX 파일에서 실행됩니다. 거기에서 TeX 입력 및 출력과 관련된 TeX 상호 작용 모드 및 기본 요소에 대한 정보도 찾을 수 있습니다."
p2: "TeX의 주요 용도는 수학적 또는 기술적인 텍스트 작성을 돕는 것입니다. 그러나 파일이 이미 생성되어 더 이상 조작하지 않으려면 파일을 더 널리 사용되는 다른 형식으로 변환할 수 있습니다."
p3: "이 페이지에서는 입력 및 출력에 파일 시스템 디렉토리 사용, XPS 장치로 출력, 작업 이름 재정의, 터미널 출력을 디스크에 쓰는 방법을 설명하는 코드 예제를 찾을 수 있습니다. 간단히 말해서 출력을 디스크에 쓰는 변환입니다. 이러한 작업을 실행하려면 다음이 필요합니다."
p4: "Aspose.TeX for .NET API는 C# 플랫폼을 위한 기능이 풍부하고 강력하며 사용하기 쉬운 문서 조작 및 변환 API입니다."
p5: "NuGet 패키지 관리자를 열고 Aspose.TeX를 검색하여 설치합니다. 패키지 관리자 콘솔에서 다음 명령을 사용할 수도 있습니다."
---

{{<section feature1>}}
---
title: "터미널 출력을 디스크 C#에 쓰는 단계:"
h3: "TeX를 변환하고 출력을 디스크에 쓰기 위한 C# 코드"
item1: "[*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)의 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 메서드를 사용하여 ObjectTeX 엔진 확장 시 변환 옵션 생성 클래스."
item2: "TeXJob 생성자의 첫 번째 인수를 작업 이름으로 사용하지 않으려면 작업 이름을 지정하십시오."
item3: "입력에 대한 파일 시스템 작업 디렉토리를 지정하십시오. 이를 위해 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 클래스를 사용합니다."
item4: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 클래스의 엔터티를 사용하여 출력에 대한 파일 시스템 작업 디렉터리를 지정합니다."
item5: "터미널 출력이 출력 작업 디렉토리의 파일에 기록되어야 함을 지정합니다."
item6: "[*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)에 대한 작업 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 메서드 실행."
---