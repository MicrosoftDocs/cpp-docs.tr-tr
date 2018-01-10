---
title: CSimpleRow::Compare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87ee21022aa379820ced0463892be12ee0676d88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
Aynı satır örneğine bakın görmek için iki satır karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRow`  
 Bir işaretçi bir `CSimpleRow` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `HRESULT` değeri, genellikle `S_OK`, iki satır aynı satır örneğini belirterek veya **S_FALSE**, iki satır belirten farklıdır. Bkz: [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) içinde *OLE DB Programcının Başvurusu* diğer olası dönüş değerleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSimpleRow sınıfı](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)