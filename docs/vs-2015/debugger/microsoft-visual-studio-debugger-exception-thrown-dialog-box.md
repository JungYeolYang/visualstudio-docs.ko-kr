---
title: Microsoft Visual Studio Debugger (예외 Throw) 대화 상자 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.exceptions.thrown
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Microsoft Visual Studio Debugger (Exception Thrown) dialog box
- exception handling, during debugging
- debugger, exceptions
- throwing exceptions, during debugging
ms.assetid: 1fe98d10-c8f9-4b39-a920-99169bfd542e
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d0968c5ee67df10bad99ae31a3f0d812251ad818
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58986149"
---
# <a name="microsoft-visual-studio-debugger-exception-thrown-dialog-box"></a>Microsoft Visual Studio Debugger(예외 throw) 대화 상자
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

프로그램에 예외가 발생하면 나타나는 대화 상자입니다. 이 대화 상자는 throw된 예외의 종류를 보고합니다. 코드를 통해 이 예외를 처리해야 합니다. 선택할 수 있는 예외 처리 옵션은 다음과 같습니다.  
  
 **Break**  
 프로그램의 실행을 중단하고 디버거를 시작합니다. 실행을 중단하기 전에는 예외 처리기가 호출되지 않습니다. 중단 위치에서 실행을 계속하면 예외 처리기가 호출됩니다.  
  
 **Continue**  
 실행을 계속하여 예외 처리기에 예외를 처리할 기회를 줍니다. 특정 유형의 예외에는 이 옵션을 사용할 수 없습니다. **계속**을 선택하면 애플리케이션 실행이 계속됩니다. 네이티브 응용 프로그램에서는 예외가 다시 throw됩니다. 관리되는 응용 프로그램에서는 프로그램이 종료되거나 호스팅 응용 프로그램에서 예외를 처리합니다.  
  
> [!NOTE]
>  관리 코드에서는 처리되지 않은 예외가 발생한 후 실행을 계속할 수 없습니다. 관리 코드에서 처리되지 않은 예외가 발생한 후 **계속**을 선택하면 디버깅이 중지됩니다.  
  
 **무시**  
 예외 처리기를 호출하지 않고 실행을 계속합니다. 예외 처리기가 호출되지 않으므로 추가적인 예외 및 오류를 비롯한 후속 결과가 발생할 수 있습니다. 특정 유형의 예외에는 이 옵션을 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)   
 [예외에 대한 모범 사례](http://msdn.microsoft.com/library/f06da765-235b-427a-bfb6-47cd219af539)   
 [예외 처리](http://msdn.microsoft.com/library/ccb11fe8-6938-41ac-b477-a183e85865b9)
