---
title: CRowset::MovePrev | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>.MovePrev
- CRowset.MovePrev
- MovePrev
- CRowset::MovePrev
- ATL.CRowset.MovePrev
- ATL::CRowset<TAccessor>::MovePrev
- ATL::CRowset::MovePrev
- ATL.CRowset<TAccessor>.MovePrev
- CRowset<TAccessor>::MovePrev
dev_langs:
- C++
helpviewer_keywords:
- MovePrev method
ms.assetid: 7ced2bfb-f556-40fc-97ea-0d4e7213e114
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b86a5266faefaacb0df940f51985f1d31dd006b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097152"
---
# <a name="crowsetmoveprev"></a>CRowset::MovePrev
İmleci önceki kayda taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT MovePrev() throw();  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem ya da ayarlamanızı gerektirir **DBPROP_CANFETCHBACKWARDS** veya **DBPROP_CANSCROLLBACKWARDS** için `VARIANT_TRUE` çağırmadan önce **açık** tablo üzerinde veya satır kümesi içeren komutu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)