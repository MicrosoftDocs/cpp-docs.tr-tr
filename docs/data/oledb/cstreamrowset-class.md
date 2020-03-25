---
title: CStreamRowset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
ms.openlocfilehash: 300933fd6d10f5da39d9276db746ab789851a9a1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211178"
---
# <a name="cstreamrowset-class"></a>CStreamRowset Sınıfı

`CCommand` veya `CTable` bildiriminde kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Erişimci sınıfı.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CStreamRowset](#cstreamrowset)|Oluşturucu. `CStreamRowset` nesnesini başlatır ve başlatır.|
|[~Eksik](#close)|Sınıfında [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) arabirim işaretçisini yayınlar.|

## <a name="remarks"></a>Açıklamalar

`CCommand` veya `CTable` bildiriminde `CStreamRowset` kullanın, örneğin:

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

veya

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute`, `m_spStream`depolanan `ISequentialStream` bir işaretçi döndürür. Daha sonra, (Unicode dize) verilerini XML biçiminde almak için `Read` yöntemini kullanırsınız. Örneğin:

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000, XML biçimlendirmesini gerçekleştirir ve tüm sütunları ve satır kümesinin tüm satırlarını tek bir XML dizesi olarak döndürür.

> [!NOTE]
>  Bu özellik yalnızca SQL Server 2000 ile birlikte kullanılabilir.

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a>CStreamRowset:: CStreamRowset

`CStreamRowset` nesnesini başlatır ve başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a>CStreamRowset:: Close

Sınıfında [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) arabirim işaretçisini yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
