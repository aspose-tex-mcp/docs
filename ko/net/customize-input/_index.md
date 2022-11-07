---
translation: true
template: /_templates/_customize-input-net.md
title: 사용자 정의 입력 만들기 TeX | .NET API 솔루션
url: /net/customize-input/
description: "TeX와 함께 작동하는 .NET API 솔루션. 몇 줄의 C# 코드로 TeX 파일에 대한 사용자 지정 입력을 만드는 방법을 예제에서 알아보세요."
keywords: 사용자 지정 입력 tex net api, tex 사용자 지정을 위한 C# API
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 입력 사용자 정의
h2: "TeX 파일의 입력을 사용자 정의하는 .NET API 솔루션"
---

{{<section overview>}}
---
p1: "TeX는 조판 언어로 알려져 있습니다. 문서에서 텍스트의 서식을 지정하지 않고 명령과 함께 일반 텍스트를 입력한다는 의미입니다. 문서의 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 기사에 설명되어 있듯이 TeX 작업은 명시적으로 지정된 TeX 파일에서 실행됩니다. 따라서 우리는 이 파일을 특정 TeX 작업의 입력에 포함합니다."
p2: "이 페이지에서는 입력이 TeX 구문을 따라야 하고 이상적으로는 엔진에 알려진 명령만 포함해야 한다는 점을 고려하여 TeX 소스 파일의 입력을 사용자 정의하는 방법을 설명하는 코드 예제를 찾을 수 있습니다."
p3: ".tex 파일 입력을 사용자 정의하려면 다음이 필요합니다."
p4: "Aspose.TeX for .NET API는 C# 플랫폼을 위한 기능이 풍부하고 강력하며 사용하기 쉬운 문서 조작 및 변환 API입니다."
p5: "NuGet 패키지 관리자를 열고 Aspose.TeX를 검색하여 설치합니다. 패키지 관리자 콘솔에서 다음 명령을 사용할 수도 있습니다."
---

{{<section feature1>}}
---
title: "TeX 입력 C# 사용자 지정 단계:"
h3: "TeX 입력 사용자 지정을 위한 C# 코드"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 메서드 사용 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 클래스, ObjectTeX 엔진 확장 시 형식이 없는 TeX 엔진 옵션을 만듭니다."
item2: "[*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 클래스를 사용하여 입력에 대한 파일 시스템 작업 디렉터리를 지정합니다."
item3: "[*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) 메서드를 사용하여 사용자 지정 형식을 만듭니다."
---