---
title: IDiaStackWalkHelper::searchForReturnAddress | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::searchForReturnAddress method
ms.assetid: 904223b1-6e26-4980-b310-d0b222cdbbbd
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 935621b6a9eff8fdef53b76be95065fa6ed050fc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549454"
---
# <a name="idiastackwalkhelpersearchforreturnaddress"></a>IDiaStackWalkHelper::searchForReturnAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDiaStackWalkHelper::searchForReturnAddress](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress)합니다.  
  
가장 가까운 함수 반환 주소를 지정한 스택 프레임을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT searchForReturnAddress(   
   IDiaFrameData*  frame,  
   ULONGLONG*      returnAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `frame`  
 [in] [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 현재 스택 프레임을 나타내는 개체입니다.  
  
 `returnAddress`  
 [out] 가장 가까운 함수 반환 주소를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)


