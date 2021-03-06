---
title: 네트워크 기반 설치 업데이트
description: --layout 명령을 사용하여 네트워크 기반 Visual Studio 설치를 업데이트하는 방법 알아보기
ms.date: 2/22/2019
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 1AF69C0E-0AC9-451B-845D-AE4EDBCEA65C
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 4f7f7a7297b7cc48b9300c21875af5a0971136e1
ms.sourcegitcommit: 8d453b345c72339c37b489a140dad00b244e6ba4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58475983"
---
# <a name="update-a-network-based-installation-of-visual-studio"></a>Visual Studio의 네트워크 기반 설치 업데이트

최신 제품 업데이트를 사용하여 Visual Studio의 네트워크 설치 레이아웃을 업데이트할 수 있으므로, 해당 레이아웃을 Visual Studio의 최신 업데이트에 대한 설치 지점으로 사용하거나 이미 클라이언트 워크스테이션에 배포된 설치를 유지 관리하는 데 사용할 수 있습니다.

## <a name="how-to-update-a-network-layout"></a>네트워크 레이아웃을 업데이트하는 방법

최신 업데이트를 포함하도록 네트워크 설치 공유를 새로 고치려면 `--layout` 명령을 실행하여 업데이트된 패키지를 점진적으로 다운로드합니다.

**15.3의 새로운 기능**: 네트워크 레이아웃을 처음 만들 때 부분 레이아웃을 선택했다면 이러한 설정이 저장됩니다.  이후 모든 레이아웃 명령은 이전 옵션과 함께 지정하는 새 옵션을 사용합니다. 그러나 이전 버전의 레이아웃을 사용 중인 경우에는 네트워크 설치 레이아웃을 처음 만들 때 사용한 것과 같은 명령줄 매개 변수(즉, 같은 워크로드 및 언어)를 사용하여 콘텐츠를 업데이트해야 합니다.

레이아웃을 파일 공유에서 호스트하는 경우 개인 레이아웃 복사본(예: c:\vs2017offline)을 업데이트하고 업데이트된 콘텐츠가 모두 다운로드된 후 해당 복사본을 파일 공유(예: \\server\products\VS2017)로 복사합니다. 이 작업을 하지 않으면 레이아웃이 업데이트되는 동안 설치 프로그램을 실행하는 사용자가 레이아웃에서 일부 콘텐츠를 가져오지 못할 수 있습니다. 이는 레이아웃이 완전히 업데이트되지 않았기 때문입니다.

레이아웃을 만든 다음, 업데이트하는 방법에 대한 몇 가지 예를 살펴보겠습니다.

* 먼저, 다음은 영어용 워크로드 하나만 포함된 레이아웃을 만드는 방법의 예입니다.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --lang en-US
  ```

* 다음은 이 동일한 레이아웃을 최신 버전으로 업데이트하는 방법입니다. 명령줄 매개 변수를 추가로 지정할 필요가 없습니다. 이전 설정이 저장되어 이 레이아웃 폴더의 모든 후속 레이아웃 명령에 사용됩니다.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout
  ```

* 무인 방식으로 레이아웃에 최신 버전으로 업데이트하는 방법은 다음과 같습니다. 레이아웃 작업은 새 콘솔 창에서 설치 프로세스를 실행합니다. 사용자가 최종 결과는 물론, 발생했을 수 있는 오류에 대한 요약을 볼 수 있도록 창이 열려 있습니다. 무인 방식으로 레이아웃 작업을 수행하고 있는 경우(예를 들어 레이아웃을 최신 버전으로 업데이트하기 위해 정기적으로 실행되는 스크립트가 있는 경우) `--passive` 매개 변수를 사용하면 프로세스는 창을 자동으로 종료하니다.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout --passive
  ```

* 다음은 추가 워크로드와 지역화된 언어를 추가하는 방법입니다.  여기의 명령은 Azure 워크로드를 추가합니다.  이제 관리되는 데스크톱과 Azure가 이 레이아웃에 포함됩니다.  이러한 모든 워크로드에 대해 영어 및 독일어용 언어 리소스도 포함됩니다.  그리고 레이아웃이 사용 가능한 최신 버전으로 업데이트됩니다.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.Azure --lang de-DE
  ```

    > [!IMPORTANT]
    > 업데이트 작업은 [응답 파일](automated-installation-with-response-file.md)의 "추가" 섹션에 이러한 구성 요소를 포함하더라도 새로 추가된 선택적 구성 요소를 설치하지 않습니다. 이는 업데이트하는 동안 추가 작업이 사용되지 않기 때문에 발생합니다.<br>
    > **해결 방법**: 업그레이드 후 별도의 수정 작업을 실행하여 누락된 구성 요소를 설치합니다.

