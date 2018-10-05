---
title: IDebugEnumField::GetStringFromValue | Microsoft Docs
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
- IDebugEnumField::GetStringFromValue
helpviewer_keywords:
- IDebugEnumField::GetStringFromValue method
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 38dbd88ea8b84c64b277daf5b77970fa127d82fd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549883"
---
# <a name="idebugenumfieldgetstringfromvalue"></a>IDebugEnumField::GetStringFromValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugEnumField::GetStringFromValue](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugenumfield-getstringfromvalue)합니다.  
  
이 메서드는 해당 값을 지정 된 열거형 상수의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetStringFromValue(  
   ULONGLONG value,  
   BSTR*     pbstrValue  
);  
```  
  
```csharp  
int GetStringFromValue(  
   ulong      value,  
   out string pbstrValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value`  
 [in] 열거형의 이름을 상수 가져올 값입니다.  
  
 `pbstrValue`  
 [out] 열거형 상수의 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 값에 연결 된 이름은 또는 오류 코드를 반환 하는 경우.  
  
## <a name="remarks"></a>설명  
 동일한 값과 연결 된 이름을 여러 개 있으면 열거형에 정의 된 이름이 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
