---
title: no_registry | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_registry
dev_langs: C++
helpviewer_keywords: no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d2b4b34a4ebf266f4ae8062bb2fff0f80060a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="noregistry"></a>no_registry
`no_registry`Tür kitaplıkları ile içeri aktarılan kayıt defteri aramak için değil derleyici söyler `#import`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#import filename no_registry  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Dosya adı*  
 Tür kitaplığı.  
  
## <a name="remarks"></a>Açıklamalar  
 Başvurulan tür kitaplığını INCLUDE dizinlerde bulunmazsa, kayıt defterinde tür kitaplığı olsa bile, derleme başarısız olur.  `no_registry`ile örtük olarak alınan diğer tür kitaplıklarına yayar `auto_search`.  
  
 Derleyici hiçbir zaman dosya adıyla belirtilen ve doğrudan geçirilen tür kitaplıkları için kayıt defterini arayacaktır `#import`.  
  
 Zaman `auto_search` belirtilirse, ek `#import`s ile oluşturulmayacak `no_registry` ilk harfini ayarı `#import` (durumunda ilk `#import` yönergesi edildi `no_registry`, bir `auto_search`- oluşturulan`#import`de `no_registry`.)  
  
 `no_registry`Kayıt defterinde dosyanın daha eski bir sürümü bulma derleyici riski olmadan çapraz başvurulan tür kitaplıklarının almak istiyorsanız kullanışlıdır.  `no_registry`Ayrıca tür kitaplığı kayıtlı değilse faydalı olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)