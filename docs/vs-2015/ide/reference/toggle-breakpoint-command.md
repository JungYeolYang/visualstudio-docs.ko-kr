---
title: 중단점 설정/해제 명령 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.togglebreakpoint
helpviewer_keywords:
- ToggleBreakpoint command
- Debug.ToggleBreakPoint command
- Toggle Breakpoint command
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c7dd3bd7a4d42b8135aed034464223af53091f87
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541739"
---
# <a name="toggle-breakpoint-command"></a>중단점 설정/해제 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [중단점 설정/해제 명령](https://docs.microsoft.com/visualstudio/ide/reference/toggle-breakpoint-command)입니다.  
  
  
파일의 현재 위치에서 현재 상태에 따라 중단점을 켜거나 끕니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.ToggleBreakpoint [text]  
```  
  
## <a name="arguments"></a>인수  
 `text`  
 선택 사항입니다. 텍스트를 지정하는 경우 해당 줄은 명명된 중단점으로 표시됩니다. 그렇지 않은 경우 해당 줄은 F9 키를 누를 때처럼 명명되지 않은 중단점으로 표시됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 현재 중단점을 설정/해제합니다.  
  
```  
>Debug.ToggleBreakpoint  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)


