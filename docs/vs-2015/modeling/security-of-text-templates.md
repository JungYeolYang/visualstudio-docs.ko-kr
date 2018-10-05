---
title: 텍스트 템플릿 보안 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, security
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 4ce9ccca0a144de7101e886712105315ec64fa75
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543267"
---
# <a name="security-of-text-templates"></a>텍스트 템플릿 보안
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Security of Text Templates](https://docs.microsoft.com/visualstudio/modeling/security-of-text-templates)합니다.  
  
텍스트 템플릿 모두 다음 보안 고려 사항:  
  
-   텍스트 템플릿은 임의의 코드 삽입에 취약 합니다.  
  
-   호스트 된 지시문 프로세서를 찾는 데 사용 하는 메커니즘에 보안이 설정 되지 않으면 악성 지시문 프로세서를 실행할 수 있습니다.  
  
## <a name="arbitrary-code"></a>임의의 코드  
 서식 파일을 작성 하는 경우 내 코드를 넣을 수 있습니다는 \<# # > 태그입니다. 이렇게 하면 임의의 코드를 텍스트 템플릿 내에서 실행할 수 있습니다.  
  
 신뢰할 수 있는 출처에서 템플릿을 가져올 해야 합니다. 신뢰할 수 있는 출처에서 제공 되지 않은 템플릿을 실행 하지 않도록 응용 프로그램의 최종 사용자에 게 경고 해야 합니다.  
  
## <a name="malicious-directive-processor"></a>악의적인 지시문 프로세서  
 텍스트 템플릿 엔진 템플릿 텍스트를 출력 파일로 변환할 변환 호스트와 하나 이상의 지시문 프로세서를 사용 하 여 상호 작용 합니다. 자세한 내용은 [은 텍스트 템플릿 변형 프로세스](../modeling/the-text-template-transformation-process.md)합니다.  
  
 호스트 된 지시문 프로세서를 찾는 데 사용 하는 메커니즘에 보안이 설정 되지 않으면 악성 지시문 프로세서를 실행 하는 위험이 실행 됩니다. 악의적인 지시문 프로세서에서 실행 되는 코드를 제공할 수 `FullTrust` 템플릿이 실행 될 때의 모드입니다. 사용자 지정 텍스트 템플릿 변형 호스트를 만드는 경우 지시문 프로세서를 찾으려고 엔진에 대 한 레지스트리와 같은 보안 메커니즘을 사용 해야 합니다.


