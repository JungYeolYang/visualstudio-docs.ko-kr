---
title: '연습: 텍스트 뷰 사용자 지정 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - customizing the view
ms.assetid: 32d32ac8-22ff-4de7-af69-bd46ec4ad9bf
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f141fb6a29a012dbd185c258610c3e4b1d362629
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58985109"
---
# <a name="walkthrough-customizing-the-text-view"></a>연습: 텍스트 보기 사용자 지정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

편집기 서식 맵에에서 다음 속성 중 하나를 수정 하 여 텍스트 뷰를 사용자 지정할 수 있습니다.  
  
-   표시기 여백  
  
-   삽입 캐럿  
  
-   캐럿을 덮어쓰기  
  
-   선택한 텍스트  
  
-   선택한 비활성 텍스트 (즉, 선택한 텍스트의 포커스가 있는)  
  
-   공백 표시  
  
## <a name="prerequisites"></a>전제 조건  
 Visual Studio 2015부터 수행 설치 하면 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-mef-project"></a>MEF 프로젝트 만들기  
  
1.  C# VSIX 프로젝트를 만듭니다. (에 **새 프로젝트** 대화 상자에서 **Visual C# / 확장성**, 한 다음 **VSIX 프로젝트**.) 솔루션의 이름을 `ViewPropertyTest`로 지정합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
## <a name="defining-the-content-type"></a>콘텐츠 형식 정의  
  
1. 클래스 파일을 추가하고 이름을 `ViewPropertyModifier`로 지정합니다.  
  
2. 다음 추가 `using` 지시문:  
  
    [!code-csharp[VSSDKViewPropertyTest#1](../snippets/csharp/VS_Snippets_VSSDK/vssdkviewpropertytest/cs/viewpropertymodifier.cs#1)]
    [!code-vb[VSSDKViewPropertyTest#1](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkviewpropertytest/vb/viewpropertymodifier.vb#1)]  
  
3. 이라는 클래스를 선언 `TestViewCreationListener` 에서 상속 되는 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener>합니다. 이 클래스는 다음과 같은 특성을 내보냅니다.  
  
   - <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> 이 수신기가 적용 되는 콘텐츠의 형식을 지정 합니다.  
  
   - <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute> 이 수신기의 역할을 지정 합니다.  
  
     [!code-csharp[VSSDKViewPropertyTest#2](../snippets/csharp/VS_Snippets_VSSDK/vssdkviewpropertytest/cs/viewpropertymodifier.cs#2)]
     [!code-vb[VSSDKViewPropertyTest#2](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkviewpropertytest/vb/viewpropertymodifier.vb#2)]  
  
4. 이 클래스에서 가져오기는 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>합니다.  
  
    [!code-csharp[VSSDKViewPropertyTest#3](../snippets/csharp/VS_Snippets_VSSDK/vssdkviewpropertytest/cs/viewpropertymodifier.cs#3)]
    [!code-vb[VSSDKViewPropertyTest#3](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkviewpropertytest/vb/viewpropertymodifier.vb#3)]  
  
## <a name="changing-the-view-properties"></a>보기 속성 변경  
  
1.  구현 된 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> 메서드는 보기 속성 보기를 열 때 변경 됩니다. 을 변경 하려면 먼저 찾습니다는 <xref:System.Windows.ResourceDictionary> 찾으려는 뷰의 측면에 해당 하는 합니다. 그런 다음 리소스 사전에 적절 한 속성을 변경 하 고 속성을 설정 합니다. 에 대 한 호출을 일괄 처리를 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.SetProperties%2A> 메서드를 호출 합니다 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.BeginBatchUpdate%2A> 속성을 설정 하기 전에 차례로 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.EndBatchUpdate%2A> 속성을 설정한 후 합니다.  
  
     [!code-csharp[VSSDKViewPropertyTest#4](../snippets/csharp/VS_Snippets_VSSDK/vssdkviewpropertytest/cs/viewpropertymodifier.cs#4)]
     [!code-vb[VSSDKViewPropertyTest#4](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkviewpropertytest/vb/viewpropertymodifier.vb#4)]  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
  
1.  솔루션을 빌드합니다.  
  
     디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
2.  텍스트 파일을 만들고 일부 텍스트를 입력합니다.  
  
    -   삽입 캐럿 자홍 해야 및 덮어쓰기 캐럿 옥색 이어야 합니다.  
  
    -   표시기 여백 (왼쪽 텍스트 뷰)에 밝은 해야 합니다. 녹색입니다.  
  
3.  방금 입력 한 텍스트를 선택 합니다. 선택한 텍스트의 색 light 해야 분홍색 합니다.  
  
4.  텍스트를 선택한 상태에서 텍스트 창 외부 아무 곳 이나 클릭 합니다. 선택한 텍스트의 색 어두운 분홍 이어야 합니다.  
  
5.  공백 표시를 켭니다. (에 **편집** 메뉴에서 **고급** 을 클릭 한 다음 **공백 보기**). 일부 탭 텍스트에 입력 합니다. 탭을 나타내는 빨간색 화살표가 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)
