---
title: "CArrayRowset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
dev_langs:
- C++
helpviewer_keywords:
- CArrayRowset class
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 28d3a28f5c00cb0231738e8f02f07318bf156921
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="carrayrowset-class"></a>CArrayRowset Sınıfı
Array sözdizimini kullanarak bir satır kümesi öğeleri erişir.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Kullanılacak satır istediğiniz erişimci sınıfı türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CArrayRowset](../../data/oledb/carrayrowset-carrayrowset.md)|Oluşturucu.|  
|[Anlık Görüntü](../../data/oledb/carrayrowset-snapshot.md)|Tüm satır belleğe okur.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[Operator &#91; &#93;](../../data/oledb/carrayrowset-operator.md)|Bir öğe kümesi erişir.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[CArrayRowset::m_nRowsRead](../../data/oledb/carrayrowset-m-nrowsread.md)|Satır sayısı zaten okuyun.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset Sınıfı](../../data/oledb/crowset-class.md)