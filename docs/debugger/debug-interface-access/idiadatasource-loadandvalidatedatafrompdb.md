---
title: 'Idiadatasource:: Loadandvalidatedatafrompdb | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadAndValidateDataFromPdb method
ms.assetid: d66712dd-6c24-4192-919a-cce262066f0e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5426e27d7b100c42cd571935b1634d6dbd6e990f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56626143"
---
# <a name="idiadatasourceloadandvalidatedatafrompdb"></a>IDiaDataSource::loadAndValidateDataFromPdb
열립니다 및 프로그램 데이터베이스 (.pdb) 파일에 제공 된 서명을 정보와 일치 하는지 확인 하 고 디버그 데이터 소스로.pdb 파일을 준비 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT loadAndValidateDataFromPdb ( 
   LPCOLESTR pdbPath,
   GUID*     pcsig70,
   DWORD     sig,
   DWORD     age
);
```

#### <a name="parameters"></a>매개 변수
`pdbPath`

[in] .Pdb 파일에 대 한 경로입니다.

`pcsig70`

[in] .Pdb 파일 서명을 확인할 GUID 서명입니다. 만.pdb 파일 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] GUID 서명을 나중에 한 합니다.

`sig`

[in] 32 비트 서명.pdb 파일 서명에 대 한 확인입니다.

`age`

[in] 확인 하려면 보존 기간 값입니다. 보존 기간 반드시 모든 알려진된 시간 값에 해당 하지 않는,.pdb 파일을 해당.exe 파일을 사용 하 여 동기화 되었는지 확인 하려면 사용 됩니다.

## <a name="return-value"></a>반환 값
성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 다음 표에서이 메서드에 대 한 가능한 반환 값을 보여 줍니다.

|값|설명|
|-----------|-----------------|
|E_PDB_NOT_FOUND|파일을 열지 못했습니다. 또는 파일 형식이 잘못 되었습니다.|
|E_PDB_FORMAT|사용 되지 않는 형식으로 파일에 액세스 하려고 했습니다.|
|E_PDB_INVALID_SIG|서명이 일치 하지 않습니다.|
|E_PDB_INVALID_AGE|기간 일치 하지 않습니다.|
|E_INVALIDARG|잘못된 매개 변수입니다.|
|E_UNEXPECTED|이미 데이터 소스를 준비 했습니다.|

## <a name="remarks"></a>주의
.Pdb 파일 서명 및 보존 기간 값을 포함 합니다. 이러한 값은.pdb 파일과 일치 하는.exe 또는.dll 파일에 복제 됩니다. 데이터 소스를 준비 하기 전에이 메서드는 명명 된.pdb 파일의 서명 및 age 제공 된 값과 일치 하는지 확인 합니다.

유효성 검사 없이.pdb 파일을 로드 하려면 사용 합니다 [idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 메서드.

(콜백 메커니즘을)를 통해 데이터 로드 프로세스에 대 한 액세스 권한을 사용 합니다 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.

메모리에서 직접.pdb 파일을 로드 하려면 사용 합니다 [idiadatasource:: Loaddatafromistream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) 메서드.

## <a name="example"></a>예제

```C++
IDiaDataSource* pSource;  // Previously created data source.
DEFINE_GUID(expectedGUIDSignature,0x1234,0x5678,0x01,0x02,0x03,0x04,0x05,0x06,0x07,0x08);
DWORD expectedFileSignature = 0x12345678;
DWORD expectedAge           = 128;

HRESULT hr;
hr = pSource->loadAndValidateDataFromPdb( L"yprog.pdb",
                                          &expectedGUIDSignature,
                                          expectedFileSignature,
                                          expectedAge);
if (FAILED(hr))
{
    // Report an error
}

```

## <a name="see-also"></a>참고 항목
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)
- [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)
