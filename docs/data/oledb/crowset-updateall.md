---
title: CRowset::UpdateAll | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset::UpdateAll
- ATL.CRowset.UpdateAll
- CRowset<TAccessor>.UpdateAll
- ATL.CRowset<TAccessor>.UpdateAll
- UpdateAll
- CRowset.UpdateAll
- ATL::CRowset<TAccessor>::UpdateAll
- CRowset<TAccessor>::UpdateAll
- ATL::CRowset::UpdateAll
dev_langs:
- C++
helpviewer_keywords:
- UpdateAll method
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f7dc38544641043f95d24cf9a8f9cf40ccca1dbf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetupdateall"></a>CRowset::UpdateAll
Bekleyen tüm satırları itibaren son fetch yapılan değişiklikler iletir veya **güncelleştirme** üzerinde çağırın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT UpdateAll(DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pcRows`  
 [out] Konuma bir işaretçi nerede `UpdateAll` onu çalıştı güncelleştirmek için gerekirse satır sayısını döndürür.  
  
 `pphRow`  
 [out] Hangi bellekte bir işaretçi `UpdateAll` çalıştı güncelleştirmek için satır işleyicisini döndürür. Hiçbir tanıtıcı döndürülür `pphRow` null.  
  
 `ppStatus`  
 [out] Konuma bir işaretçi nerede **güncelleştirme** satır durum değeri döndürür. Durum yok döndürülür `ppStatus` null.  
  
## <a name="remarks"></a>Açıklamalar  
 Bekleyen tüm satırları son getirildi veya kullanarak güncelleştirilmiş beri tüm satırları yapılan değişiklikleri iletir [güncelleştirme](../../data/oledb/crowset-update.md) veya `UpdateAll`. `UpdateAll` hala tanıtıcı kendileri için olmasına bakılmaksızın değiştirilmiş her satır güncelleştirmek (bkz: `pphRow`) veya değil.  
  
 Örneğin, kullandığınız **Ekle** bir satır kümesinde beş satır eklemek için her iki çağrı verebilir **güncelleştirme** beş kez veya çağrı `UpdateAll` tümünü güncelleştirmek için bir kez.  
  
 Bu yöntem isteğe bağlı bir arabirim gerektirir `IRowsetUpdate`, hangi desteklenmeyebilir tüm sağlayıcılarının; bu durumda, yöntem **E_NOINTERFACE**. De ayarlamalısınız **DBPROP_IRowsetUpdate hatalı** için `VARIANT_TRUE` çağırmadan önce **açık** tablodaki veya satır kümesi içeren komutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)