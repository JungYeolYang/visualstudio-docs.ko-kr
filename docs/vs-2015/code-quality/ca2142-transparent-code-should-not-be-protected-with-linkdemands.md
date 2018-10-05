---
title: 'CA2142: 투명 코드는 보호 해서는 안 LinkDemands를 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 744ca0b6b988591b646c66d349cc39649d323116
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591143"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: 투명한 코드는 LinkDemands를 사용하여 보호해서는 안 됩니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2142: 투명 코드는 LinkDemands를 사용 하 여 보호 해서는 안](https://docs.microsoft.com/visualstudio/code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands)합니다.

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 투명 한 메서드를 사용 하려면를 <xref:System.Security.Permissions.SecurityAction> 또는 다른 보안 요청 합니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 액세스하는 데 LinkDemands가 필요한 투명한 메서드에 적용됩니다. 보안 투명 코드는 작업 보안을 확인할 책임이 없으므로 권한을 요구해서는 안 됩니다. 투명 한 메서드는 보안 중립 할 때문에 이러한 내려서는 안 보안 의사 결정 합니다. 또한가 이전에 이러한 결정을 위해 투명 코드에서 하지 않습니다 보안 결정을 안전 하 게 중요 한 코드를 신뢰 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 투명 메서드에 링크 요청을 제거 하거나 메서드를 사용 하 여 표시 <xref:System.Security.SecuritySafeCriticalAttribute> 보안 요구 사항 등을 보안 수행 하는 경우 특성을 검사 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서에서 규칙이 실행 메서드는 메서드가 이루어집니다 LinkDemand 표시 되어 있기 때문에 <xref:System.Security.PermissionSet> 를 포함 하는 <xref:System.Security.Permissions.SecurityAction>합니다.

 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2142.transparentmethodsshouldnotbeprotectedwithlinkdemands/cs/ca2142 -transparentmethodsshouldnotbeprotectedwithlinkdemands.cs#1)]

 이 규칙에서는 경고를 표시해야 합니다.


