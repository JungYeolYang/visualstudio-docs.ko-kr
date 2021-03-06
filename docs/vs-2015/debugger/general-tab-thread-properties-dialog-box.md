---
title: 스레드 속성 대화 상자, 일반 탭 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- threading [Visual Studio], thread properties
- thread properties
ms.assetid: 46b6c668-6786-456e-97dc-337bcac0d812
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b1a8e6fd583f6035fc84f0c86adcee059562235d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58982248"
---
# <a name="general-tab-thread-properties-dialog-box"></a>스레드 속성 대화 상자, 일반 탭
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

특정 스레드에 대 한 자세한 내용은이 대화 상자를 사용 합니다. 이 대화 상자를 표시 하려면 포커스를 이동 하는 [스레드 뷰](../debugger/threads-view.md) 창을 열거나 [메시지 뷰](../debugger/messages-view.md) 메시지를 확장 합니다. 선택한 스레드 노드 트리에서 선택 **속성** 에서 합니다 **보기** 메뉴.  
  
 **Thread Properties** 대화 상자에는 하나의 창에는 **일반** 탭. 다음 설정은 사용할 수 있습니다.  
  
|입력|설명|  
|-----------|-----------------|  
|**모듈 이름**|모듈의 이름입니다.|  
|**스레드 ID**|이 스레드의 고유 ID입니다. 스레드 ID 번호는 다시 사용; 참고 스레드의 수명 동안만 스레드를 식별합니다.|  
|**프로세스 ID**|이 프로세스의 고유 ID입니다. 프로세스 ID 번호는 다시 사용 되므로 해당 프로세스의 기간에만 프로세스를 식별 합니다. 프로세스 개체 유형은 프로그램이 실행 될 때 생성 됩니다. 프로세스의 모든 스레드는 동일한 주소 공간을 공유 하 고 동일한 데이터에 액세스할 수 있습니다. 프로세스 ID의 속성을 보려면이 값을 선택|  
|**스레드 상태**|스레드의 현재 상태입니다. 실행 스레드는 프로세서;를 사용 하 여 대기 스레드를 하나를 사용 합니다. 스레드 준비는 무료 아니기 때문에 프로세서를 사용 하는 대기 중입니다. 디스크에서 페이지 수에 해당 실행 스택을 기다리는 등을 실행 하려면 리소스에 대 한 전환 스레드를 기다리고 있습니다. 대기 중인 스레드가 주변 작업이 완료 또는 무료 되도록 리소스를 기다리고 있으므로 프로세서를 필요 하지 않습니다.|  
|**대기 원인**|스레드가 대기 상태에 있을 경우에 적용 됩니다. 이벤트 쌍은 보호 된 하위 시스템을 사용 하 여 통신 하는 데 사용 됩니다.|  
|**CPU 시간**|이 프로세스와 해당 스레드에서 소요 된 총 CPU 시간입니다. 사용자 시간 + 특권을과 같습니다.|  
|**사용자 시간**|이 스레드가 사용자 모드에서 코드를 실행 중인 데 걸린 총 경과 시간입니다. 응용 프로그램 창 관리자 그래픽 엔진 등 하위 시스템 사용자 모드에서 실행 됩니다.|  
|**권한 있는 시간**|이 스레드가 특권 모드에서 실행 중인 코드 데 걸린 총 경과 시간입니다. Windows 시스템 서비스를 호출 하면 서비스는 종종 시스템 전용 데이터에 액세스할 수 있는 특권 모드에서 실행 됩니다. 이러한 데이터는 사용자 모드에서 실행 되는 스레드의 액세스 로부터 보호 됩니다. 시스템에 대 한 호출 명시적 일 수 또는 페이지 폴트 또는 인터럽트가 발생 하는 경우와 같은 암시적 일 수 있습니다.|  
|**경과 시간**|총 경과 시간 (초)이이 스레드가 실행 되었습니다.|  
|**현재 우선 순위**|이 스레드의 현재 동적 우선 순위입니다. 스레드는 프로세스 내에서 발생 하 고 프로세스의 기본 우선 순위를 기준으로 자신의 기본 우선 순위를 낮출 수 있습니다.|  
|**기본 우선 순위**|이 스레드에 대 한 현재 기본 우선 순위입니다.|  
|**시작 주소**|이 스레드에 대 한 시작 가상 주소입니다.|  
|**사용자 PC**|사용자 프로그램 스레드에 대 한 카운터입니다.|  
|**컨텍스트 전환**|다른 스레드 간에서 전환의 수입니다. 단일 프로세스 내에서 또는 프로세스 간 스레드 전환 발생할 수 있습니다. 다른 정보를 요청 하는 한 스레드에 의해 또는 더 높은 우선 순위 스레드는 실행할 준비가 되 면 선점 되는 스레드에서 스레드 스위치를 발생할 수 있습니다.|
