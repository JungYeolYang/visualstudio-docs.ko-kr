---
title: IDebugModule2::GetInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugModule2::GetInfo method
ms.assetid: de337e66-294f-4ac9-b21e-71fac7418e36
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0a5ad3d7651e89c2ef864a184155e8b0a430d79
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694805"
---
# <a name="idebugmodule2getinfo"></a>IDebugModule2::GetInfo
이 모듈에 대 한 정보를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetInfo( 
   MODULE_INFO_FIELDS dwFields,
   MODULE_INFO*       pInfo
);
```

```cpp
int GetInfo( 
   enum_MODULE_INFO_FIELDS dwFields,
   MODULE_INFO[]           pInfo
);
```

#### <a name="parameters"></a>매개 변수
 `dwFields`

 [in] 플래그의 조합을 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) 의 필드를 지정 하는 열거형 `pInfo` 작성 됩니다.

 `pInfo`

 [out에서] A [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) 는 모듈에 대 한 설명을 포함 하는 구조입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 합니다 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) 구조에 표시 되는 모듈의 이름을 포함 합니다 **모듈** 창입니다.

## <a name="see-also"></a>참고 항목
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)