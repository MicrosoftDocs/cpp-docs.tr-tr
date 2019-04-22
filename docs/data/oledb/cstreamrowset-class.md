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
- CStreamRowset
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
ms.openlocfilehash: b566ddab89d2198e3f6b24eb9a20c60747749d1a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022586"
---
# <a name="cstreamrowset-class"></a>CStreamRowset Sınıfı

Kullanılan bir `CCommand` veya `CTable` bildirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Bir erişimci sınıfı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CStreamRowset](#cstreamrowset)|Oluşturucu. Oluşturur ve başlatır `CStreamRowset` nesne.|
|[Kapat](#close)|Yayınları [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) sınıfında arabirim işaretçisi.|

## <a name="remarks"></a>Açıklamalar

Kullanım `CStreamRowset` içinde `CCommand` veya `CTable` bildirimi, örneğin:

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

veya

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute` döndürür bir `ISequentialStream` depolanan işaretçi `m_spStream`. Daha sonra `Read` XML biçiminde (Unicode dize) veri almak için yöntemi. Örneğin:

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000 XML biçimlendirme gerçekleştirir ve tüm sütun ve satır kümesinin bir XML dizesi olarak tüm satırları döndürür.

> [!NOTE]
>  Bu özellik yalnızca SQL Server 2000 ile çalışır.

## <a name="cstreamrowset"></a> CStreamRowset::CStreamRowset

Oluşturur ve başlatır `CStreamRowset` nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
CStreamRowset();
```

## <a name="close"></a> CStreamRowset::Close

Yayınları [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) sınıfında arabirim işaretçisi.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)