---
title: 요소 (Visual Studio 템플릿)를 참조 | Microsoft Docs
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
- http://schemas.microsoft.com/developer/vstemplate/2005#References
helpviewer_keywords:
- <References> element [Visual Studio Templates]
- References element [Visual Studio Templates]
ms.assetid: 1969146d-46bf-422d-8d46-0e9493925003
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 54ff9d03291adf55f0bae3d4cb85d5f8c075b431
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551952"
---
# <a name="references-element-visual-studio-templates"></a>References 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [References 요소 (Visual Studio 템플릿)](https://docs.microsoft.com/visualstudio/extensibility/references-element-visual-studio-templates)합니다.  
  
서식 파일 프로젝트에 추가 하는 어셈블리 참조를 그룹화 합니다.  
  
 \<VSTemplate>  
 \<TemplateContent >  
 \<참조 >  
  
## <a name="syntax"></a>구문  
  
```  
<References>  
    <Reference>... </Reference>  
    <Reference>... </Reference>  
    ...  
</References>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[참조](../extensibility/reference-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 항목이 프로젝트에 추가될 때 추가할 어셈블리 참조를 지정합니다. 하나 이상 이어야 `Reference` 의 요소를 `References` 요소입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|서식 파일의 내용을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 `References`은 `TemplateContent`의 선택적 자식 요소입니다.  
  
 `Reference` 하 고 `References` 요소.vstemplate 파일에서 사용할 수 있습니다를 `Type` 특성 값 `Item`합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `TemplateContent` 항목 템플릿의 요소입니다. 이 XML에는 System.dll 및 System.Data.dll 어셈블리에 대 한 참조를 추가합니다.  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)
