---
title: CEnumeratorAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
- CEnumeratorAccessor.m_bIsParent
- ATL::CEnumeratorAccessor::m_bIsParent
- m_bIsParent
- ATL.CEnumeratorAccessor.m_bIsParent
- CEnumeratorAccessor::m_bIsParent
- ATL::CEnumeratorAccessor::m_nType
- CEnumeratorAccessor.m_nType
- CEnumeratorAccessor::m_nType
- ATL.CEnumeratorAccessor.m_nType
- m_nType
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
- m_szName
- ATL::CEnumeratorAccessor::m_szName
- CEnumeratorAccessor.m_szName
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
ms.openlocfilehash: e609b346bb4a0c2469c24e20540c646fa869ae26
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025169"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor Sınıfı

Tarafından kullanılan [CEnumerator](../../data/oledb/cenumerator-class.md) Numaralandırıcı satır kümesinden verilere erişmek için.

## <a name="syntax"></a>Sözdizimi

```cpp
class CEnumeratorAccessor
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_bIsParent](#bisparent)|Satır bir numaralandırıcı ise Numaralandırıcı bir üst Numaralandırıcı olup olmadığını belirten bir değişken.|
|[m_nType](#ntype)|Satır bir veri kaynağı veya bir numaralandırıcı tanımlayıp tanımlamadığını belirten bir değişken.|
|[m_szDescription](#szdescription)|Veri kaynağı veya numaralandırıcı açıklaması.|
|[m_szName](#szname)|Veri kaynağı veya numaralandırıcı adı.|
|[m_szParseName](#szparsename)|Geçirilecek dize [IParseDisplayName](/windows/desktop/api/oleidl/nn-oleidl-iparsedisplayname) Numaralandırıcı ve veri kaynağı için bir bilinen ad elde edilir.|

## <a name="remarks"></a>Açıklamalar

Bu satır kümesi veri kaynakları ve geçerli Numaralandırıcının görünür numaralandırıcılar oluşur.

## <a name="bisparent"></a> Cenumeratoraccessor::m_bısparent

Satır bir numaralandırıcı ise Numaralandırıcı bir üst Numaralandırıcı olup olmadığını belirten bir değişken.

### <a name="syntax"></a>Sözdizimi

```cpp
VARIANT_BOOL m_bIsParent;
```

### <a name="remarks"></a>Açıklamalar

Bkz: [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) içinde *OLE DB Programcının Başvurusu* daha fazla bilgi için.

## <a name="ntype"></a> CEnumeratorAccessor::m_nType

Satır bir veri kaynağı veya bir numaralandırıcı tanımlayıp tanımlamadığını belirten bir değişken.

### <a name="syntax"></a>Sözdizimi

```cpp
USHORT m_nType;
```

### <a name="remarks"></a>Açıklamalar

Bkz: [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) içinde *OLE DB Programcının Başvurusu* daha fazla bilgi için.

## <a name="szdescription"></a> CEnumeratorAccessor::m_szDescription

Veri kaynağı veya numaralandırıcı açıklaması.

### <a name="syntax"></a>Sözdizimi

```cpp
WCHAR m_szDescription[129];
```

### <a name="remarks"></a>Açıklamalar

Bkz: [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) içinde *OLE DB Programcının Başvurusu* daha fazla bilgi için.

## <a name="szname"></a> CEnumeratorAccessor::m_szName

Veri kaynağı veya numaralandırıcı adı.

### <a name="syntax"></a>Sözdizimi

```cpp
WCHAR m_szName[129];
```

### <a name="remarks"></a>Açıklamalar

Bkz: [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) içinde *OLE DB Programcının Başvurusu* daha fazla bilgi için.

## <a name="szparsename"></a> CEnumeratorAccessor::m_szParseName

Geçirilecek dize [IParseDisplayName](/windows/desktop/api/oleidl/nn-oleidl-iparsedisplayname) Numaralandırıcı ve veri kaynağı için bir bilinen ad elde edilir.

### <a name="syntax"></a>Sözdizimi

```cpp
WCHAR m_szParseName[129];
```

### <a name="remarks"></a>Açıklamalar

Bkz: [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) içinde *OLE DB Programcının Başvurusu* daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)