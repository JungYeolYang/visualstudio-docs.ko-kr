---
title: IDebugPortRequest2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortRequest2
helpviewer_keywords:
- IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7873d3d73556bae671cc1150525eb3d08a136e27
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47557243"
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugPortRequest2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportrequest2)합니다.  
  
이 인터페이스는 포트를 설명합니다. 이 설명은 포트 공급자에 포트를 추가할 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio는 일반적으로 디버그 포트를 포트 공급자에서 시작 하 고이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 이 인터페이스에 전달 됩니다 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 디버그 포트를 만듭니다. 에 대 한 호출 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md) 나타내는 요청 포트를 처음부터 만드는 데이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPortRequest2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|만들려는 포트의 이름을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 디버그 엔진을 일반적으로 포트 공급자 상호 작용 하지 않습니다 있으며,이 인터페이스 사용 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)
