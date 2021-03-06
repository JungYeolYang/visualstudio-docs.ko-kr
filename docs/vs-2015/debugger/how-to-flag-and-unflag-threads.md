---
title: '방법: 플래그 지정 및 스레드의 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
caps.latest.revision: 36
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: be6ebe9e2031b24442f368b626d53b15a043023c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58970777"
---
# <a name="how-to-flag-and-unflag-threads"></a>방법: 스레드에 플래그 지정 및 해제
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

아이콘 표시 하 여 특별 한 주의가 하려는 스레드에 플래그를 수는 **스레드**를 **병렬 스택**를 **병렬 조사식**, 및 **GPU 스레드** windows. 이 아이콘은 플래그 설정된 스레드를 다른 스레드와 구분하는 데 도움이 됩니다.  
  
 플래그가 지정 된 스레드 권한도에서 별도로 처리 합니다 **스레드** 목록에서 **디버그 위치** 도구 모음입니다. 이 목록에 모든 스레드나 플래그 설정된 스레드만 표시할 수 있습니다. 스레드에 플래그 지정 된 **스레드** 목록 플래그가 지정 된 스레드만 표시 하도록 자동으로 전환 되지만 전환할 수도 있습니다 적절 하 게 모든 스레드 표시를 다시 합니다.  
  
### <a name="to-flag-or-unflag-a-thread-by-using-the-threads-window"></a>스레드 창을 사용하여 스레드에 플래그를 설정하거나 해제하려면  
  
-   에 **스레드** 창에서 원하는 스레드를 찾아 선택 하 고 플래그를 지우려면 플래그 아이콘을 클릭 합니다.  
  
### <a name="to-unflag-all-threads"></a>모든 스레드의 플래그를 해제하려면  
  
-   **스레드** 창에서 스레드를 마우스 오른쪽 단추로 클릭하고 **모든 스레드 플래그 해제**를 클릭합니다.  
  
### <a name="to-display-only-flagged-threads"></a>플래그가 지정된 스레드만 표시하려면  
  
-   디버깅 창에서 플래그 단추를 선택합니다.  
  
### <a name="to-flag-just-my-code"></a>내 코드만 플래그를 설정하려면  
  
1.  **스레드** 창의 맨 위에 있는 도구 모음에서 플래그 아이콘을 클릭합니다.  
  
2.  드롭다운 목록에서 **내 코드만 플래그 지정**을 클릭합니다.  
  
### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>선택한 모듈과 연결된 스레드에 플래그를 설정하려면  
  
1.  **스레드** 창의 도구 모음에서 플래그 아이콘을 클릭합니다.  
  
2.  드롭다운 목록에서 **사용자 지정 모듈 선택 영역 플래그 지정**을 클릭합니다.  
  
3.  **모듈 선택** 대화 상자에서 원하는 모듈을 선택합니다.  
  
4.  (선택 사항) **검색** 상자에서 특정 모듈을 검색할 문자열을 입력합니다.  
  
5.  **확인**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 애플리케이션 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [연습: 다중 스레드 애플리케이션 디버그](../debugger/walkthrough-debugging-a-multithreaded-application.md)
