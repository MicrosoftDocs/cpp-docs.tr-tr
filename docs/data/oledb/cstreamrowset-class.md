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
ms.openlocfilehash: ad4987422fd200faef141150908d4df0722f669a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366270"
---
# <a name="cstreamrowset-class"></a>CStreamRowset Sınıfı

Bir `CCommand` veya `CTable` beyannamede kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Erişimci sınıf.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Cstreamrowset](#cstreamrowset)|Oluşturucu. Nesneyi anında laştırır ve `CStreamRowset` başharfe alar.|
|[Kapat](#close)|Sınıftaki [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) arabirim işaretçisini serbest bırakır.|

## <a name="remarks"></a>Açıklamalar

Örneğin, `CCommand` beyannamenizde veya `CTable` bildiriminizde kullanın: `CStreamRowset`

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

or

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute`' `ISequentialStream` de `m_spStream`depolanan bir işaretçi döndürür Daha sonra `Read` (Unicode dize) verileri XML biçiminde almak için yöntemi kullanın. Örneğin:

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000, XML biçimlendirmesini gerçekleştirir ve satır kümesinin tüm sütunlarını ve tüm satırlarını tek bir XML dizesi olarak döndürür.

> [!NOTE]
> Bu özellik yalnızca SQL Server 2000 ile çalışır.

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a>CStreamRowset::CStreamRowset

Nesneyi anında laştırır ve `CStreamRowset` başharfe alar.

### <a name="syntax"></a>Sözdizimi

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a>CStreamRowset::Kapat

Sınıftaki [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) arabirim işaretçisini serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
