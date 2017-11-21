---
title: Statement (C) devam | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: continue
dev_langs: C++
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5d0fc645bdeec7ea9ec6df124279140fcd63f77d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="continue-statement-c"></a>continue Deyimi (C)
`continue` Deyimi en yakın kapsayan, sonraki yinelemeye denetim geçirir `do`, `for`, veya `while` göründüğü, kalan tüm deyimlerinde atlayarak deyimi `do`, `for`, veya `while` deyimi gövdesi.  
  
## <a name="syntax"></a>Sözdizimi  
 `jump-statement`:  
 `continue;`  
  
 Bir sonraki yinelemesini bir `do`, `for`, veya `while` deyimi şu şekilde belirlenir:  
  
-   İçinde bir `do` veya `while` deyimi, sonraki yinelemesini başlattığı bir ifade reevaluating tarafından `do` veya `while` deyimi.  
  
-   A `continue` deyiminde bir `for` deyimi neden döngü bir ifade `for` değerlendirilecek ifade. Ardından derleyici koşullu ifade reevaluates ve, sonuç bağlı olarak ya da sona erer veya deyimi gövde yineler. Bkz: [deyimi için](../c-language/for-statement-c.md) hakkında daha fazla bilgi için `for` deyimi ve onun Terminal dışı.  
  
 Bu bir örnektir `continue` deyimi:  
  
```  
while ( i-- > 0 )   
{  
    x = f( i );  
    if ( x == 1 )  
        continue;  
    y += x * x;  
}  
```  
  
 Bu örnekte, deyimi gövdesi yürütülür sırada `i` 0'dan büyük. İlk `f(i)` atandığı `x`; daha sonra eğer `x` 1'e eşittir `continue` deyimi gerçekleştirilir. Gövde deyimlerinde kalan dikkate alınmaz ve döngü döngünün test değerlendirmesi ile üstündeki yürütme devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [continue deyimi](../cpp/continue-statement-cpp.md)