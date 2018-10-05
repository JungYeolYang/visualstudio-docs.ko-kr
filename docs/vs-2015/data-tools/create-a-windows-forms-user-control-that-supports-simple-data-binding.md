---
title: 단순 데이터 바인딩을 지 원하는 Windows Forms 사용자 컨트롤 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- custom controls [Visual Studio], Data Sources Window
- Data Sources Window, controls
ms.assetid: b1488366-6dfb-454e-9751-f42fd3f3ddfb
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a5cb2d1e9d1ea175122381c19fa93c9abc07b2a2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551159"
---
# <a name="create-a-windows-forms-user-control-that-supports-simple-data-binding"></a>단순 데이터 바인딩을 지 원하는 Windows Forms 사용자 컨트롤 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [단순 데이터 바인딩을 지 원하는 사용자 정의 컨트롤 만들기](https://docs.microsoft.com/visualstudio/data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding)합니다.  
  
  
Windows 응용 프로그램에서 폼에 데이터를 표시할 때 기존 컨트롤에서 선택할 수 있습니다 합니다 **도구 상자**, 또는 응용 프로그램에 표준 컨트롤에서 사용할 수 없는 기능이 필요한 경우 사용자 지정 컨트롤을 작성할 수 있습니다. 이 연습에서는 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>를 구현하는 컨트롤을 만드는 방법을 보여줍니다. <xref:System.ComponentModel.DefaultBindingPropertyAttribute>를 구현하는 컨트롤은 데이터에 바인딩할 수 있는 속성 한 개를 포함할 수 있습니다. 이러한 컨트롤은 <xref:System.Windows.Forms.TextBox> 또는 <xref:System.Windows.Forms.CheckBox>와 비슷합니다.  
  
 컨트롤 작성에 대 한 자세한 내용은 참조 하세요. [디자인 타임에 Windows Forms 컨트롤 개발](http://msdn.microsoft.com/library/e5a8e088-7ec8-4fd9-bcb3-9078fd134829)합니다.  
  
 데이터 바인딩 시나리오에서 사용할 컨트롤을 작성할 때 다음 데이터 바인딩 특성 중 하나를 구현 해야 합니다.  
  
|데이터 바인딩 특성 사용법|  
|-----------------------------------|  
|단일 데이터 열이나 속성을 표시하는 <xref:System.ComponentModel.DefaultBindingPropertyAttribute> 등의 단순 컨트롤에 대해 <xref:System.Windows.Forms.TextBox>를 구현합니다. 이 연습 페이지에서 해당 프로세스에 대해 설명합니다.|  
|데이터 목록 또는 테이블을 표시하는 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> 등의 컨트롤에 대해 <xref:System.Windows.Forms.DataGridView>를 구현합니다. 자세한 내용은 [복잡 한 데이터 바인딩을 지 원하는 Windows Forms 사용자 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)합니다.|  
|데이터 목록 또는 테이블을 표시하는 동시에 단일 열이나 속성도 제공해야 하는 <xref:System.ComponentModel.LookupBindingPropertiesAttribute> 등의 컨트롤에 대해 <xref:System.Windows.Forms.ComboBox>를 구현합니다. 자세한 내용은 [조회 데이터 바인딩을 지 원하는 Windows Forms 사용자 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)합니다.|  
  
 이 연습에서는 테이블 내 단일 열의 데이터를 표시하는 단순 컨트롤을 만듭니다. 이 예에서는 Northwind 샘플 데이터베이스 `Phone` 테이블의 `Customers` 열을 사용합니다. 간단한 사용자 정의 컨트롤을 사용 하 여 표준 전화 번호 형식으로 고객의 전화 번호에 표시 됩니다는 <xref:System.Windows.Forms.MaskedTextBox> 및 전화 번호에 마스크를 설정 합니다.  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   새 **Windows 응용 프로그램**합니다.  
  
-   새 **사용자 정의 컨트롤** 프로젝트입니다.  
  
-   사용자 컨트롤을 시각적으로 디자인합니다.  
  
-   `DefaultBindingProperty` 특성을 구현합니다.  
  
-   사용 하 여 데이터 집합을 만들 합니다 **데이터 원본 구성** 마법사.  
  
-   설정 합니다 **Phone** 열에는 **데이터 원본** 새 컨트롤을 사용 하는 창입니다.  
  
-   새 컨트롤에 데이터를 표시할 폼을 만듭니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스. 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
## <a name="create-a-windows-application"></a>Windows 응용 프로그램 만들기  
 첫 번째 단계를 만드는 것을 **Windows 응용 프로그램**합니다.  
  
#### <a name="to-create-the-new-windows-project"></a>새 Windows 프로젝트를 만들려면  
  
1.  Visual Studio에서에서 합니다 **파일** 메뉴에서 새 **프로젝트**합니다.  
  
2.  프로젝트 이름을 **SimpleControlWalkthrough**합니다.  
  
3.  선택 **Windows 응용 프로그램** 누릅니다 **확인**합니다. 자세한 내용은 [클라이언트 응용 프로그램](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)합니다.  
  
     합니다 **SimpleControlWalkthrough** 프로젝트에 추가한 만들어지면 **솔루션 탐색기**합니다.  
  
## <a name="add-a-user-control-to-the-project"></a>사용자 컨트롤을 프로젝트에 추가  
 이 연습에서 단순 데이터 바인딩 가능한 컨트롤을 만듭니다는 **사용자 정의 컨트롤**, 추가 **사용자 정의 컨트롤** 항목을 합니다 **SimpleControlWalkthrough** 프로젝트.  
  
#### <a name="to-add-a-user-control-to-the-project"></a>프로젝트에 사용자 컨트롤을 추가하려면  
  
1.  **프로젝트** 메뉴 선택 **사용자 정의 컨트롤 추가**합니다.  
  
2.  형식 `PhoneNumberBox` 이름 영역 및 클릭 **추가**합니다.  
  
     합니다 **PhoneNumberBox** 컨트롤을 추가할 **솔루션 탐색기**, 디자이너에서 엽니다.  
  
## <a name="design-the-phonenumberbox-control"></a>PhoneNumberBox 컨트롤 디자인  
 이 연습에서는 기존 <xref:System.Windows.Forms.MaskedTextBox>를 확장하여 `PhoneNumberBox` 컨트롤을 만듭니다.  
  
#### <a name="to-design-the-phonenumberbox-control"></a>PhoneNumberBox 컨트롤을 디자인하려면  
  
1.  끌어서를 <xref:System.Windows.Forms.MaskedTextBox> 에서 합니다 **도구 상자** 사용자 컨트롤의 디자인 화면으로 합니다.  
  
2.  스마트 태그를 선택 합니다 <xref:System.Windows.Forms.MaskedTextBox> 방금를 하 고 선택 **마스크 설정**합니다.  
  
3.  선택 **전화 번호** 에 **입력 마스크** 대화 상자를 클릭 **확인** 여 마스크를 설정 합니다.  
  
## <a name="add-the-required-data-binding-attribute"></a>필요한 데이터 바인딩 특성 추가  
 데이터 바인딩을 지원하는 단순 컨트롤에 대해 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>를 구현합니다.  
  
#### <a name="to-implement-the-defaultbindingproperty-attribute"></a>DefaultBindingProperty 특성을 구현하려면  
  
1.  `PhoneNumberBox` 컨트롤을 코드 보기로 전환합니다. (에 **뷰** 메뉴 선택 **코드**.)  
  
2.  `PhoneNumberBox`의 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[VbRaddataDisplaying#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/PhoneNumberBox.cs#3)]
     [!code-vb[VbRaddataDisplaying#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/PhoneNumberBox.vb#3)]  
  
3.  **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
## <a name="create-a-data-source-from-your-database"></a>데이터베이스에서 데이터 원본 만들기  
 이 단계에서는 합니다 **데이터 소스 구성**기반으로 하는 데이터 원본을 만들려면 마법사를 `Customers` Northwind 샘플 데이터베이스의 테이블입니다. 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다. Northwind 샘플 데이터베이스 설정에 대 한 내용은 참조 하세요 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성** 마법사.  
  
3.  에 **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 클릭 하 고 **다음**합니다.  
  
4.  에 **데이터 연결 선택** 페이지에서 다음 중 하나를 수행 합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
    -   선택 **새 연결** 시작 하는 **연결 추가/수정** 대화 상자.  
  
5.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 한 다음 클릭 옵션을 선택 **다음**합니다.  
  
6.  에 **응용 프로그램 구성 파일에 연결 문자열을 저장** 페이지에서 클릭 **다음**합니다.  
  
7.  에 **데이터베이스 개체 선택** 페이지에서 확장을 **테이블** 노드.  
  
8.  선택 된 `Customers` 테이블을 선택한 다음 클릭 **완료**합니다.  
  
     **NorthwindDataSet** 프로젝트에 추가 됩니다 및 `Customers` 테이블에 표시 합니다 **데이터 원본** 창입니다.  
  
## <a name="set-the-phone-column-to-use-the-phonenumberbox-control"></a>PhoneNumberBox 컨트롤을 사용 하도록 phone 열 설정  
 내 합니다 **데이터 원본** 창에서 폼으로 항목 끌기 전에 만들 컨트롤을 설정할 수 있습니다.  
  
#### <a name="to-set-the-phone-column-to-bind-to-the-phonenumberbox-control"></a>PhoneNumberBox 컨트롤에 바인딩되도록 Phone 열을 설정하려면  
  
1.  오픈 **Form1** 디자이너에서 합니다.  
  
2.  확장 된 **고객** 에서 노드를 **데이터 원본** 창.  
  
3.  드롭다운 화살표를 클릭 합니다 **고객** 노드를 선택 하 고 **세부 정보** 컨트롤 목록에서.  
  
4.  드롭다운 화살표를 클릭 합니다 **Phone** 열 선택 **사용자 지정**합니다.  
  
5.  선택 된 **PhoneNumberBox** 목록에서 **연결 된 컨트롤** 에 **데이터 UI 사용자 지정 옵션** 대화 상자.  
  
6.  드롭다운 화살표를 클릭 합니다 **Phone** 열 선택 **PhoneNumberBox**합니다.  
  
## <a name="addcontrols-to-the-form"></a>폼에 Addcontrols  
 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수는 **데이터 원본** 창에서 폼입니다.  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>폼에서 데이터 바인딩된 컨트롤을 만들려면  
  
-   주를 끌어 **고객** 에서 노드를 **데이터 원본** 창에서 폼으로 하 고 있는지 확인 합니다 `PhoneNumberBox` 컨트롤은 데이터를 표시 하는 데 사용를 `Phone` 열.  
  
     설명 레이블이 있는 데이터 바인딩된 컨트롤이 레코드 탐색을 위한 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>와 함께 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)를 [CustomersTableAdapter](../data-tools/tableadapter-overview.md)를 <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
## <a name="run-the-application"></a>응용 프로그램 실행  
  
#### <a name="to-run-the-application"></a>응용 프로그램을 실행하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
## <a name="next-steps"></a>다음 단계  
 응용 프로그램 요구 사항에 따라 데이터 바인딩을 지원하는 컨트롤을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다. 일반적으로 수행하는 몇 가지 단계는 다음과 같습니다.  
  
-   다른 응용 프로그램에서 다시 사용할 수 있도록 컨트롤 라이브러리에 사용자 지정 컨트롤을 배치합니다.  
  
-   보다 복잡한 데이터 바인딩 시나리오를 지원하는 컨트롤을 만듭니다. 자세한 내용은 [복잡 한 데이터 바인딩을 지 원하는 Windows Forms 사용자 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md) 하 고 [조회 데이터 바인딩을 지 원하는 Windows Forms 사용자 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)
