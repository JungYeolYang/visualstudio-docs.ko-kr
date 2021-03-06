---
title: '방법: 레거시 언어 서비스의 숨겨진된 텍스트 지원 제공 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- hidden text, supporting
- editors [Visual Studio SDK], hidden text
- language services, implementing hidden text regions
ms.assetid: 1c1dce9f-bbe2-4fc3-a736-5f78a237f4cc
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0a74998e6cb9b236818f20ec3c597f9a3b9bd7dd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58983288"
---
# <a name="how-to-provide-hidden-text-support-in-a-legacy-language-service"></a>방법: 레거시 언어 서비스에서 숨겨진 텍스트 지원 제공
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

개요 영역 외에도 숨겨진된 텍스트 영역을 만들 수 있습니다. 클라이언트에서 제어 되 나 편집기 제어 숨겨진된 텍스트 영역 수 및 텍스트 영역을 완전히 숨기는 데 사용 됩니다. 편집기는 가로선으로 숨겨진된 영역을 표시합니다. 이 예제는 HTML 편집기에서 스크립트 전용 뷰.  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-implement-a-hidden-text-region"></a>숨겨진된 텍스트 영역을 구현 하려면  
  
1.  호출 `QueryService` 에 대 한 <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>합니다.  
  
     에 대 한 포인터를 반환 하는이 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>합니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>지정된 텍스트 버퍼에 대 한 포인터에 전달 합니다. 버퍼에 대 한 숨겨진된 텍스트 세션이 이미 있는지 여부를 결정 합니다.  
  
3.  이미 있는 경우 및 기존에 대 한 포인터를 만들 필요가 없습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 개체가 반환 됩니다. 이 포인터를 사용 하 여 숨겨진된 텍스트 영역을 만들고 열거 합니다. 그렇지 않으면 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> 버퍼에 대 한 숨겨진된 텍스트 세션을 만듭니다.  
  
     에 대 한 포인터를 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 개체가 반환 됩니다.  
  
    > [!NOTE]
    >  호출 하는 경우 `CreateHiddenTextSession`, 숨겨진된 텍스트 클라이언트를 지정할 수 있습니다 (즉, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient>). 숨겨진된 텍스트 클라이언트 숨겨진된 텍스트 또는 개요 확장 또는 사용자가 축소 하는 경우이 알려 줍니다.  
  
4.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> 을 추가 하거나 더 많은 새로운 개요 영역 번에서 다음 정보를 지정 하는 `reHidReg` (<xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>) 매개 변수:  
  
    1.  값을 지정 `hrtConcealed` 에 `iType` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 개요 영역 보다는 숨겨진된 영역을 만드는 것을 나타내기 위해 구조입니다.  
  
        > [!NOTE]
        >  숨겨진된 영역 숨겨지면 편집기가 있는지 표시 하려면 숨겨진된 영역 주위에 선을 자동으로 표시 합니다.  
  
    2.  클라이언트에서 제어 되 나 편집기 제어에서 지역 인지 지정 합니다 `dwBehavior` 의 멤버는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> 구조. 스마트 개요 구현에는 다양 한 편집기 및 클라이언트 제어 개요 및 숨겨진된 텍스트 영역을 포함할 수 있습니다.
