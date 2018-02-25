---
title: END_ACCESSOR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- END_ACCESSOR
dev_langs:
- C++
helpviewer_keywords:
- END_ACCESSOR macro
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2907823c09c481c648c648d86df676fc5c435955
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="endaccessor"></a>END_ACCESSOR
Erişimci girdinin sonuna işaretler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
END_ACCESSOR()  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üzerinde bir satır kümesinde çoklu erişimci için belirtmeniz gerekir. `BEGIN_ACCESSOR_MAP` ve `BEGIN_ACCESSOR` makrosu tek tek her erişimcisi için. `BEGIN_ACCESSOR` Makrosu ile tamamlandı `END_ACCESSOR` makrosu. `BEGIN_ACCESSOR_MAP` Makrosu ile tamamlandı `END_ACCESSOR_MAP` makrosu.  
  
## <a name="example"></a>Örnek  
 Bkz: [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)