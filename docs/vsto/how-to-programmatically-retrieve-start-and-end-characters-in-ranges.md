---
title: '방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, retrieving start and end characters
- end characters
- start characters
- documents [Office development in Visual Studio], retrieving ranges
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 1f30e06017d4e2a3cba9b20cba8647f995b496a6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56614053"
---
# <a name="how-to-programmatically-retrieve-start-and-end-characters-in-ranges"></a>방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색
  이 예제는 범위의 시작 및 끝 위치의 문자 위치를 가져오는 방법을 보여 줍니다.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-retrieve-start-and-end-characters-of-a-range-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 범위의 시작 및 끝 글자를 가져오려면

1.  <xref:Microsoft.Office.Interop.Word.Range.Start%2A> 개체의 <xref:Microsoft.Office.Interop.Word.Range.End%2A> 및 <xref:Microsoft.Office.Interop.Word.Range> 속성 값을 가져옵니다. 다음 코드 예제에서는 문서의 두 번째 문장에서 시작 및 끝 위치를 가져옵니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#25)]

## <a name="to-retrieve-start-and-end-characters-of-a-range-by-using-a-vsto-add-in"></a>VSTO 추가 기능을 사용 하 여 범위의 시작 및 끝 문자 검색

1.  <xref:Microsoft.Office.Interop.Word.Range.Start%2A> 개체의 <xref:Microsoft.Office.Interop.Word.Range.End%2A> 및 <xref:Microsoft.Office.Interop.Word.Range> 속성 값을 가져옵니다. 다음 코드 예제에서는 활성 문서의 두 번째 문장에서 시작 및 끝 위치를 가져옵니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#25)]

## <a name="see-also"></a>참고자료
- [방법: 프로그래밍 방식으로 정의 하 고 문서에서 범위를 선택 합니다.](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
- [방법: 프로그래밍 방식으로 Word 문서의 범위 다시 설정](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)
- [방법: 프로그래밍 방식으로 범위 또는 문서 선택 영역 축소](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)
- [방법: 프로그래밍 방식으로 제외 단락 표시 범위를 만들 때](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)
- [방법: 프로그래밍 방식으로 문서의 문자 수 계산](../vsto/how-to-programmatically-count-characters-in-documents.md)
