---
title: CCommand::GetNextResult | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
dev_langs: C++
helpviewer_keywords: GetNextResult method
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a0b4c03d7aa31949752e4362380d1705d7db6e9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccommandgetnextresult"></a>CCommand::GetNextResult
Sonraki sonuç varsa kümesi getirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
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
 [CCommand sınıfı](../../data/oledb/ccommand-class.md)