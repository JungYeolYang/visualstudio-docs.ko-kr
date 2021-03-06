---
title: IDebugFormatter::GetStringForVariant | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugFormatter.GetStringForVariant
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugFormatter::GetStringForVariant
ms.assetid: 95189d03-1126-433e-8513-659107b3df16
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 901bf9648d4d16faf7386b528cc3fd877070a5b6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58153671"
---
# <a name="idebugformattergetstringforvariant"></a>IDebugFormatter::GetStringForVariant
지정된 된 변형 값을 나타내는 문자열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetStringForVariant(  
   VARIANT*  pvar,  
   ULONG     nRadix,  
   BSTR*     pbstrValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvar`  
 [in] 변형을 문자열로 나타냅니다.  
  
 `nRadix`  
 [in] 숫자 값에 사용할 기 수입니다.  
  
 `pbstrValue`  
 [out] 문자열을 나타내는 `pvar`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정된 된 변형 값을 나타내는 문자열을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFormatter 인터페이스](../../winscript/reference/idebugformatter-interface.md)