---
title: 관리 코드에 대 한 기본 수정 규칙 규칙 집합 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 631f0daf-1d42-4c90-a7dc-1a6a9de64c93
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 83f0ac2eb1345a8a933e92682e0f6a76ed3d0edf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543112"
---
# <a name="basic-correctness-rules-rule-set-for-managed-code"></a>관리 코드에 대한 기본 수정 규칙 규칙 집합
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [관리 되는 코드에 대 한 기본 수정 규칙 규칙 집합](https://docs.microsoft.com/visualstudio/code-quality/basic-correctness-rules-rule-set-for-managed-code)합니다.  
  
기본 수정 규칙 규칙 집합을 논리 오류 및 일반적인 실수 프레임 워크 Api의 사용량에서에 중점을 둡니다. 기본 수정 규칙 최소 권장 규칙 규칙 집합에 있는 규칙을 포함 합니다. 자세한 내용은 [관리 되는 코드에 대 한 관리 권장 규칙 규칙 집합](../code-quality/managed-recommended-rules-rule-set-for-managed-code.md) 의 최소 권장 규칙 보고서는 경고의 목록을 확장 하려면이 규칙 집합을 포함 해야 합니다.  
  
 다음 표에서 Microsoft 기본 수정 규칙 규칙 집합의 모든 규칙을 설명 합니다.  
  
|규칙|설명|  
|----------|-----------------|  
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.|  
|[CA1009](../code-quality/ca1009-declare-event-handlers-correctly.md)|이벤트 처리기를 제대로 선언하십시오.|  
|[CA1016](../code-quality/ca1016-mark-assemblies-with-assemblyversionattribute.md)|AssemblyVersionAttribute로 어셈블리 표시|  
|[CA1033](../code-quality/ca1033-interface-methods-should-be-callable-by-child-types.md)|인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.|  
|[CA1049](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)|네이티브 리소스가 있는 형식은 삭제 가능해야 합니다.|  
|[CA1060](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)|P/Invoke를 NativeMethods 클래스로 이동|  
|[CA1061](../code-quality/ca1061-do-not-hide-base-class-methods.md)|기본 클래스 메서드를 숨기지 마십시오.|  
|[CA1063](../code-quality/ca1063-implement-idisposable-correctly.md)|IDisposable을 올바르게 구현하십시오.|  
|[CA1065](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)|예기치 않은 위치에서 예외를 발생시키지 마십시오.|  
|[CA1301](../code-quality/ca1301-avoid-duplicate-accelerators.md)|중복 액셀러레이터 키를 사용하지 마십시오.|  
|[CA1400](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)|P/Invoke 진입점이 있어야 합니다.|  
|[CA1401](../code-quality/ca1401-p-invokes-should-not-be-visible.md)|P/Invoke는 노출되지 않아야 합니다.|  
|[CA1403](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)|자동 레이아웃 형식은 COM 노출이면 안 됩니다.|  
|[CA1404](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)|P/Invoke 다음에 바로 GetLastError를 호출하십시오.|  
|[CA1405](../code-quality/ca1405-com-visible-type-base-types-should-be-com-visible.md)|COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.|  
|[CA1410](../code-quality/ca1410-com-registration-methods-should-be-matched.md)|COM 등록 메서드는 일치해야 합니다.|  
|[CA1415](../code-quality/ca1415-declare-p-invokes-correctly.md)|P/Invoke를 올바르게 선언하십시오.|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|빈 종료자를 제거하십시오.|  
|[CA1900](../code-quality/ca1900-value-type-fields-should-be-portable.md)|값 형식 필드는 이식 가능해야 합니다.|  
|[CA1901](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|P/Invoke 선언은 이식 가능해야 합니다.|  
|[CA2002](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|약한 ID를 가진 개체를 잠그지 마십시오.|  
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.|  
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.|  
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|값 형식에서 선언적 보안을 검토하십시오.|  
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|포인터는 노출되면 안 됩니다.|  
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|보안 형식은 필드를 노출하면 안 됩니다.|  
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|메서드 보안은 형식의 상위 집합이어야 합니다.|  
|[CA2116](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|APTCA 메서드는 APTCA 메서드만 호출해야 합니다.|  
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.|  
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.|  
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|재정의 링크 요청은 기본 링크 요청과 같아야 합니다.|  
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|취약한 finally 절을 외부 try에 래핑하십시오.|  
|[CA2126](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|형식 링크 요청에는 상속 요청이 필요합니다.|  
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|보안에 중요한 형식은 형식 동등에 참여할 수 없습니다.|  
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|기본 생성자는 최소한 기본 형식 기본 생성자 만큼 중요 해야 합니다.|  
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|대리자는 투명도가 일관된 메서드에 바인딩되어야 합니다.|  
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|메서드는 기본 메서드를 재정의할 때 일관된 투명도를 유지해야 합니다.|  
|[CA2137](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|투명 메서드에는 확인할 수 있는 IL만 포함되어야 합니다.|  
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|투명 메서드는 SuppressUnmanagedCodeSecurity 특성을 사용하여 메서드를 호출해서는 안 됩니다.|  
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.|  
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|투명 메서드는 LinkDemands를 충족해서는 안 됩니다|  
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|형식은 최소한 기본 형식 및 인터페이스 만큼 중요 해야 합니다.|  
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|투명 메서드는 보안 어설션을 사용할 수 없습니다.|  
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|투명 메서드는 네이티브 코드를 호출해서는 안 됩니다.|  
|[CA2200](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|스택 정보를 유지하도록 다시 throw하십시오.|  
|[CA2202](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|개체를 여러 번 삭제하지 마십시오.|  
|[CA2207](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|값 형식 정적 필드 인라인을 초기화하십시오.|  
|[CA2212](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|서비스 구성 요소를 WebMethod를 사용하여 표시하지 마십시오.|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|삭제 가능한 필드는 삭제해야 합니다.|  
|[CA2214](../code-quality/ca2214-do-not-call-overridable-methods-in-constructors.md)|재정의 가능한 메서드를 생성자에서 호출하지 마십시오.|  
|[CA2216](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|삭제 가능한 형식은 종료자를 선언해야 합니다.|  
|[CA2220](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|종료자는 기본 클래스 종료자를 호출해야 합니다.|  
|[CA2229](../code-quality/ca2229-implement-serialization-constructors.md)|serialization 생성자를 구현하십시오.|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.|  
|[CA2232](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|Windows Forms 진입점을 STAThread를 사용하여 표시하십시오.|  
|[CA2235](../code-quality/ca2235-mark-all-non-serializable-fields.md)|모두 serialize할 수 없는 필드로 표시하십시오.|  
|[CA2236](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.|  
|[CA2237](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|SerializableAttribute로 ISerializable 형식 표시|  
|[CA2238](../code-quality/ca2238-implement-serialization-methods-correctly.md)|serialization 메서드를 올바르게 구현하십시오.|  
|[CA2240](../code-quality/ca2240-implement-iserializable-correctly.md)|ISerializable을 올바르게 구현하십시오.|  
|[CA2241](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|서식 지정 메서드에 올바른 인수를 제공하십시오.|  
|[CA2242](../code-quality/ca2242-test-for-nan-correctly.md)|NaN에 대해 정확하게 테스트하십시오.|  
|[CA1008](../code-quality/ca1008-enums-should-have-zero-value.md)|열거형 값이 0 이면 있어야 합니다.|  
|[CA1013](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)|오버 로드에 같음 연산자를 오버 더하기 및 빼기|  
|[CA1303](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|리터럴을 지역화 된 매개 변수로 전달 하지 마십시오|  
|[CA1308](../code-quality/ca1308-normalize-strings-to-uppercase.md)|문자열을 대문자로 정규화 하십시오.|  
|[CA1806](../code-quality/ca1806-do-not-ignore-method-results.md)|메서드 결과 무시 하지 마십시오|  
|[CA1816](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|GC를 호출 합니다. SuppressFinalize 올바르게|  
|[CA1819](../code-quality/ca1819-properties-should-not-return-arrays.md)|속성은 배열을 반환 해서는|  
|[CA1820](../code-quality/ca1820-test-for-empty-strings-using-string-length.md)|문자열 길이 사용 하 여 문자열이 비었는지 테스트|  
|[CA1903](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|대상된 프레임 워크에서 API만 사용|  
|[CA2004](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|GC에 대 한 호출을 제거 합니다. KeepAlive|  
|[CA2006](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|네이티브 리소스를 캡슐화 하기 위해 SafeHandle 사용|  
|[CA2102](../code-quality/ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)|일반 처리기에서 비 CLSCompliant 예외를 catch 합니다.|  
|[CA2104](../code-quality/ca2104-do-not-declare-read-only-mutable-reference-types.md)|읽기 전용 참조 형식을 선언 하지 마십시오.|  
|[CA2105](../code-quality/ca2105-array-fields-should-not-be-read-only.md)|배열 필드는 읽기 전용 이면 안|  
|[CA2106](../code-quality/ca2106-secure-asserts.md)|보안 어설션|  
|[CA2115](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)|GC를 호출 합니다. KeepAlive 네이티브 리소스를 사용 하는 경우|  
|[CA2119](../code-quality/ca2119-seal-methods-that-satisfy-private-interfaces.md)|Private 인터페이스를 만족 하는 메서드를 봉인|  
|[CA2120](../code-quality/ca2120-secure-serialization-constructors.md)|보안 serialization 생성자|  
|[CA2121](../code-quality/ca2121-static-constructors-should-be-private.md)|정적 생성자는 private 이어야 합니다.|  
|[CA2130](../code-quality/ca2130-security-critical-constants-should-be-transparent.md)|보안 위험 상수는 투명 해야 합니다.|  
|[CA2205](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|관리 되는 Win32 api를 사용 합니다.|  
|[CA2215](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)|Dispose 메서드는 기본 클래스 dispose를 호출 해야 합니다.|  
|[CA2221](../code-quality/ca2221-finalizers-should-be-protected.md)|종료자는 protected 여야|  
|[CA2222](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|노출 수준을 낮추지 마십시오 상속 된 멤버 표시 유형|  
|[CA2223](../code-quality/ca2223-members-should-differ-by-more-than-return-type.md)|멤버 반환 형식 이외의 달라 야 합니다.|  
|[CA2224](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|같음 연산자를 오버 로드할 때 equals 재정의|  
|[CA2226](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|연산자에는 대칭 오버 로드가 있어야 합니다.|  
|[CA2227](../code-quality/ca2227-collection-properties-should-be-read-only.md)|컬렉션 속성은 읽기 전용 이어야|  
|[CA2239](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|선택적 필드에 deserialization 메서드를 제공 합니다.|


