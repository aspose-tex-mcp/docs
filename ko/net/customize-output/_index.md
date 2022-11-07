---
translation: true
template: /_templates/_customize-output-net.md
title: 사용자 정의 출력 만들기 TeX | .NET API 솔루션
url: /net/customize-output/
description: "TeX와 함께 작동하는 .NET API 솔루션. 몇 줄의 C# 코드로 TeX 파일에 대한 사용자 지정 출력을 만드는 방법의 예를 읽어보세요."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 출력 사용자 정의
h2: "TeX 파일의 출력을 사용자 정의하는 .NET API 솔루션"
---

{{<section overview>}}
---
p1: "TeX는 조판 언어로 알려져 있습니다. 문서에서 텍스트의 서식을 지정하지 않고 명령과 함께 일반 텍스트를 입력한다는 의미입니다."
p2: "문서의 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 기사에서는 TeX 파일이 조판할 데이터가 아니라 제어 시퀀스만 포함할 수 있다고 알려줍니다. . 그러나 일반적으로 그러한 데이터를 포함하고 대상 형식의 파일에는 조판 텍스트가 있습니다. 파일은 또한 입력으로 지정된 파일과 동일한 이름을 가지며 기본 출력 파일입니다. 원본 TeX의 경우 DVI 형식의 파일입니다. 작업 이름을 확장하지 않고 입력 및 출력 파일의 이름을 모두 호출합니다."
p3: "이 페이지에서는 TeX 파일의 출력을 사용자 정의하는 방법을 볼 수 있는 사용자 정의 TeX 형식 파일 생성을 설명하는 코드 예제를 찾을 수 있습니다. .tex 파일 출력을 사용자 정의하려면 다음이 필요합니다."
p4: "Aspose.TeX for .NET API는 C# 플랫폼을 위한 기능이 풍부하고 강력하며 사용하기 쉬운 문서 조작 및 변환 API입니다."
p5: "NuGet 패키지 관리자를 열고 Aspose.TeX를 검색하여 설치합니다. 패키지 관리자 콘솔에서 다음 명령을 사용할 수도 있습니다."
---

{{<section feature1>}}
---
title: "TeX 출력 C#을 사용자 정의하는 단계:"
h3: "TeX 출력 사용자 정의를 위한 C# 코드"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 메서드의 도움으로 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 클래스, ObjectTeX 엔진 확장 시 형식이 없는 TeX 엔진 옵션을 만듭니다."
item2: "[*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 클래스를 사용하여 입력에 대한 파일 시스템 작업 디렉터리를 지정합니다."
item3: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 클래스를 사용하여 출력에 대한 파일 시스템 작업 디렉터리를 지정합니다."
item4: "새 형식을 만들려면 [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) 메서드를 사용합니다."
item5: 출력을 수정합니다.
---