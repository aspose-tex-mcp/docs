---
translation: true
template: /_templates/_create-custom-tex-net.md
title: 맞춤형 TeX 파일 | .NET API 솔루션
url: /net/create-custom-tex/
description: "TeX와 함께 작동하는 .NET API 솔루션. 사용자 정의 TeX 형식을 만드는 기능을 포함합니다. TeX를 사용자 정의하는 기능의 C# 예제."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 사용자 정의 TeX 형식 만들기
h2: "C# .NET을 통해 사용자 정의 TeX 형식의 파일 만들기"
---

{{<section overview>}}
---
p1: "TeX는 데이터 마크업 언어 중 하나로 알려져 있습니다. 출판 세트 시스템(컴퓨터 조판)의 핵심입니다. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/)를 프로그래밍 언어이기 때문에 파일 형식으로 간주하는 것은 의문입니다. 한편, 이 언어를 이해하는 것은 인터프리터 엔진입니다. 어쨌든, 간단히 말해서, 그것의 주요 목적은 수학적 또는 기술적 텍스트 작성을 돕는 것입니다. ΤeΧ를 기반으로 많은 다른 패킷이 생성되었습니다. 특히 공식이나 수학 방정식이 있을 때 문서를 더 쉽게 처리할 수 있도록 하기 위한 것입니다."
p2: "다른 기능 중 Aspose.TeX API 솔루션을 사용하면 자신만의 TeX 파일을 만들 수 있습니다. 여기에서 이러한 사용자 정의 형식의 파일을 만드는 방법을 설명하는 정보를 찾을 수 있습니다. 이러한 파일에는 사용자 정의된 엔진 옵션이 있습니다. 이를 위해 다음이 필요합니다."
p3: "Aspose.TeX for .NET API는 C# 플랫폼을 위한 기능이 풍부하고 강력하며 사용하기 쉬운 문서 조작 및 변환 API입니다."
p4: "NuGet 패키지 관리자를 열고 Aspose.TeX를 검색하여 설치합니다. 패키지 관리자 콘솔에서 다음 명령을 사용할 수도 있습니다."
---

{{<section feature1>}}
---
title: 사용자 정의 TeX 파일을 만드는 단계 C#.
h3: "TeX 파일을 사용자 정의하는 C# 코드"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 메서드 사용 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 클래스, ObjectTeX 엔진 확장 시 형식이 없는 TeX 엔진 옵션을 만듭니다."
item2: "[*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 클래스를 사용하여 입력에 대한 파일 시스템 작업 디렉터리를 지정합니다."
item3: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 클래스를 사용하여 출력에 대한 파일 시스템 작업 디렉터리를 지정합니다."
item4: "[*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) 메서드를 사용하여 형식을 만듭니다."
item5: 출력을 수정합니다.
---