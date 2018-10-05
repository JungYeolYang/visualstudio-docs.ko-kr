---
title: 대상 및 작업 구성 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7756e649fe9bc5907c888ae6141bed45eae8ccae
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551488"
---
# <a name="configuring-targets-and-tasks"></a>대상 및 작업 구성
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [대상 및 작업 구성](https://docs.microsoft.com/visualstudio/msbuild/configuring-targets-and-tasks)합니다.  
  
  
MSBuild 대상 및 작업을 구성하여 MSBuild를 통해 out-of-process로 실행할 수 있으므로 현재 실행하고 있는 컨텍스트와는 다른 컨텍스트를 대상으로 지정할 수 있습니다. 예를 들어, 개발 컴퓨터가 64비트 .NET Framework 4.5 운영 체제에서 실행되는 동안 32비트 .NET Framework 2.0 응용 프로그램을 대상으로 지정할 수 있습니다. 또한 .NET Framework 4 또는 이전 버전을 실행하는 컴퓨터를 대상으로 지정할 수 있습니다. 32비트 또는 64비트 및 특정 .NET Framework 버전의 조합은 *대상 컨텍스트*로 알려져 있습니다.  
  
## <a name="installation"></a>설치  
 .NET Framework 4.5 및 4.5.1은 CLR(공용 언어 런타임), 대상, 작업 및 .NET Framework 4의 도구를 이름을 바꾸지 않고 대체합니다. .NET Framework 4.5.1이 [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)]의 부분으로 설치됩니다.  
  
 Visual Studio와 개별적으로 MSBuild를 설치하려면 [MSBuild 다운로드](http://go.microsoft.com/fwlink/?LinkId=309745)에서 설치 패키지를 다운로드할 수 있습니다. 또한 사용하려는 .NET Framework 버전도 설치해야 합니다.  
  
## <a name="targets-and-tasks"></a>대상 및 작업  
 MSBuild는 특정 빌드 작업을 프로세스 외부에서 실행하여 더 큰 컨텍스트 집합을 대상으로 지정합니다.  예를 들어, 32비트 MSBuild가 64비트 프로세스에서 빌드 작업을 실행하여 64비트 컴퓨터를 대상으로 지정할 수 있습니다. 이 작업은 `UsingTask` 인수 및 `Task` 매개 변수에 의해 제어됩니다. .NET Framework 4.5에 의해 설치된 대상은 이러한 인수 및 매개 변수를 설정하고, 다양한 대상 컨텍스트를 위한 응용 프로그램을 빌드하는 데 필요한 변경 사항은 없습니다.  
  
 대상 컨텍스트를 직접 만들려면 이러한 인수 및 매개 변수를 적절하게 설정해야 합니다. .NET Framework 4.5 Microsoft.Common.targets 파일과 Microsoft.Common.Tasks 파일에서 예제를 살펴봅니다.  여러 대상 컨텍스트를 사용하여 작업할 수 있는 사용자 지정 작업 만들기 또는 기존 작업을 수정하는 방법에 대한 자세한 내용은 [방법: 대상 및 작업 구성](../msbuild/how-to-configure-targets-and-tasks.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [멀티 타기팅](../msbuild/msbuild-multitargeting-overview.md)


