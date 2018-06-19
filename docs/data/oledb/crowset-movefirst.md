---
title: CRowset::MoveFirst | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>::MoveFirst
- ATL::CRowset::MoveFirst
- CRowset<TAccessor>.MoveFirst
- CRowset::MoveFirst
- CRowset.MoveFirst
- ATL.CRowset.MoveFirst
- ATL.CRowset<TAccessor>.MoveFirst
- ATL::CRowset<TAccessor>::MoveFirst
dev_langs:
- C++
helpviewer_keywords:
- MoveFirst method
ms.assetid: a17c0799-ead9-4d85-9a1d-8b17188d01e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 811e2cdc18711c85cbb2a43e555a273bf3f50d81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091790"
---
# <a name="crowsetmovefirst"></a>CRowset::MoveFirst
İmleci ilk konuma taşır ve ilk satır alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT MoveFirst() throw();  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrıları [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) sonraki getirme konumunu ilk konumuna (satır kümesi oluşturduğunuzda, sonraki getirme konumunu konumu) yeniden konumlandırmak için ve ilk satır alır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)