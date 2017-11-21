---
title: CRowset::SetData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.SetData
- SetData
- ATL::CRowset::SetData
- CRowset<TAccessor>.SetData
- CRowset::SetData
- ATL.CRowset.SetData
- CRowset.SetData
- CRowset<TAccessor>::SetData
- ATL::CRowset<TAccessor>::SetData
dev_langs: C++
helpviewer_keywords: SetData method
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0daa66111e2b9657218e42d66c9f9b5b9364cd4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetsetdata"></a>CRowset::SetData
Bir veya daha fazla satır sütunu veri değerlerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT SetData( ) const throw( );   
HRESULT SetData(  
   int nAccessor   
) const throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nAccessor`  
 [in] Veri erişim için kullanılacak erişimcisi sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin `SetData` bağımsız değişkenler, tüm erişimciler kabul formu güncelleştirmek için kullanılır. Genellikle çağrısı **SetData** sütunlarında bir satır veri değerlerini ayarlamak için ' ı çağırın [güncelleştirme](../../data/oledb/crowset-update.md) bu değişiklikleri iletmek için.  
  
 Bu yöntem isteğe bağlı bir arabirim gerektirir `IRowsetChange`, hangi desteklenmeyebilir tüm sağlayıcılarının; bu durumda, yöntem **E_NOINTERFACE**. De ayarlamalısınız **DBPROP_IRowsetChange** için `VARIANT_TRUE` çağırmadan önce **açık** tablodaki veya satır kümesi içeren komutu.  
  
 Bir veya daha fazla sütun yoksa yazılabilir ayarlama işlemi başarısız olabilir. Bu sorunu gidermek için imleç haritanızı değiştirin.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)