---
title: '방법: 프로그래밍 방식으로 워크시트에서 보호 제거'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bd071a10ab456014190df4f84d6a0bff13c859b8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604849"
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>방법: 프로그래밍 방식으로 워크시트에서 보호 제거
  Microsoft Office Excel 워크시트에서 프로그래밍 방식으로 보호를 제거할 수 있습니다.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 다음 예제에서는 사용자에게서 가져온 암호가 들어 있는 `getPasswordFromUser`변수를 사용합니다.

## <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 워크시트를 보호 해제하려면

1.  호출 된 <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> 메서드 워크시트 및 필요한 경우 암호를 전달 합니다. 이 예제에서는 `Sheet1`이라는 워크시트를 사용한다고 가정합니다.

     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]

## <a name="to-unprotect-a-worksheet-in-a-vsto-add-in"></a>VSTO 추가 기능에서 워크시트의 보호를 해제 하려면

1.  호출 된 <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A> 메서드 활성 워크시트 및 필요한 경우 암호를 전달 합니다.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]

## <a name="see-also"></a>참고자료
- [워크시트 작업](../vsto/working-with-worksheets.md)
- [방법: 프로그래밍 방식으로 워크시트 보호](../vsto/how-to-programmatically-protect-worksheets.md)
- [방법: 프로그래밍 방식으로 통합 문서를 보호](../vsto/how-to-programmatically-protect-workbooks.md)
- [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)
- [Office 프로젝트의 개체에 대 한 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)
