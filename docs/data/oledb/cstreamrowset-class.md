---
title: CStreamRowset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3365767ed36bcdc45e87f08fb038500fa9ac6d82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100037"
---
# <a name="cstreamrowset-class"></a>CStreamRowset Sınıfı
Kullanılan bir `CCommand` veya `CTable` bildirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Bir erişimci sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|Oluşturucu. Oluşturur ve başlatır `CStreamRowset` nesnesi.|  
|[Kapat](../../data/oledb/cstreamrowset-close.md)|Sürümler [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) sınıfında arabirim işaretçisi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CStreamRowset` içinde `CCommand` veya `CTable` bildirimi, örneğin:  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
 veya  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` döndüren bir `ISequentialStream` depolanan işaretçi `m_spStream`. Daha sonra **okuma** XML biçiminde (UNICODE dizesi) verileri almak üzere yöntemi. Örneğin:  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 XML biçimlendirme gerçekleştirir ve tüm sütunları ve satır kümesinin bir XML dizesi olarak tüm satırları döndürür.  
  
> [!NOTE]
>  Bu özellik yalnızca SQL Server 2000 ile çalışır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)