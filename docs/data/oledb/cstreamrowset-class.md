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
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e0aad7fe25205d4cf31cbe76db3f1fb441858858
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233405"
---
# <a name="cstreamrowset-class"></a>CStreamRowset Sınıfı
Kullanılan bir `CCommand` veya `CTable` bildirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
### <a name="parameters"></a>Parametreler  
 *TAccessor*  
 Bir erişimci sınıfı.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CStreamRowset](#cstreamrowset)|Oluşturucu. Oluşturur ve başlatır `CStreamRowset` nesne.|  
|[Kapat](#close)|Yayınları [ISequentialStream](https://msdn.microsoft.com/library/ms718035.aspx) sınıfında arabirim işaretçisi.|  
  
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
Yayınları [ISequentialStream](https://msdn.microsoft.com/library/ms718035.aspx) sınıfında arabirim işaretçisi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
void Close();  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)