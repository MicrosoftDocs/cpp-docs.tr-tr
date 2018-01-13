---
title: devam et deyimi (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: continue_cpp
dev_langs: C++
helpviewer_keywords: continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e4dd91489bfe22fca875f98110dadcb75def39d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="continue-statement-c"></a>continue Deyimi (C++)
En küçük kapsayan denetleme ifade için Denetim aktarımını zorlar [yapmak](../cpp/do-while-statement-cpp.md), [için](../cpp/for-statement-cpp.md), veya [sırada](../cpp/while-statement-cpp.md) döngü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
continue;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli yinelemeye kalan tüm deyimlerinde yürütülmedi. Sonraki döngü şu şekilde belirlenir:  
  
-   İçinde bir `do` veya `while` döngü, sonraki yinelemeye başlatır kontrol eden bir ifade reevaluating tarafından `do` veya `while` deyimi.  
  
-   İçinde bir `for` döngü (sözdizimini kullanarak `for`(`init-expr`; `cond-expr`; `loop-expr`)), `loop-expr` yan tümcesi gerçekleştirilir. Ardından `cond-expr` yan tümcesi yeniden değerlendirimiş ve sonucuna bağlı olarak, döngü ya da sona veya başka bir yineleme gerçekleşir.  
  
 Aşağıdaki örnekte gösterildiği nasıl `continue` deyimi, kodun bölümlerini atlayıp sonraki yineleme döngüsü başlatmak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
```Output  
before the continue  
before the continue  
before the continue  
after the do loop  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atlama deyimleri](../cpp/jump-statements-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)