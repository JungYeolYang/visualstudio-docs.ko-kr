---
title: IDiaPropertyStorage::ReadMultiple | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 40cd84e00f2e6abea285368a6206c7400abf8877
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981550"
---
# <a name="idiapropertystoragereadmultiple"></a>IDiaPropertyStorage::ReadMultiple
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

지정한 현재 속성 집합에서 속성을 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT ReadMultiple(   
   ULONG          cpspec,  
   PROPSPEC const rgpspec,  
   PROPVARIANT    rgvar  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cpspec`  
 [in] 속성에 지정 된 개수는 `rgpspec` 배열입니다. 메서드 없음 속성을 반환 하지만 반환지 않습니다 0 이면 `S_OK` 를 성공 코드입니다.  
  
 `rgpspec`  
 [in] 배열 속성을 읽을 수입니다. 속성 ID로 또는 선택적 문자열 이름으로 속성을 지정할 수 있습니다. 배열에서 특정 순서로 속성을 지정 하는 데 필요한 것입니다. 배열에는 단순 속성에 대 한 중복 된 속성 값에 중복 된 속성을 포함할 수 있습니다. 비 단순 속성 두 번 열어서 하려고 할 때 액세스 거부를 반환 해야 합니다. 배열 속성 Id와 문자열 Id의 혼합을 포함할 수 있습니다. 이 배열에 적어도 있어야 `cpspec` 속성 값의 수입니다.  
  
 `rgvar`  
 [out에서] 배열을 `PROPVARIANT` 구조 (Microsoft.VisualStudio.OLE.Interop 네임 스페이스) 각 속성에 대 한 값을 채울 수 있습니다. 배열 이상 이어야 합니다 `cpspec` 요소의 크기입니다. 호출자가 배열의 값을 초기화할 필요가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 속성 중 하나 이상이 없는 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 경우 속성을 찾을 수 없습니다, 해당 항목에는 `rgvar` 배열에는 `VARIANT` 유형의 `VT_EMPTY`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
