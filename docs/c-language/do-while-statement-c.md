---
title: "yapın-while Statement (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- do
- while
dev_langs:
- C++
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 26a7cef5e023c0fb0d5e24fe68fed6b33bc8ae75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="do-while-statement-c"></a>do-while Deyimi (C)
`do-while` Deyimi bir deyim veya bileşik deyim belirtilen ifadeye false olana kadar yineleyin olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
 *Yineleme deyimi*:  
 **yapmak***deyimi***sırada (***ifade***);**   
  
 *İfade* içinde bir `do-while` döngünün gövdesi yürütüldükten sonra deyimi değerlendirilir. Bu nedenle, döngünün gövdesi her zaman en az bir kez çalıştırılır.  
  
 *İfade* aritmetik veya işaretçi türü olmalıdır. Yürütme gibi çalışır:  
  
1.  Deyimi gövdesi yürütülür.  
  
2.  Ardından, *ifade* değerlendirilir. Varsa *ifade* false, `do-while` açıklamayı sonlandıran ve denetim geçirir program sonraki ifadesine. Varsa *ifade* (sıfır), işlem yinelenir, adım 1 ile başlayan doğrudur.  
  
 `do-while` Deyimi de sonlandırmak ne zaman bir **sonu**, `goto`, veya `return` deyimi deyimi gövdesi içinde yürütülür.  
  
 Bu bir örnektir `do-while` deyimi:  
  
```  
do   
{  
    y = f( x );  
    x--;  
} while ( x > 0 );  
```  
  
 Bu `do-while` deyimi, iki deyimleri `y = f( x );` ve `x--;` bağımsız olarak ilk değeri yürütülür `x`. Ardından `x > 0` değerlendirilir. Varsa `x` 0'dan büyük deyimi gövdesi yeniden yürütülür ve `x > 0` değerlendirilir. Deyimi gövde sürekli yürütüldüğünde sürece `x` 0'dan büyük kalır. Yürütülmesi `do-while` açıklamayı sonlandıran `x` 0 veya eksi olur. Döngünün gövdesi en az bir kez çalıştırılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [do-while Deyimi (C++)](../cpp/do-while-statement-cpp.md)