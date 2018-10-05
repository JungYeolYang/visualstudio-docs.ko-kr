---
title: '방법: ClickOnce를 통해 게시할 파일 지정 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.BaseProvider.Dialog.File
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, file exclusion
- files, publishing via ClickOnce
ms.assetid: 579c134a-d50f-4e0c-8e05-2a4ff654896a
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: c56d378c8adee1801fb82fc4a2ed84e5b05c0aef
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47544189"
---
# <a name="how-to-specify-which-files-are-published-by-clickonce"></a>방법: ClickOnce를 통해 게시할 파일 지정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 지정 하는 파일 ClickOnce를 통해 게시할](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-which-files-are-published-by-clickonce)합니다.  
  
게시 하는 경우는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 프로젝트의 응용 프로그램, 모든 비 코드 파일은 응용 프로그램과 함께 배포 됩니다. 경우에 따라 원하는 또는 특정 파일을 게시 해야 할 수 있습니다 또는 조건에 따라 특정 파일을 설치 하는 것이 좋습니다. Visual Studio, 파일을 제외 하 고, 데이터 파일 또는 필수 구성 요소를으로 파일을 표시 하 고, 조건부 설치를 위한 파일 그룹을 만들려면 하는 기능을 제공 합니다.  
  
 파일에 대 한는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 응용 프로그램에서 관리 되는 **응용 프로그램 파일** 에서 액세스할 수 있는 대화 상자는 **게시** 페이지를 **프로젝트 디자이너**합니다.  
  
 처음에 단일 파일 그룹인 **(필수)** 합니다. 추가 파일 그룹을 만들고 파일을 지정할 수 있습니다. 변경할 수 없습니다는 **다운로드 그룹** 실행할 응용 프로그램에 필요한 파일에 대 한 합니다. 예를 들어, 응용 프로그램의.exe 파일 또는 파일 것으로 표시 데이터 파일에 속해 있어야 합니다 **(필수)** 그룹입니다.  
  
 기본 게시 상태 파일의 값으로 태그가 지정 됩니다 **(자동)** 합니다. 예를 들어, 응용 프로그램의.exe 상태가 게시 **포함 (자동)** 기본적으로 합니다.  
  
 사용 하 여 파일을 **빌드 작업** 속성으로 설정 **콘텐츠** 응용 프로그램 파일로 지정 되 고 기본적으로 포함 하는 것으로 표시 됩니다. 포함, 제외 하거나 수를 데이터 파일로 표시 합니다. 예외는 다음과 같습니다.  
  
-   기본적으로 데이터 파일 (.mdf 및.mdb) SQL Database 파일 및 XML 파일과 같은 데이터 파일로 표시 됩니다.  
  
-   어셈블리 (.dll 파일)에 대 한 참조는 참조를 추가할 때 다음과 같이 지정 됩니다: 경우 **로컬 복사** 됩니다 **False**, 필수 구성 요소 어셈블리는 기본적으로 표시 됩니다 (**필수 구성 요소 ( 자동)**) 응용 프로그램을 설치 하기 전에 GAC에 존재 해야 하는 합니다. 하는 경우 **로컬 복사** 됩니다 **True**, 어셈블리가 응용 프로그램 어셈블리로 기본적으로 표시 됩니다 (**포함 (자동)**) 설치 시 응용 프로그램 폴더로 복사 됩니다. COM 참조에 표시 됩니다는 **응용 프로그램 파일** 대화 상자 (써.ocx 파일) 경우에만 해당 **격리** 속성이로 설정 되어 **True**합니다. 기본적으로 포함 됩니다.  
  
### <a name="to-add-files-to-the-application-files-dialog-box"></a>Application Files Dialog Box에 파일을 추가 하려면  
  
1.  데이터 파일 선택 **솔루션 탐색기**합니다.  
  
2.  속성 창에서 변경 된 **빌드 작업** 속성을 합니다 **콘텐츠** 값입니다.  
  
### <a name="to-exclude-files-from-clickonce-publishing"></a>ClickOnce 게시에서 파일을 제외 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭 합니다 **게시** 탭 합니다.  
  
3.  클릭 합니다 **응용 프로그램 파일** 버튼을 클릭 합니다 **응용 프로그램 파일** 대화 상자.  
  
4.  에 **응용 프로그램 파일** 대화 상자에서 제외 하려는 파일을 선택 합니다.  
  
5.  에 **게시 상태** 필드를 선택한 **제외** 드롭 다운 목록에서.  
  
### <a name="to-mark-files-as-data-files"></a>데이터 파일로 파일을 표시 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭 합니다 **게시** 탭 합니다.  
  
3.  클릭 합니다 **응용 프로그램 파일** 버튼을 클릭 합니다 **응용 프로그램 파일** 대화 상자.  
  
4.  에 **응용 프로그램 파일** 대화 상자에서 데이터를 표시 하려는 파일을 선택 합니다.  
  
5.  에 **게시 상태** 필드를 선택한 **데이터 파일** 드롭 다운 목록에서.  
  
### <a name="to-mark-files-as-prerequisites"></a>필수 조건으로 구성 파일을 표시 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭 합니다 **게시** 탭 합니다.  
  
3.  클릭 합니다 **응용 프로그램 파일** 버튼을 클릭 합니다 **응용 프로그램 파일** 대화 상자.  
  
4.  에 **응용 프로그램 파일** 대화 상자에서 필수 구성 요소로 표시 하려는 응용 프로그램 어셈블리 (.dll 파일)를 선택 합니다. 응용 프로그램 목록에 표시 되려면에서 응용 프로그램 어셈블리에 대 한 참조를 있어야 하는 참고 합니다.  
  
5.  에 **게시 상태** 필드를 선택한 **필수 구성 요소** 드롭 다운 목록에서.  
  
### <a name="to-add-a-new-file-group"></a>새 파일 그룹을 추가 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭 합니다 **게시** 탭 합니다.  
  
3.  클릭 합니다 **응용 프로그램 파일** 버튼을 클릭 합니다 **응용 프로그램 파일** 대화 상자.  
  
4.  에 **응용 프로그램 파일** 대화 상자를 선택 합니다 **그룹** 새 그룹에 포함 하려는 파일에 대 한 필드.  
  
    > [!NOTE]
    >  파일이 있어야 합니다 **빌드 작업** 속성이로 설정 **콘텐츠** 파일 이름에 표시 되기까지 **응용 프로그램 파일** 대화 상자.  
  
5.  에 **다운로드 그룹** 필드를 선택한  **\<새로 만들기... >** 드롭 다운 목록에서.  
  
6.  에 **새 그룹** 대화 상자에서 그룹의 이름을 입력 하 고 클릭 **확인**합니다.  
  
### <a name="to-add-a-file-to-a-group"></a>파일 그룹에 추가 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭 합니다 **게시** 탭 합니다.  
  
3.  클릭 합니다 **응용 프로그램 파일** 버튼을 클릭 합니다 **응용 프로그램 파일** 대화 상자.  
  
4.  에 **응용 프로그램 파일** 대화 상자를 선택 합니다 **그룹** 새 그룹에 포함 하려는 파일에 대 한 필드.  
  
5.  에 **다운로드 그룹** 필드에서 드롭다운 목록에서 그룹을 선택 합니다.  
  
    > [!NOTE]
    >  변경할 수 없습니다는 **다운로드 그룹** 실행할 응용 프로그램에 필요한 파일에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)


