---
title: CRowset::MoveToRatio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MoveToRatio
- CRowset<TAccessor>::MoveToRatio
- CRowset::MoveToRatio
- CRowset<TAccessor>.MoveToRatio
- ATL.CRowset.MoveToRatio
- ATL::CRowset::MoveToRatio
- CRowset.MoveToRatio
- ATL.CRowset<TAccessor>.MoveToRatio
- ATL::CRowset<TAccessor>::MoveToRatio
dev_langs: C++
helpviewer_keywords: MoveToRatio method
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bc5c5a46eabd6b308a8b91fba8f7844950d55985
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetmovetoratio"></a>CRowset::MoveToRatio
Satır satır kümesindeki bir kesir konumundan başlayarak getirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT MoveToRatio(   
   DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,   
   bool bForward = true    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nNumerator`  
 [in] Kesirli belirlemek için kullanılan pay konumsal içinden veri getirilemiyor.  
  
 `nDenominator`  
 [in] Kesirli belirlemek için kullanılan payda konumsal içinden veri getirilemiyor.  
  
 `bForward`  
 [in] İleriye veya geriye doğru hareket gösterir. İleri varsayılandır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 `MoveToRatio`kabaca aşağıdaki formüle göre satırları getirir:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 Burada `RowsetSize` satır ölçülen satır boyutu. Bu formülü doğruluğunu belirli sağlayıcısına bağlıdır. Ayrıntılar için bkz [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx).  
  
 Bu yöntem isteğe bağlı bir arabirim gerektirir `IRowsetScroll`, hangi desteklenmeyebilir tüm sağlayıcılarının; bu durumda, yöntem **E_NOINTERFACE**. De ayarlamalısınız **DBPROP_IRowsetScroll** için `VARIANT_TRUE` çağırmadan önce **açık** tablodaki veya satır kümesi içeren komutu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)