---
title: CRowset::MoveNext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>.MoveNext
- ATL.CRowset.MoveNext
- ATL::CRowset<TAccessor>::MoveNext
- CRowset<TAccessor>.MoveNext
- CRowset.MoveNext
- CRowset<TAccessor>::MoveNext
- CRowset::MoveNext
- ATL::CRowset::MoveNext
dev_langs:
- C++
helpviewer_keywords:
- MoveNext method
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6c56e3dc53699f47c9dc1061120a201ef5698c04
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098227"
---
# <a name="crowsetmovenext"></a>CRowset::MoveNext
İmleci sonraki kayda taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT MoveNext() throw();HRESULT MoveNext(LONG lSkip,   
   bool bForward= true) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lSkip`  
 [in] Getirme önce atlanacak satırların sayısı.  
  
 `bForward`  
 [in] Geçirmek **true** sonraki kayda ilerlemek için **false** geri gitmek için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`. Satır sonu erişildiğinde döndürür **DB_S_ENDOFROWSET**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sonraki sıralı satırdaki getirir `CRowset` önceki konumdan hatırlamak nesnesi. İsteğe bağlı olarak, İleri atlayabilirsiniz seçebileceğiniz `lSkip` satırları veya geriye dönük taşıyın.  
  
 Bu yöntemi çağırmadan önce aşağıdaki özellikler kümesi gerektirir **açık** tablodaki veya satır kümesi içeren komutu:  
  
-   **DBPROP_CANSCROLLBACKWARDS** olmalıdır `VARIANT_TRUE` varsa `lSkip` < 0  
  
-   **DBPROP_CANFETCHBACKWARDS** olmalıdır `VARIANT_TRUE` varsa `bForward` = false  
  
 Aksi takdirde (varsa `lSkip` > = 0 ve `bForward` = true), ek özellikleri ayarlayın gerekmez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)