---
title: 명령줄에서 CPU 사용량 측정
description: 명령줄에서 애플리케이션의 CPU 성능을 측정합니다.
ms.custom: ''
ms.date: 02/19/2019
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools, command-line
- Diagnostics Tools, command-line
- CPU Usage, command-line
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: '>= vs-2019'
ms.workload:
- multiple
ms.openlocfilehash: b2de537b17b68461c16f886c1eab706d2438ff6c
ms.sourcegitcommit: 62149c96de0811415e99bb1e0194e76c320e1a1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "57007500"
---
# <a name="measure-application-performance-from-the-command-line"></a>명령줄에서 애플리케이션 성능 측정

명령줄 도구를 사용하여 애플리케이션에 대한 성능 정보를 수집할 수 있습니다.

이 문서에 설명된 예제에서는 Microsoft Notepad에 대한 성능 정보를 수집하지만 동일한 방법을 사용하여 모든 프로세스를 프로파일링할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2019 미리 보기 3 이상 버전

* 명령줄 도구 사용 경험

## <a name="collect-performance-data"></a>성능 데이터 수집

Visual Studio 진단 CLI 도구를 사용하여 프로파일링 도구를 수집기 에이전트 중 하나와 함께 프로세스에 연결하면 프로파일링이 작동합니다. 프로파일링 도구를 연결하면 도구가 중지될 때까지 프로파일링 데이터를 캡처하고 저장하는 진단 세션을 시작합니다. 이때 해당 데이터는 *.diagsession* 파일로 내보내집니다. 그런 다음, Visual Studio에서 이 파일을 열어 결과를 분석할 수 있습니다.

1. 메모장을 시작한 다음, 작업 관리자를 열어 프로세스 ID(PID)를 가져옵니다. 작업 관리자의 **세부 정보** 탭에서 PID를 찾습니다.

1. 명령 프롬프트를 열고 일반적으로 여기에 컬렉션 에이전트 실행 파일을 사용하여 디렉터리로 변경합니다.

   ```<Visual Studio installation folder>\2019\Preview\Team Tools\DiagnosticsHub\Collector\```

1. 다음 명령을 입력하여 *VSDiagnostics.exe*를 시작합니다.

   ```cmd
   VSDiagnostics.exe start <id> /attach:<pid> /loadConfig:<configFile>
   ```

   포함되어야 하는 인수는 다음과 같습니다.

   * \<*id*> 컬렉션 세션을 식별합니다. ID는 1~255 사이의 숫자여야 합니다.
   * \<*pid*> 프로파일링하려는 프로세스의 PID(이 경우 1단계에서 찾은 PID)
   * \<*configFile*> 시작하려는 컬렉션 에이전트의 구성 파일입니다. 자세한 내용은 [에이전트의 구성 파일](#config_file)을 참조하세요.

1. 메모장의 크기를 조정하거나 몇 가지 흥미로운 프로파일링 정보가 수집되는지 확인하기 위해 항목을 입력합니다.

1. 컬렉션 세션을 중지하고 다음 명령을 입력하여 출력을 파일로 보냅니다.

   ```cmd
   VSDiagnostics.exe stop <id> /output:<path to file>
   ```

1. 이전 명령의 파일 출력으로 이동하여 Visual Studio에서 열어 수집된 정보를 검사합니다.

## <a name="config_file"></a> 에이전트 구성 파일

컬렉션 에이전트는 측정하려는 항목에 따라 서로 다른 유형의 데이터를 수집하는 상호 교환이 가능한 구성 요소입니다.

편의를 위해 에이전트 구성 파일에 해당 정보를 저장할 수 있습니다. 구성 파일은 최소한 *.dll*의 이름과 해당 COM CLSID를 포함하는 *.json* 파일입니다. 다음 폴더에서 찾을 수 있는 구성 파일의 예제는 다음과 같습니다.

```<Visual Studio installation folder>\2019\Preview\Team Tools\DiagnosticsHub\Collector\AgentConfigs\```

* CpuUsage 구성(기본/높음/낮음)은 [CPU 사용량](../profiling/cpu-usage.md) 프로파일링 도구에 대해 수집된 데이터에 해당합니다.
* DotNetObjectAlloc 구성(기본/낮음)은 [.NET 개체 할당 도구](https://devblogs.microsoft.com/visualstudio/visual-studio-2017-version-15-8-preview-3/#tooling)에 대해 수집된 데이터에 해당합니다.

기본/낮음/높음 구성은 샘플링 주기를 참조하세요. 예를 들어 낮음은 100 샘플/초이고 높음은 4000 샘플/초입니다.

컬렉션 에이전트와 함께 작동하는 *VSDiagnostics.exe* 도구의 경우, 해당 에이전트에 DLL 및 COM CLSID가 모두 필요하며 에이전트에도 추가 구성 옵션이 있을 수 있습니다. 구성 파일 없이 에이전트를 사용하는 경우 다음 명령의 형식을 사용합니다.

```cmd
VSDiagnostics.exe start <id> /attach:<pid> /loadAgent:<agentCLSID>;<agentName>[;<config>]
```

## <a name="permissions"></a>사용 권한

높은 권한이 필요한 애플리케이션을 프로파일링하려면 관리자 권한 명령 프롬프트에서 수행해야 합니다.




