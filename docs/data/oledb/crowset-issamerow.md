---
title: "CRowset::ıssamerow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset::IsSameRow
- CRowset.IsSameRow
- IsSameRow
- ATL::CRowset::IsSameRow
- ATL.CRowset.IsSameRow
- CRowset<TAccessor>::IsSameRow
- ATL.CRowset<TAccessor>.IsSameRow
- CRowset<TAccessor>.IsSameRow
- ATL::CRowset<TAccessor>::IsSameRow
dev_langs: C++
helpviewer_keywords: IsSameRow method
ms.assetid: 53cba847-52f5-4dd9-973f-bbe7454c425c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a67952947275789fbcb38e8807a2b754cd4baf8a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetissamerow"></a>CRowset::IsSameRow
Geçerli satır belirtilen satır karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT IsSameRow(   
   HROW hRow    
) const throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hRow`  
 [in] Geçerli satır karşılaştırmak için satır için bir tanıtıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`. `S_OK`satırları aynı olduğunu gösterir. Diğer değerleri için bkz: [IRowsetIndentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)