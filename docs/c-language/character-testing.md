---
title: Karakter test etme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89f48346d9b96c7de20c11fd4cbcde106571ed57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="character-testing"></a>Karakter Test Etme
**ANSI 4.3.1** tarafından karakter kümesi test için `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint`, ve `isupper` işlevleri  
  
 Aşağıdaki listede, Microsoft C derleyicisi tarafından uygulanan bu işlevler açıklanmaktadır.  
  
|İşlev|Şunlara yönelik testler|  
|--------------|---------------|  
|`isalnum`|Karakter 0 - 48 57, 65-90, 97 122 9, A-Z, a-z ASCII|  
|`isalpha`|Karakter A-Z, a-z ASCII 65-90, 97 122|  
|`iscntrl`|ASCII 0-31, 127|  
|`islower`|Karakter a-z ASCII 97-122|  
|`isprint`|Karakter A-Z, a-z, 0 - 9 Noktalama, ASCII 32-126 boşluk|  
|`isupper`|A-Z 65-90 ASCII karakterleri|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık işlevleri](../c-language/library-functions.md)