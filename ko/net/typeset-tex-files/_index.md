---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: TeX 조판 기능 | .NET API
url: /net/typeset-tex-files/
description: "TeX와 함께 작동하는 .NET API 솔루션. 몇 줄의 C# 코드로 TeX 조판을 만드는 방법을 예제에서 배우십시오."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX 파일 조판
h2: "사용자 정의 TeX 형식 C# .NET을 사용하여 TeX 파일 조판"
---

{{<section overview>}}
---
p1: "TeX는 데이터 마크업 언어 및/또는 조판 언어 중 하나로 알려져 있습니다. 문서에서 텍스트의 서식을 지정하지 않고 명령과 함께 일반 텍스트를 입력한다는 의미입니다. 출력으로 필요한(지정된) 형식의 형식화된 파일을 얻을 수 있습니다. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/)는 출판 세트 시스템(컴퓨터 조판)의 중심 코어입니다."
p2: "TeX 조판에 대한 더 많은 이해를 얻으려면 문서의 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/)를 배우십시오. 그리고 이 페이지에서 사용자 정의 TeX 형식을 사용하여 TeX 파일을 조판하는 방법을 설명하는 코드 조각을 찾을 수 있습니다."
p3: "예제를 실행하려면 다음이 필요합니다."
p4: "Aspose.TeX for .NET API는 C# 플랫폼을 위한 기능이 풍부하고 강력하며 사용하기 쉬운 문서 조작 및 변환 API입니다."
p5: "NuGet 패키지 관리자를 열고 Aspose.TeX를 검색하여 설치합니다. 패키지 관리자 콘솔에서 다음 명령을 사용할 수도 있습니다."
---

{{<section feature1>}}
---
title: C#을 사용하여 TeX를 조판하는 단계.
h3: "TeX 조판을 위한 C# 코드"
item1: "[*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 클래스를 사용하여 형식 공급자를 만듭니다."
item2: "[*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 클래스."
item3: "기본 입력이 스트림으로 제공되지 않는 경우 입력 작업 디렉토리를 지정하십시오. 이를 위해 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 클래스를 사용합니다."
item4: "출력을 위한 파일 시스템 작업 디렉토리를 지정하십시오. 이를 위해 [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 클래스를 사용합니다."
item5: "[*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)에 대한 작업 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 메서드 실행."
item6: 출력을 수정합니다.
---