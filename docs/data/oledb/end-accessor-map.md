---
title: END_ACCESSOR_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- END_ACCESSOR_MAP
dev_langs:
- C++
helpviewer_keywords:
- END_ACCESSOR_MAP macro
ms.assetid: ede813c7-46c9-48a6-aa1a-8ebf38e92023
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 139fcf788449a8cd1d23e2aa85691f8d0e8c3da7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="endaccessormap"></a>END_ACCESSOR_MAP
Erişimci eşleme girdilerini sonunu işaretler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
END_ACCESSOR_MAP()  
  
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