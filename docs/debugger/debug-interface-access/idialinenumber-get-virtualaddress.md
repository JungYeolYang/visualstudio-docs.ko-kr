---
title: 'Idialinenumber:: Get_virtualaddress | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_virtualAddress method
ms.assetid: 9048ef91-a59d-4ad8-90cb-4c13d0989241
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 98826ec691efdca70a9d0ca98b089904b2ed0c48
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56629783"
---
# <a name="idialinenumbergetvirtualaddress"></a>IDiaLineNumber::get_virtualAddress
블록의 가상 주소 (VA)를 검색합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_virtualAddress ( 
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 블록의 가상 주소를 반환합니다.

## <a name="return-value"></a>반환 값
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="see-also"></a>참고 항목
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)