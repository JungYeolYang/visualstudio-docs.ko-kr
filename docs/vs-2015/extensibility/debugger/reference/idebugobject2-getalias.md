---
title: IDebugObject2::GetAlias | Microsoft Docs
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
- IDebugObject2::GetAlias
helpviewer_keywords:
- IDebugObject2::GetAlias method
ms.assetid: aa6824d5-c932-42ba-8713-950e7d1fb42f
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 77cd9b8ccdb89d2a0e52cf1193dd3137780964d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543496"
---
# <a name="idebugobject2getalias"></a>IDebugObject2::GetAlias
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugObject2::GetAlias](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject2-getalias)합니다.  
  
있는 경우이 개체와 연결 된 별칭을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAlias(  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int GetAlias(  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppAlias`  
 [out] 반환 된 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) 이 개체에 대 한 별칭을 나타내는 개체, 그렇지 않으면 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 호출을 사용 하 여 개체에 대 한 별칭이 만들어집니다 합니다 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
