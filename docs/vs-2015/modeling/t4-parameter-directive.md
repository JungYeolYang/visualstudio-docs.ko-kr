---
title: T4 매개 변수 지시문 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 1d590387-1d9d-40a5-a72c-65fae7a8bdf3
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c7971dc3402a344a5318fd8415404e7a45ae8485
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58986326"
---
# <a name="t4-parameter-directive"></a>T4 매개 변수 지시문
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

에 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 텍스트 템플릿을 `parameter` 지시문 컨텍스트 외부에서 전달 된 값에서 초기화 되는 템플릿 코드에 대 한 속성을 선언 합니다. 텍스트 변환 호출 하는 코드를 작성 하는 경우 이러한 값을 설정할 수 있습니다.  
  
## <a name="using-the-parameter-directive"></a>매개 변수 지시문 사용  
  
```  
<#@ parameter type="Full.TypeName" name="ParameterName" #>  
```  
  
 `parameter` 지시문 컨텍스트 외부에서 전달 된 값에서 초기화 되는 템플릿 코드에 대 한 속성을 선언 합니다. 텍스트 변환 호출 하는 코드를 작성 하는 경우 이러한 값을 설정할 수 있습니다. 값을 전달할 수 있습니다 합니다 `Session` 사전 또는 <xref:System.Runtime.Remoting.Messaging.CallContext>합니다.  
  
 원격으로 사용 가능한 모든 형식의 매개 변수를 선언할 수 있습니다. 형식으로 선언 해야, 즉 <xref:System.SerializableAttribute>에서 파생 되어야 합니다 또는 <xref:System.MarshalByRefObject>합니다. 이 템플릿이 처리 되는 AppDomain에 전달 될 매개 변수 값을 허용 합니다.  
  
 예를 들어 다음 콘텐츠를 사용 하 여 텍스트 템플릿을 작성할 수 있습니다.  
  
```  
<#@ template language="C#" #>  
  
<#@ parameter type="System.Int32" name="TimesToRepeat" #>  
  
<# for (int i = 0; i < TimesToRepeat; i++) { #>  
Line <#= i #>  
<# } #>  
  
```  
  
## <a name="passing-parameter-values-to-a-template"></a>템플릿에 매개 변수 값을 전달합니다.  
 작성 하는 경우는 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 메뉴 명령 또는 이벤트 처리기와 같은 확장을 텍스트 템플릿 서비스를 사용 하 여 서식 파일을 처리할 수 있습니다.  
  
```csharp  
// Get a service provider – how you do this depends on the context:  
IServiceProvider serviceProvider = dte; // or dslDiagram.Store, for example   
// Get the text template service:  
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;  
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;  
// Create a Session in which to pass parameters:  
host.Session = host.CreateSession();  
// Add parameter values to the Session:  
session["TimesToRepeat"] = 5;  
// Process a text template:  
string result = t4.ProcessTemplate("MyTemplateFile.t4",  
  System.IO.File.ReadAllText("MyTemplateFile.t4"));  
  
```  
  
## <a name="passing-values-in-the-call-context"></a>호출 컨텍스트에서 값을 전달합니다.  
 또는 값을 전달할 수의 데이터를 논리적으로 <xref:System.Runtime.Remoting.Messaging.CallContext>입니다.  
  
 다음 예제에서는 두 방법을 사용 하 여 값을 전달 합니다.  
  
```csharp  
ITextTemplating t4 = this.Store.GetService(typeof(STextTemplating)) as ITextTemplating;  
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;  
host.Session = host.CreateSession();  
// Pass a value in Session:  
host.Session["p1"] = 32;  
// Pass another value in CallContext:  
System.Runtime.Remoting.Messaging.CallContext.LogicalSetData("p2", "test");  
  
// Process a small template inline:  
string result = t4.ProcessTemplate("",   
   "<#@parameter type=\"System.Int32\" name=\"p1\"#>"  
 + "<#@parameter type=\"System.String\" name=\"p2\"#>"  
 + "Test <#=p1#> <#=p2#>");  
  
// Result value is:  
//     Test 32 test  
  
```  
  
## <a name="passing-values-to-a-run-time-preprocessed-text-template"></a>전처리 된 런타임 텍스트 템플릿에 값을 전달합니다.  
 일반적으로 사용할 필요가 없기를 `<#@parameter#>` 전처리 된 런타임 텍스트 템플릿을 사용 하 여 지시문입니다. 대신 추가 생성자 또는 매개 변수 값을 전달 하는 생성 된 코드를 설정할 수 있는 속성을 정의할 수 있습니다. 자세한 내용은 [T4 텍스트 템플릿을 사용 하 여 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)합니다.  
  
 그러나 사용 하려는 경우 `<#@parameter>` 런타임 템플릿에서 값을 전달할 수를 세션 사전을 사용 하 여 합니다. 예를 들어 호출 전처리 템플릿으로 파일을 만들었다고 가정해 보겠습니다 `PreTextTemplate1`합니다. 다음 코드를 사용 하 여 템플릿을 프로그램에서 호출할 수 있습니다.  
  
```csharp  
PreTextTemplate1 t = new PreTextTemplate1();  
t.Session = new Microsoft.VisualStudio.TextTemplating.TextTemplatingSession();  
t.Session["TimesToRepeat"] = 5;  
// Add other parameter values to t.Session here.  
t.Initialize(); // Must call this to transfer values.  
string resultText = t.TransformText();  
  
```  
  
## <a name="obtaining-arguments-from-texttemplateexe"></a>TextTemplate.exe에서 인수 가져오기  
  
> [!IMPORTANT]
>  합니다 `parameter` 지시문에 설정 된 값을 검색 하지 않습니다는 `–a` 의 매개 변수는 `TextTransform.exe` 유틸리티입니다. 이러한 값을 얻으려면 설정 `hostSpecific="true"` 에 `template` 지시문을 사용 하 여 `this.Host.ResolveParameterValue("","","argName")`입니다.
