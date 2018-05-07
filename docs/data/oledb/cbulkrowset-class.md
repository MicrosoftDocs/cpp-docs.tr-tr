---
title: CBulkRowset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
dev_langs:
- C++
helpviewer_keywords:
- CBulkRowset class
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7dddf645b8795b12f6da70081327366b62946303
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cbulkrowset-class"></a>CBulkRowset Sınıfı
Getirir ve tek bir çağrı ile birden çok satır işleyicilerini alarak, toplu veriler üzerinde çalışmaya satırları yönetir.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Bir erişimci sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|Başvuru sayısını artırır.|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|Oluşturucu.|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|Gerekirse, yeni bir toplu getirme gerçekleştirme verilerin ilk satırını alır.|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|Son satır taşır.|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|Sonraki satıra veri alır.|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|Önceki satıra geçer.|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|Yer işareti tarafından işaretlenen satırı veya belirtilen kayma satırındaki bu yer işaretinin getirir.|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|Satır satır kümesindeki bir kesir konumundan başlayarak getirir.|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|Geçerli satırda ayarlar (**m_nCurrentRow**) sıfır ve sürümler için tüm satırlar.|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|Bir çağrı tarafından alınmasına izin satır işleyicilerini sayısını ayarlar.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren `CBulkRowset` sınıfı.  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)