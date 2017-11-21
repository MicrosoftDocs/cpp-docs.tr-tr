---
title: CRowset::Update | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Update
- ATL.CRowset.Update
- ATL.CRowset<TAccessor>.Update
- ATL::CRowset<TAccessor>::Update
- CRowset<TAccessor>::Update
- CRowset::Update
- CRowset<TAccessor>.Update
- ATL::CRowset::Update
dev_langs: C++
helpviewer_keywords: Update method
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17541ea324fa7d6c314501f1e09519881a1fff7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetupdate"></a>CRowset::Update
Bekleyen tüm geçerli satırda son fetch itibaren yaptığınız değişiklikleri iletir veya **güncelleştirme** üzerinde çağırın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT Update(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pcRows`  
 [out] Konuma bir işaretçi nerede **güncelleştirme** onu çalıştı güncelleştirmek için gerekirse satır sayısını döndürür.  
  
 `phRow`  
 [out] Konuma bir işaretçi nerede **güncelleştirme** çalıştı güncelleştirmek için satır işleyicisini döndürür. Hiçbir tanıtıcı döndürülür `phRow` null.  
  
 `pStatus`  
 [out] Konuma bir işaretçi nerede **güncelleştirme** satır durum değeri döndürür. Durum yok döndürülür `pStatus` null.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bekleyen tüm değişiklikleri satır son getirilen veya güncelleştirilmiş geçerli satır yaptığından aktarır (kullanarak **güncelleştirme** veya [UpdateAll](../../data/oledb/crowset-updateall.md)). Genellikle çağrısı [SetData](../../data/oledb/crowset-setdata.md) sütunlarında bir satır veri değerleri ayarlayın ve ardından çağırmak için **güncelleştirme** bu değişiklikleri iletmek için.  
  
 Bu yöntem isteğe bağlı bir arabirim gerektirir `IRowsetUpdate`, hangi desteklenmeyebilir tüm sağlayıcılarının; bu durumda, yöntem **E_NOINTERFACE**. De ayarlamalısınız **DBPROP_IRowsetUpdate hatalı** için `VARIANT_TRUE` çağırmadan önce **açık** tablodaki veya satır kümesi içeren komutu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)