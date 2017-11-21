---
title: "&lt;Yeni&gt; tür tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: e23ea06002dc840997a0e7202f581cd81ef407c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltnewgt-typedefs"></a>&lt;Yeni&gt; tür tanımları
||  
|-|  
|[new_handler](#new_handler)|  
  
##  <a name="new_handler"></a>new_handler  
 Uygun bir işlev türü noktasına yeni bir işleyici olarak kullanın.  
  
```
typedef void (*new_handler)();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tür bir işleyici işlevi tarafından çağrılır **operatornew** veya `operator new[]` olduğunda bunlar olamaz karşılamak ek depolama alanı için bir istek.  
  
### <a name="example"></a>Örnek  
  Bkz: [set_new_handler](../standard-library/new-functions.md#set_new_handler) kullanarak bir örnek için `new_handler` dönüş değeri olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Yeni >](../standard-library/new.md)



