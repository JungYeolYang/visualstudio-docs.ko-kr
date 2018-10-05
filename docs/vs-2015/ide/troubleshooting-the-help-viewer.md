---
title: 도움말 뷰어 문제 해결 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting [Help Viewer 2.0]
- Help Viewer 2.0, troubleshooting
ms.assetid: 461a4553-064a-4142-a2d2-058658b9ba12
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 68946af27925347cee497c237de396d31f214e13
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556369"
---
# <a name="troubleshooting-the-help-viewer"></a>도움말 뷰어 문제 해결
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [도움말 뷰어 문제 해결](https://docs.microsoft.com/visualstudio/ide/troubleshooting-the-help-viewer)합니다.  
  
이 항목에서는 도움말 뷰어에 발생할 수 있는 문제를 설명합니다.  
  
## <a name="audio-doesnt-work"></a>오디오가 작동하지 않습니다.  
 도움말 뷰어에 오디오 플레이어가 포함되어 있지 않습니다. 오디오가 포함된 콘텐츠르 다운로드하고 **재생**을 선택한 경우 아무 일도 발생하지 않으면 오디오 플레이어를 설치하십시오.  
  
## <a name="search-doesnt-work-in-windows-server-2008-windows-server-2008-with-sp1-or-windows-server-2008-r2"></a>검색은 Windows Server 2008, Windows Server 2008 SP1, 또는 Windows Server 2008 R2에서는 작동하지 않습니다.  
 도움말 뷰어의 검색 및 필터 기능을 사용하려면 Windows 검색 서비스를 설치하고 사용 설정해야 합니다. 기본적으로 이 서비스는 Windows Server 2008, Windows Server 2008 서비스 팩 1(SP1) 및 Windows Server 2008 R2에서 사용 해제되어 있습니다.  
  
#### <a name="to-activate-windows-search-service"></a>Windows 검색 서비스를 활성화하려면  
  
1.  서버 관리자를 클릭합니다.  
  
2.  왼쪽된 탐색 창에서 선택 **역할**을 선택합니다.  
  
3.  역할 요약 창에서 선택 **역할 추가**를 선택합니다.  
  
4.  파일 서비스 역할을 선택하고 **다음** 단추를 선택합니다.  
  
5.  Windows 검색 역할 서비스를 선택합니다.  
  
## <a name="additional-resources"></a>추가 리소스  
 다음 리소스를 사용하여 도움말 뷰어에 대한 추가 정보를 얻고 피드백을 제공할 수 있습니다.  
  
-   피드백을 제공 하려면 Microsoft 웹 사이트에서 [Microsoft Connect](http://go.microsoft.com/fwlink/?linkid=243983)를 참조하거나 [hlpfdbk@microsoft.com](mailto:hlpfdbk@microsoft.com)으로 이메일을 보내십시오.  
  
-   자세한 내용은 참조는 [Developer Documentation and Help System](http://go.microsoft.com/fwlink/?LinkId=232741) 포럼 및 [The Help Guy](http://go.microsoft.com/fwlink/?LinkId=232743) 블로그.  
  
## <a name="see-also"></a>참고 항목  
 [도움말 뷰어 2.1 관리자 가이드](http://go.microsoft.com/fwlink/?LinkId=243985)


