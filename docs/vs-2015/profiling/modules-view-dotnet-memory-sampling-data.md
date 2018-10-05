---
title: 모듈 뷰 - .NET 메모리 샘플링 데이터 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Modules view
ms.assetid: 9c05b51a-8382-44cf-a8f7-3fabdd2e8f1b
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f1596d85e2668090533df9021c964d6767d36b38
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550460"
---
# <a name="modules-view---net-memory-sampling-data"></a>모듈 뷰 - .NET 메모리 샘플링 데이터
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [모듈 뷰-.NET 메모리 샘플링 데이터](https://docs.microsoft.com/visualstudio/profiling/modules-view-dotnet-memory-sampling-data)입니다.  
  
샘플링 방법을 사용하여 수집되는 .NET 메모리 할당 데이터의 모듈 뷰에서는 프로파일링 실행에서 실행된 모듈을 기준으로 메모리 데이터를 그룹화합니다. 각 모듈은 계층 트리의 루트입니다. 모듈의 함수는 모듈 노드 아래에 나열됩니다.  
  
 메모리를 할당하는 문의 소스 파일 줄 번호는 함수 노드 아래에 나열되며 할당을 수행하는 명령의 주소는 줄 노드 아래에 나열됩니다. 포괄 및 전용 값은 줄 데이터와 명령 데이터에 대해 항상 동일합니다.  
  
|열|설명|  
|------------|-----------------|  
|**이름**|모듈, 함수, 줄 번호 또는 명령 주소의 이름입니다.|  
|**프로세스 ID**|프로파일링 실행의 PID(프로세스 ID)입니다.|  
|**프로세스 이름**|프로세스의 이름입니다.|  
|**모듈 이름**|함수가 포함된 모듈의 이름입니다.|  
|**모듈 경로**|모듈의 경로입니다.|  
|**소스 파일**|이 함수의 정의가 포함된 소스 파일입니다.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**포함 할당**|-   함수의 경우 함수에 의해 생성된 개체의 총 수입니다. 이 수에는 이 함수가 호출한 함수에 생성된 개체가 포함됩니다.<br />-   모듈의 경우 모듈의 함수 중 하나 이상이 실행 중인 동안 할당된 프로파일링 실행의 개체 수입니다. 이 수에는 모듈 함수가 호출한 함수에 생성된 개체가 포함됩니다.<br />-   줄이나 명령의 경우 해당 줄 또는 명령에 의해 할당된 총 개체 수입니다.|  
|**포함 할당 비율(%)**|모듈, 함수, 줄 또는 명령의 포함 할당인 프로파일링 실행에서 할당된 모든 개체의 비율입니다.|  
|**제외 할당**|-   현재 함수의 경우 함수가 함수 본문의 코드를 실행하고 있을 때(즉, 함수가 호출 스택의 맨 위에 있을 때) 생성된 개체의 수입니다. 이 수에는 이 함수가 호출한 함수에 생성된 개체는 포함되지 않습니다.<br />-   모듈의 경우 모듈 내 함수의 제외 할당 합계입니다.<br />-   줄이나 명령의 경우 이 줄 또는 명령에 의해 생성된 총 개체 수입니다.|  
|**제외 할당 비율(%)**|모듈, 함수, 줄 또는 명령의 제외 할당인 프로파일링 실행에서 할당된 모든 개체의 비율입니다.|  
|**포함 바이트**|-   함수의 경우 함수에 의해 할당된 바이트 수입니다. 이 수에는 이 함수가 호출한 함수에서 할당된 바이트가 포함됩니다.<br />-   모듈의 경우 프로파일링 실행에서 할당되었으며 모듈의 함수 중 하나 이상이 실행 중인 동안 할당된 바이트 수입니다. 이 수에는 모듈 함수가 호출한 모든 함수에 생성된 개체가 포함됩니다.<br />-   줄이나 명령의 경우 해당 줄 또는 명령에 의해 생성된 총 개체 수입니다.|  
|**포함 바이트 비율(%)**|모듈, 함수, 줄 또는 명령의 포함 바이트인 프로파일링 실행에서 할당된 모든 바이트의 비율입니다.|  
|**제외 바이트**|-   함수의 경우 함수에 의해 할당된 총 바이트 수입니다. 이 수에는 이 함수가 호출한 함수에서 할당된 바이트는 포함되지 않습니다.<br />-   모듈의 경우 모듈 내 함수에 의해 할당된 제외 바이트의 합계입니다.<br />-   줄이나 명령의 경우 이 줄 또는 명령에 의해 할당된 총 개체 수입니다.|  
|**제외 바이트(%)**|모듈, 함수, 줄 또는 명령의 제외 바이트인 프로파일링 실행에서 할당된 모든 바이트의 비율입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [방법: 보고서 뷰 열 사용자 지정](../profiling/how-to-customize-report-view-columns.md)   
 [모듈 뷰 - 계측](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [모듈 뷰](../profiling/modules-view-sampling-data.md)   
 [모듈 뷰](../profiling/modules-view-instrumentation-data.md)


