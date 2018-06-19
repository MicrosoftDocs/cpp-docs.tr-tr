---
title: Statement (C) devam | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue
dev_langs:
- C++
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f474d24bd6057165a50cc6edaca5db5462f6459
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383556"
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
 [continue Deyimi](../cpp/continue-statement-cpp.md)