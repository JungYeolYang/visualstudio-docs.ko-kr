---
title: 요소는 명령 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Commands
helpviewer_keywords:
- Commands element (VSCT XML schema)
- VSCT XML schema elements, Commands
ms.assetid: 47cf16a5-d78b-452e-86f6-b5893856dddf
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed21cfb92cbf39b384be512aca640555bb4884f7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550028"
---
# <a name="commands-element"></a>Commands 요소
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Commands 요소](https://docs.microsoft.com/visualstudio/extensibility/commands-element)합니다.  
  
VSPackage 도구 모음에서 명령의 컬렉션을 나타냅니다. 컬렉션 수 최대 5 개의 하위 섹션에서는 다음과 같이: 메뉴, 그룹, 단추, combos, 및 비트맵입니다.  
  
 각 하위 섹션에서는 자식 요소, 예를 들어 \<메뉴 >, GUID 및 숫자 식별자 쌍은 고유 명령 ID로 식별 됩니다. GUID는 "명령 집합"을 식별 하 고 논리적으로 관련 된 명령을 그룹화 하는 데 사용 됩니다. VSPackage는 자체 명령 다른 Vspackage에서 정의 된 명령 Id 사용 하 여 충돌을 방지 하려면 집합을 정의 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<Commands package="GuidMyPackage" >  
  <Menus>... </Menus>  
  <Groups>... </Groups>  
  <Buttons>... </Buttons>  
  <Combos>... </Combos>  
  <Bitmaps>... </Bitmaps>  
</Commands>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|패키지|명령을 제공 하는 VSPackage를 식별 하는 GUID입니다.<br /><br /> 예를 들어 패키지 = "guidVsPackage1Pkg"입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Menus 요소](../extensibility/menus-element.md)|VSPackage를 구현 하는 모든 메뉴를 정의 합니다.|  
|[Groups 요소](../extensibility/groups-element.md)|VSPackage의 명령 그룹을 정의 하는 항목을 포함 합니다.|  
|[Buttons 요소](../extensibility/buttons-element.md)|단추 요소를 그룹화합니다.|  
|[Bitmaps 요소](../extensibility/bitmaps-element.md)|비트맵 요소를 그룹화합니다.|  
|[Combos 요소](../extensibility/combos-element.md)|콤보 요소를 그룹화합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|VSPackage는 IDE를 제공 하는 명령을 나타내는 모든 요소를 정의 합니다. 가능한 요소에는 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자는입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다는 [Commands 요소](../extensibility/commands-element.md)합니다.  
  
```  
<Commands package="guidMyPackage">  
    <Menus>  
      <Menu Condition="'%(DEBUG)' != 'true'"   
        guid="cmdSetGuidMyProductCommands" id="menuIDMainMenu"   
        priority="0x0000" type="Menu">  
        <Annotation>  
          <Documentation>this is an annotation</Documentation>  
          <AppInfo>  
            <CustomData>  
              <CustomSubElement>Some data</CustomSubElement>  
            </CustomData>  
          </AppInfo>  
        </Annotation>  
        <CommandFlag>AlwaysCreate</CommandFlag>  
        <Strings>  
          <ButtonText>MainMenu</ButtonText>  
        </Strings>  
      </Menu>  
  </Menus>  
<Commands>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)
