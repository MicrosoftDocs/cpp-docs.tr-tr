---
title: "&lt;Yeni&gt; tür tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: cbcc542095ad8b75bbe632f741f43206e436b5e4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltnewgt-typedefs"></a>&lt;Yeni&gt; tür tanımları
||  
|-|  
|[new_handler](#new_handler)|  
  
##  <a name="new_handler"></a>  new_handler  
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



