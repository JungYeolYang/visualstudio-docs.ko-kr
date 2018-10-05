---
title: Windows 문서 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio SDK, document windows
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c620de56e3658c3aef33da136930221578b9be4a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550063"
---
# <a name="document-windows"></a>문서 창
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [문서 Windows](https://docs.microsoft.com/visualstudio/extensibility/internals/document-windows)합니다.  
  
Visual Studio에서를 *문서 창* (MDI) 다중 문서 인터페이스 창과 사용 하 여 연결 된 자식 프레임된 창입니다. 문서 일반적으로 사용 하는 표시 하 고 소스 코드 또는 텍스트를 수정 하지만 다른 기능 종류를 호스팅할 수도 있습니다. 문서 창:  
  
-   동시에 여러 파일을 볼 수 있습니다 있도록 MDI 부모에서 별도 가로 또는 세로 탭 그룹에 구성할 수 있습니다.  
  
-   MDI 부모에서 순서에 관계 없이 도킹 될 수 있습니다.  
  
-   자유롭게 이동할 수 있습니다.  
  
-   다른 MDI 창에 탭 순서에 연결 됩니다.  
  
 그룹화에 대 한 명령, 도킹 및 부동 있습니다 문서 창의 탭에 대 한 바로 가기 메뉴.  
  
 Visual Studio에서 창 동작에 대 한 자세한 내용은 참조 하세요. [창 레이아웃 사용자 지정](../../ide/customizing-window-layouts-in-visual-studio.md)합니다.  
  
## <a name="document-window-implementation"></a>문서 창 구현  
 문서 창은 편집기를 구현 하 여 생성 됩니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 인터페이스 인스턴스화를 편집기의 일부로 문서 창을 만듭니다. 자세한 내용은 [편집기에서 레거시 인터페이스](../../extensibility/legacy-interfaces-in-the-editor.md)합니다.  
  
> [!NOTE]
>  뒤로 제공 하 고 창의 탐색 요소를 전달 하려면 구현 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBackForwardNavigation> 인터페이스입니다. 텍스트 편집기 텍스트 마커를 사용 하 여 문서의 탐색 지점을 식별할 수 있습니다.  
  
## <a name="the-running-document-table"></a>실행 중인 문서 테이블  
 IDE 모든 문서 창의 상태를 추적 하는 실행 중인 document 테이블 (RDT)를 사용 합니다. RDT는 메커니즘은 문서를 통해 windows 이벤트를 같은 솔루션을 닫을 때 또는 파일을 편집한 후 알림이 표시 됩니다. 자세한 내용은 [문서 테이블 실행](../../extensibility/internals/running-document-table.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지연된 문서 로드](../../extensibility/internals/delayed-document-loading.md)