* 마지막으로 버전을 업데이트하지 않고 워크로드와 지역화된 언어를 추가하는 방법은 다음과 같습니다. 여기의 명령은 ASP.NET 및 웹 워크로드를 추가합니다.  이제 관리되는 데스크톱, Azure, ASP.NET 및 웹 워크로드가 이 레이아웃에 포함됩니다. 이러한 모든 워크로드에 대해 영어, 독일어 및 프랑스어용 언어 리소스도 포함됩니다.  그러나 이 명령이 실행될 때 레이아웃이 사용 가능한 최신 버전으로 업데이트되지 않았고, 기존 버전으로 유지됩니다.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.NetWeb --lang fr-FR --keepLayoutVersion
  ```

## <a name="how-to-deploy-an-update-to-client-machines"></a>업데이트를 클라이언트 컴퓨터에 배포하는 방법

네트워크 환경 구성 방법에 따라 엔터프라이즈 관리자가 업데이트를 배포하거나 클라이언트 컴퓨터에서 업데이트를 시작할 수 있습니다.

* 사용자는 오프라인 설치 폴더에서 설치된 Visual Studio 인스턴스를 업데이트할 수 있습니다.
  * Visual Studio 설치 관리자를 실행합니다.
  * 그런 다음 **업데이트**를 클릭합니다.

* 관리자는 다음 두 가지 명령을 각각 사용하여 사용자 조작 없이 Visual Studio의 클라이언트 배포를 업데이트할 수 있습니다.
  * 먼저 Visual Studio 설치 관리자를 업데이트합니다. <br>```vs_enterprise.exe --quiet --update```
  * 그다음에 Visual Studio 애플리케이션 자체를 업데이트합니다. <br>```vs_enterprise.exe update --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" --quiet --wait --norestart```

> [!NOTE]
> [vswhere.exe 명령](tools-for-managing-visual-studio-instances.md)을 사용하여 클라이언트 컴퓨터에서 기존 Visual Studio 인스턴스의 설치 경로를 확인합니다.
>
> [!TIP]
> 사용자에게 업데이트 알림이 제공되는 시점을 제어하는 방법에 대한 자세한 내용은 [네트워크 기반 Visual Studio 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md)를 참조하세요.

## <a name="how-to-verify-a-layout"></a>레이아웃을 확인하는 방법

`--verify`를 사용하여 제공된 오프라인 캐시에 대한 확인을 수행할 수 있습니다. 이 명령은 패키지 파일이 누락되거나 잘못되었는지 확인합니다. 확인이 끝나면 누락된 파일과 잘못된 파일의 목록을 표시합니다.

```cmd
vs_enterprise.exe --layout <layoutDir> --verify
```

vs_enterprise.exe는 layoutDir 내에서 호출할 수 있습니다.

> [!NOTE]
> `--verify` 옵션에 필요한 몇 가지 중요한 메타데이터 파일이 레이아웃 오프라인 캐시에 있어야 합니다. 이러한 메타데이터 파일을 사용할 수 없으면 “--verify”가 실행될 수 없고 설치 프로그램에서 오류가 발생합니다. 이 오류가 발생하는 경우 새 오프라인 레이아웃을 다른 폴더나 같은 오프라인 캐시 폴더에 다시 만듭니다. 이렇게 하려면 초기 오프라인 레이아웃을 만드는 데 사용한 동일한 레이아웃 명령을 실행합니다. 예를 들어, `Vs_enterprise.exe --layout <layoutDir>`을 입력합니다.

Microsoft에서 Visual Studio 업데이트를 정기적으로 제공하므로, 만드는 새 레이아웃은 초기 레이아웃과 버전이 같지 않을 수 있습니다.

