---
title: 기존 프로젝트 추가 명령 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- file.addexistingproject
helpviewer_keywords:
- Add Existing Project command
- File.AddExistingProject
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 048ba8e43b66ac5ad4bbc1d0c09adb75a2d61e1d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542434"
---
# <a name="add-existing-project-command"></a>기존 프로젝트 추가 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [기존 프로젝트 추가 명령](https://docs.microsoft.com/visualstudio/ide/reference/add-existing-project-command)입니다.  
  
  
현재 솔루션에 기존 프로젝트를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
File.AddExistingProject filename  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 선택 사항입니다. 솔루션에 추가할 프로젝트의 전체 경로 및 프로젝트 이름(확장명 포함)입니다.  
  
 `filename` 인수에 공백이 있는 경우 따옴표로 묶어야 합니다.  
  
 파일 이름을 지정하지 않은 경우 명령을 실행하면 사용자가 프로젝트를 선택할 수 있는 파일 대화 상자가 열립니다.  
  
## <a name="remarks"></a>설명  
 입력 시 자동 완성에서 올바른 경로와 파일 이름을 찾으려고 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] 프로젝트인 TestProject1을 현재 솔루션에 추가합니다.  
  
```  
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)


