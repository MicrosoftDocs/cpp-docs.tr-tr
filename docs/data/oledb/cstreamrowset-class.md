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
ms.openlocfilehash: 304dfe0e026a9fbba899c1ef17c06cf1baf1529b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841057"
---
# <a name="cstreamrowset-class"></a>CStreamRowset Sınıfı

Bir `CCommand` veya bildiriminde kullanılır `CTable` .

## <a name="syntax"></a>Söz dizimi

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

| Ad | Açıklama |
|-|-|
|[CStreamRowset](#cstreamrowset)|Oluşturucu. Nesneyi örnekleyen ve başlatır `CStreamRowset` .|
|[Kapat](#close)|Sınıfında [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) arabirim işaretçisini yayınlar.|

## <a name="remarks"></a>Açıklamalar

`CStreamRowset` `CCommand` Veya `CTable` bildiriminde kullanın, örneğin:

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

veya

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute``ISequentialStream`içinde depolanan bir işaretçi döndürür `m_spStream` . Daha sonra, `Read` (Unicode dize) VERILERINI XML biçiminde almak için yöntemini kullanabilirsiniz. Örnek:

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000, XML biçimlendirmesini gerçekleştirir ve tüm sütunları ve satır kümesinin tüm satırlarını tek bir XML dizesi olarak döndürür.

> [!NOTE]
> Bu özellik yalnızca SQL Server 2000 ile birlikte kullanılabilir.

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a> CStreamRowset:: CStreamRowset

Nesneyi örnekleyen ve başlatır `CStreamRowset` .

### <a name="syntax"></a>Syntax

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a> CStreamRowset:: Close

Sınıfında [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) arabirim işaretçisini yayınlar.

### <a name="syntax"></a>Syntax

```cpp
void Close();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
