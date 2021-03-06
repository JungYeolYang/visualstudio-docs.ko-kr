---
title: 모델링 프로젝트 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], implementing project objects
- project models, automation
ms.assetid: c8db8fdb-88c1-4b12-86fe-f3c30a18f9ee
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e0edca4a45419a4a4c962ebf62b65e99c4732a12
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2019
ms.locfileid: "58986562"
---
# <a name="project-modeling"></a>프로젝트 모델링
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

표준 프로젝트 개체를 구현 하는 프로젝트에 대 한 자동화를 제공 하는 다음 단계: 합니다 <xref:EnvDTE.Projects> 및 `ProjectItems` 컬렉션에 `Project` 및 <xref:EnvDTE.ProjectItem> 구현에 고유한 나머지 개체와 개체;. 이러한 표준 개체 Dteinternal.h 파일에 정의 됩니다. 표준 개체 구현의 BscPrj 샘플에서 제공 됩니다. Side-by-side-는 표준 프로젝트 개체를 만들려면 모델으로 이러한 클래스를 사용할 수 있습니다 다른 프로젝트 형식에서 프로젝트 개체를 사용 하 여 합니다.  
  
 Automation 소비자를 호출 하려면 가정 <xref:EnvDTE.Solution>("`<UniqueProjName>")` 하 고 <xref:EnvDTE.ProjectItems> (`n`) 여기서 n은 솔루션의 특정 프로젝트 가져오기에 대 한 인덱스 번호입니다. 호출 하는 환경을 사용 하면이 automation 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.GetProperty%2A> VSITEMID_ROOT ItemID 매개 변수 및 VSHPROPID_ExtObject VSHPROPID 매개 변수로 전달 하는 적절 한 프로젝트 계층 구조에서. `IVsHierarchy::GetProperty` 반환 합니다는 `IDispatch` 핵심을 제공 하는 자동화 개체에 대 한 포인터 `Project` 인터페이스를 구현 했습니다.  
  
 다음은 구문의 `IVsHierarchy::GetProperty`합니다.  
  
 `HRESULT GetProperty (`  
  
 `VSITEMID` `itemid`,  
  
 `VSHPROPID` `propid`,  
  
 `VARIANT` `*pvar`  
  
 `);`  
  
 프로젝트 중첩을 수용 하 고 프로젝트 항목의 그룹을 만들 컬렉션을 사용 합니다. 계층 구조는 다음과 같습니다.  
  
```  
Projects  
  |– Project  
      |– ProjectItems (a collection of ProjectItem)  
          |– ProjectItem (single object) or ProjectItems (another collection)  
```  
  
 즉 중첩을 <xref:EnvDTE.ProjectItem> 개체 일 수 있습니다 <xref:EnvDTE.ProjectItems> 동시 컬렉션 때문에 `ProjectItems` 컬렉션에는 중첩 된 개체가 포함 될 수 있습니다. 기본 프로젝트 샘플에서이 중첩을 보여 주지 않습니다. 구현 하 여는 `Project` 전반적인 자동화 모델의 디자인을 지정 하는 트리와 같은 구조에 참여 하는 개체입니다.  
  
 프로젝트 자동화는 다음 다이어그램에 경로 따라갑니다.  
  
 ![Visual Studio 프로젝트 개체](../../extensibility/internals/media/projectobjects.gif "ProjectObjects")  
프로젝트 자동화  
  
 구현 하지 않는 경우는 `Project` 개체를 환경에는 제네릭 반환 여전히 `Project` 프로젝트의 이름만 포함 하는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:EnvDTE.Projects>   
 <xref:EnvDTE.ProjectItem>   
 <xref:EnvDTE.ProjectItems>
