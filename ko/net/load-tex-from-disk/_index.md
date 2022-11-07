---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: 디스크에서 TeX 로드 | .NET API 솔루션
url: /net/load-tex-from-disk/
description: "TeX와 함께 작동하는 .NET API 솔루션. 몇 줄의 C# 코드로 디스크에서 TeX 파일을 로드하는 방법을 예제에서 알아보세요."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 디스크에서 TeX 소스 파일 로드
h2: "디스크에서 TeX/LaTeX 파일을 로드하는 .NET API 솔루션"
---

{{<section overview>}}
---
p1: "TeX는 조판 언어로 알려져 있습니다. 문서에서 텍스트의 서식을 지정하지 않고 명령과 함께 일반 텍스트를 입력한다는 의미입니다. 출력으로 필요한(지정된) 형식의 형식화된 파일을 얻을 수 있습니다. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/)는 출판 세트 시스템(컴퓨터 조판)의 중심 코어입니다. TeX 작업은 명시적으로 지정된 TeX 파일에서 실행됩니다. TeX 입력 및 출력에 대한 더 많은 이해를 얻으려면 문서의 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/)를 배우십시오."
p2: "알려진 바와 같이 TeX의 주요 목적은 수학적 또는 기술적인 텍스트 작성을 돕는 것입니다. 그러나 조작하기 전에 먼저 파일을 로드해야 합니다. 여기에서 입력 및 출력을 위한 파일 시스템 디렉토리를 사용하여 디스크에서 TeX 소스 파일을 로드하고, XPS 장치로 출력하고, 콘솔에 터미널 출력을 쓰는 방법을 설명하는 코드 조각을 찾을 수 있습니다."
p3: "예제를 실행하려면 다음이 필요합니다."
p4: "Aspose.TeX for .NET API는 C# 플랫폼을 위한 기능이 풍부하고 강력하며 사용하기 쉬운 문서 조작 및 변환 API입니다."
p5: "NuGet 패키지 관리자를 열고 Aspose.TeX를 검색하여 설치합니다. 패키지 관리자 콘솔에서 다음 명령을 사용할 수도 있습니다."
---

{{<section feature1>}}
---
title: 디스크 C#에서 TeX를 로드하는 단계.
h3: "TeX 로딩을 위한 C# 코드"
item1: "[*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 클래스."
item2: "입력에 대한 파일 시스템 작업 디렉토리를 지정하십시오. 이를 위해 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 클래스를 사용합니다."
item3: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 클래스를 사용하여 출력에 대한 파일 시스템 작업 디렉터리를 지정합니다."
item4: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) 클래스를 사용하여 콘솔을 출력 터미널로 지정합니다."
item5: "필요한 경우 메모리 터미널을 출력 터미널로 지정하십시오. 이를 위해 [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) 클래스를 사용합니다."
item6: "[*XpsDevice*](https://reference.aspose.com/tex/)에 대한 작업 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 메서드 실행 net/aspose.tex.presentation.xps/xpsdevice/)."
item7: 출력을 수정합니다.
---