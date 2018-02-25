---
title: CCommand::GetNextResult | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
dev_langs:
- C++
helpviewer_keywords:
- GetNextResult method
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa77785373545b2c4efd2faef0a8c0a02ee26910
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ccommandgetnextresult"></a>CCommand::GetNextResult
Sonraki sonuç varsa kümesi getirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,  
   bool bBind = true) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pulRowsAffected*  
 [Giriş/Çıkış] Burada bir komut tarafından etkilenen satırların sayımını döndürülen bellek için bir işaretçi.  
  
 `bBind`  
 [in] Yürütülen sonra komutu otomatik olarak bağlamak belirtir. Varsayılan değer **doğru**, otomatik olarak bağlanacak komutu neden olur. Ayarı `bBind` için **false** böylece el ile bağlayabilirsiniz komutu otomatik bağlama engeller. (El ile bağlama belirli OLAP kullanıcılara ilgilendirir.)  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sonuç kümesi daha önce getirilen varsa, bu işlev önceki sonuç kümesini serbest bırakır ve sütunları bağlantısını keser. Varsa `bBind` olan **doğru**, yeni sütun bağlar.  
  
 Ayarlayarak birden çok sonuç yalnızca belirttiyseniz, bu işlev çağırmalıdır `CCommand` şablon parametresi *TMultiple*=`CMultipleResults`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCommand Sınıfı](../../data/oledb/ccommand-class.md)