> [!NOTE]
> 확인은 Visual Studio의 특정 부 버전의 최신 버전에 대해서만 작동합니다. 새 버전이 출시되는 즉시 동일한 부 버전의 이전 패치 수준 릴리스에서는 확인이 작동하지 않습니다.

## <a name="how-to-fix-a-layout"></a>레이아웃을 수정하는 방법

`--fix`를 사용하여 `--verify`와 동일한 확인을 수행하고 식별된 문제를 해결해 볼 수도 있습니다. `--fix` 프로세스를 실행하려면 인터넷 연결이 필요하므로 `--fix`를 호출하기 전에 컴퓨터가 인터넷에 연결되어 있는지 확인합니다.

```cmd
vs_enterprise.exe --layout <layoutDir> --fix
```

vs_enterprise.exe는 layoutDir 내에서 호출할 수 있습니다.

## <a name="how-to-remove-older-versions-from-a-layout"></a>레이아웃에서 이전 버전을 제거하는 방법

오프라인 캐시에 대한 레이아웃 업데이트를 수행한 후 레이아웃 캐시 폴더에 최신 Visual Studio 설치에 더 이상 필요하지 않은 사용되지 않는 패키지가 일부 포함되어 있을 수 있습니다. `--clean` 옵션을 사용하여 오프라인 캐시 폴더에서 사용되지 않는 패키지를 제거할 수 있습니다.

이렇게 하려면 이러한 사용되지 않는 패키지를 포함하는 카탈로그 매니페스트에 대한 파일 경로가 필요합니다. 카탈로그 매니페스트는 오프라인 레이아웃 캐시의 “보관” 폴더에서 찾을 수 있으며 레이아웃을 업데이트할 때 이 위치에 저장됩니다. “보관” 폴더에는 하나 이상의 “GUID” 폴더가 있고 각 폴더에는 사용되지 않는 카탈로그 매니페스트가 포함되어 있습니다. “GUID” 폴더의 수는 오프라인 캐시를 업데이트한 수와 동일합니다.

소수의 파일이 각 “GUID” 폴더 안에 저장됩니다. 가장 관심이 가는 두 파일은 “catalog.json” 파일과 “version.txt” 파일입니다. “catalog.json” 파일은 `--clean` 옵션에 전달해야 하는 사용되지 않는 카탈로그 매니페스트입니다. 다른 version.txt 파일에는 이 사용되지 않는 카탈로그 매니페스트의 버전이 포함되어 있습니다. 버전 번호를 기준으로 이 카탈로그 매니페스트에서 사용되지 않는 패키지를 제거할지를 결정할 수 있습니다. 다른 “GUID” 폴더를 확인할 때도 동일한 작업을 수행할 수 있습니다. 정리할 카탈로그를 결정한 후 이러한 카탈로그의 파일 경로를 지정하여 `--clean` 명령을 실행합니다.

다음은 --clean 옵션을 사용하는 방법에 대한 몇 가지 예입니다.

```cmd
vs_enterprise.exe --layout <layoutDir> --clean <file-path-of-catalog1> <file-path-of-catalog2> …
```

```cmd
vs_enterprise.exe --layout <layoutDir> --clean <file-path-of-catalog1> --clean <file-path-of-catalog2> …
```

vs_enterprise.exe를 &lt;layoutDir&gt; 내에서 호출할 수도 있습니다. 예를 들면 다음과 같습니다.

```cmd
c:\VS2017Layout\vs_enterprise.exe --layout c:\VS2017Layout --clean c:\VS2017Layout\Archive\1cd70189-fc55-4583-8ad8-a2711e928325\Catalog.json --clean c:\VS2017Layout\Archive\d420889f-6aad-4ba4-99e4-ed7833795a10\Catalog.json
```

이 명령을 실행하면 설치 프로그램은 오프라인 캐시 폴더를 분석하여 제거할 파일 목록을 찾습니다. 그러면 삭제될 파일을 검토하고 삭제를 확인할 수 있습니다.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>참고 항목

* [Visual Studio 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 인스턴스 검색 및 관리 도구](tools-for-managing-visual-studio-instances.md)
* [네트워크 기반 Visual Studio 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md)
