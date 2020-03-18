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
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
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
ms.openlocfilehash: d85f630a01ab7e2a07035a8a304a56be91eca8a9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442005"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor Sınıfı

Bir Numaralandırıcı satır kümesinden veriye erişmek için [CEnumerator](../../data/oledb/cenumerator-class.md) tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class CEnumeratorAccessor
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_bIsParent](#bisparent)|Satır bir Numaralandırıcı ise, Numaralandırıcının bir üst Numaralandırıcı olup olmadığını gösteren bir değişken.|
|[m_nType](#ntype)|Satırın bir veri kaynağını mı yoksa bir Numaralandırıcı mi olduğunu gösteren bir değişken.|
|[m_szDescription](#szdescription)|Veri kaynağının veya Numaralandırıcının açıklaması.|
|[m_szName](#szname)|Veri kaynağının veya Numaralandırıcının adı.|
|[m_szParseName](#szparsename)|Veri kaynağı veya Numaralandırıcı için bir bilinen ad almak üzere [IParseDisplayName](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname) 'e geçirilecek dize.|

## <a name="remarks"></a>Açıklamalar

Bu satır kümesi, geçerli Numaralandırıcı tarafından görünen veri kaynaklarından ve numaralandırıcılardan oluşur.

## <a name="bisparent"></a>CEnumeratorAccessor:: m_bIsParent

Satır bir Numaralandırıcı ise, Numaralandırıcının bir üst Numaralandırıcı olup olmadığını gösteren bir değişken.

### <a name="syntax"></a>Sözdizimi

```cpp
VARIANT_BOOL m_bIsParent;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *OLE DB Programcının başvurusunda* bulunan [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) bölümüne bakın.

## <a name="ntype"></a>CEnumeratorAccessor:: m_nType

Satırın bir veri kaynağını mı yoksa bir Numaralandırıcı mi olduğunu gösteren bir değişken.

### <a name="syntax"></a>Sözdizimi

```cpp
USHORT m_nType;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *OLE DB Programcının başvurusunda* bulunan [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) bölümüne bakın.

## <a name="szdescription"></a>CEnumeratorAccessor:: m_szDescription

Veri kaynağının veya Numaralandırıcının açıklaması.

### <a name="syntax"></a>Sözdizimi

```cpp
WCHAR m_szDescription[129];
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *OLE DB Programcının başvurusunda* bulunan [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) bölümüne bakın.

## <a name="szname"></a>CEnumeratorAccessor:: m_szName

Veri kaynağının veya Numaralandırıcının adı.

### <a name="syntax"></a>Sözdizimi

```cpp
WCHAR m_szName[129];
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *OLE DB Programcının başvurusunda* bulunan [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) bölümüne bakın.

## <a name="szparsename"></a>CEnumeratorAccessor:: m_szParseName

Veri kaynağı veya Numaralandırıcı için bir bilinen ad almak üzere [IParseDisplayName](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname) 'e geçirilecek dize.

### <a name="syntax"></a>Sözdizimi

```cpp
WCHAR m_szParseName[129];
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *OLE DB Programcının başvurusunda* bulunan [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)