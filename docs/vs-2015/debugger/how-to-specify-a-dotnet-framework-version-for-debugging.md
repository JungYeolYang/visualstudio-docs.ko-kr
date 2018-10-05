---
title: '방법: 디버깅을 위한.NET Framework 버전 지정 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- .NET Framework, specifying version for debugging
- debugging [Visual Studio], specifying .NET Framework version
ms.assetid: 7a4893ba-4620-4774-893f-378d4ca28893
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a07975591525f9109fecfbfb5aaa27642fc9562
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550248"
---
# <a name="how-to-specify-a-net-framework-version-for-debugging"></a>방법: 디버깅을 위한 .NET Framework 버전 지정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법:.NET Framework 버전에 대 한 디버깅 지정](https://docs.microsoft.com/visualstudio/debugger/how-to-specify-a-dotnet-framework-version-for-debugging)합니다.  
  
[!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] 디버거는 현재 버전을 비롯하여 이전 버전의 Microsoft [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 디버깅을 지원합니다. 디버거가 올바른 버전의 Visual Studio에서 응용 프로그램을 시작 하는 경우 식별할 항상 수는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 디버깅 하는 응용 프로그램에 대 한 합니다. 응용 프로그램이 이미 실행 되 고 사용 하는 경우 **연결할**, 디버거 항상 못할의 이전 버전을 식별 하는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]합니다. 이러한 문제가 발생하면 다음과 같은 오류 메시지가 표시됩니다.  
  
 디버거가 응용 프로그램에서 사용하는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 버전을 잘못 예상했는지 확인합니다.  
  
 드물기는 하지만 이러한 문제가 발생하면 레지스트리 키를 설정하여 디버거에 사용하려는 버전을 지정할 수 있습니다.  
  
### <a name="to-specify-a-net-framework-version-for-debugging"></a>디버깅을 위한 .NET Framework 버전을 지정하려면  
  
1.  Windows\Microsoft.NET\Framework 디렉터리에서 컴퓨터에 설치되어 있는 .NET Framework의 버전을 확인합니다. 버전 번호는 다음과 비슷합니다.  
  
     `V1.1.4322`  
  
     올바른 버전 번호를 확인하여 기록해 둡니다.  
  
2.  시작 합니다 **레지스트리 편집기** (regedit).  
  
3.  에 **레지스트리 편집기**에서 HKEY_LOCAL_MACHINE 폴더를 엽니다.  
  
4.  이동할: HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine\\{449EC4CC-30D2-4032-9256-EE18EB41B62B}  
  
     키가 없으면 HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine를 마우스 오른쪽 단추로 클릭 하 고 클릭 **새 키**합니다. 새 키 이름을 `{449EC4CC-30D2-4032-9256-EE18EB41B62B}`입니다.  
  
5.  {449EC4CC-30D2-4032-9256-EE18EB41B62B}를 탐색 한 후 확인 합니다 **이름** 열을 찾고 CLRVersionForDebugging 키입니다.  
  
    1.  키가 없으면 {449EC4CC-30D2-4032-9256-EE18EB41B62B}를 마우스 오른쪽 단추로 클릭 하 고 클릭 **새 문자열 값**합니다. 새 문자열 값을 마우스 오른쪽 단추로 클릭, 클릭 **이름 바꾸기**, 및 형식 `CLRVersionForDebugging`합니다.  
  
6.  두 번 클릭 **CLRVersionForDebugging**합니다.  
  
7.  에 **문자열 편집** 상자에.NET Framework 버전 번호를 입력 합니다 **값** 상자. 예를 들어 V1.1.4322 같은 형식입니다.  
  
8.  **확인**을 클릭합니다.  
  
9. 닫기 합니다 **레지스트리 편집기**합니다.  
  
     디버깅을 시작할 때 여전히 오류 메시지가 표시되면 레지스트리에 버전 번호를 올바르게 입력했는지 확인합니다. 현재 사용하고 있는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 버전이 Visual Studio에서 지원되는지 여부도 확인합니다. 현재 디버거는 .NET Framework 버전 및 이전 버전과 호환되지만 이후 버전과는 호환되지 않을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)


