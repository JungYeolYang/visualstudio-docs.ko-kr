---
title: 이동 명령 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 50f91c4bdb17612d56534290a7b83b7df1d771c9
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54790022"
---
# <a name="go-to-command"></a>이동 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
지정된 줄로 커서를 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Edit.GoTo [linenumber]  
```  
  
## <a name="arguments"></a>인수  
 `linenumber`  
 선택 사항입니다. 이동할 줄 번호를 나타내는 정수입니다.  
  
## <a name="remarks"></a>주의  
 줄 번호는 1부터 시작합니다. `linenumber` 값이 1보다 작은 경우 첫 번째 줄이 표시됩니다. `linenumber` 값이 마지막 줄 번호보다 큰 경우 마지막 줄이 표시됩니다.  
  
 `linenumber` 값이 지정되지 않으면 **줄 이동** 대화 상자가 표시됩니다.  
  
 이 명령에 대한 별칭은 GoToLn입니다.  
  
## <a name="example"></a>예  
  
```  
>Edit.GoTo 125  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
