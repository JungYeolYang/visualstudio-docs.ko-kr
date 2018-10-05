---
title: UNMANAGED_ADDRESS_THIS_RELATIVE | Microsoft Docs
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
- UNMANAGED_ADDRESS_THIS_RELATIVE
helpviewer_keywords:
- UNMANAGED_ADDRESS_THIS_RELATIVE structure
ms.assetid: e6a91ace-2d47-4ff9-aefb-8d8b68eab0b2
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3792d56b1987e54b15e961a191ecee5d7a60e4fd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553901"
---
# <a name="unmanagedaddressthisrelative"></a>UNMANAGED_ADDRESS_THIS_RELATIVE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [UNMANAGED_ADDRESS_THIS_RELATIVE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/unmanaged-address-this-relative)합니다.  
  
이 구조는 기준으로 하는 주소를 나타내는 `this` 포인터 (`Me` Visual basic에서).  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagUNMANAGED_THIS_RELATIVE {  
   DWORD dwOffset;  
   DWORD dwBitOffset;  
   DWORD dwBitLength;  
} UNMANAGED_ADDRESS_THIS_RELATIVE;  
```  
  
```csharp  
public struct UNMANAGED_THIS_RELATIVE {  
   public uint dwOffset;  
   public uint dwBitOffset;  
   public uint dwBitLength;  
}  
```  
  
## <a name="terms"></a>용어  
 dwOffset  
 기본 위치 (예: 클래스 vtable의 시작 부분)에서 오프셋을 바이트입니다.  
  
 dwBitOffset  
 기본 위치에서 비트에서 오프셋 (항상 0 비트 필드 참조 하지 않는 한).  
  
 dwBitLength  
 주소를 나타내는 비트 수 (항상 0 비트 필드 참조 하지 않는 한).  
  
## <a name="remarks"></a>설명  
 이 구조체의 공용 구조체의 일부인를 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 경우 구조체를 `dwKind` 필드를 `DEBUG_ADDRESS_UNION` 구조로 설정 되어 `ADDRESS_KIND_UNMANAGED_THIS_RELATIVE` (의 값을 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형)입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
