---
title: no_registry | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_registry
dev_langs:
- C++
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105c2b0ee4d2648a1cc43d0baca9f30146184e78
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42466054"
---
# <a name="noregistry"></a>no_registry
**no_registry** derleyiciye tür kitaplıklarını içeri için kayıt defterini aranmayacak `#import`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#import filename no_registry  
```  
  
### <a name="parameters"></a>Parametreler  
*Dosya adı*  
Bir tür kitaplığı.  
  
## <a name="remarks"></a>Açıklamalar  
 
Başvurulan tür kitaplığının dizinleri bulunmazsa, tür kitaplığının kayıt defterinde olsa bile, derleme başarısız olur.  **no_registry** için örtük olarak içeri diğer tür kitaplıklarında yayar `auto_search`.  
  
Derleyici, hiçbir zaman doğrudan geçirilen ve dosya adıyla belirtilen tür kitaplıkları için kayıt defterini arar `#import`.  
  
Zaman `auto_search` belirtilirse, ek `#import`s ile oluşturulacak **no_registry** ilk harfini ayarlama `#import` (durumunda ilk `#import` yönergesi olduğu **no_registry** e `auto_search`-oluşturulan `#import` de **no_registry**.)  
  
**no_registry** çapraz başvurulan tür kitaplıkları dosyanın daha eski bir sürümünü kayıt defterinde bulma derleyici riski olmadan içeri aktarmak istediğiniz durumlarda kullanışlıdır. **no_registry** tür kitaplığı kayıtlı değil de kullanışlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)