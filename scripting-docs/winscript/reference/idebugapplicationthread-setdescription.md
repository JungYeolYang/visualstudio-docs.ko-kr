---
title: IDebugApplicationThread::SetDescription | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationThread.SetDescription
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationThread::SetDescription
ms.assetid: 084e5b74-af95-41b4-ae55-01f6f4d22168
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a81c2062e002d85002b991969c4b8ccd64a82aab
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58145215"
---
# <a name="idebugapplicationthreadsetdescription"></a>IDebugApplicationThread::SetDescription
이 스레드에 대 한 설명을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SetDescription(  
   LPCOLESTR  pstrDescription  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstrDescription`  
 [in] 이 스레드에 대 한 설명입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는이 스레드에 대 한 설명을 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationThread 인터페이스](../../winscript/reference/idebugapplicationthread-interface.md)