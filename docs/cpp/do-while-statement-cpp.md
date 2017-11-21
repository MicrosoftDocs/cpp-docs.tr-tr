---
title: "yapın-while deyimi (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: do_cpp
dev_langs: C++
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b9ef52e04bd855824e709c66693cb989a18b1283
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="do-while-statement-c"></a>do-while Deyimi (C++)
Yürüten bir *deyimi* belirtilen sonlandırma koşulu kadar sürekli olarak ( *ifade*) sıfır olarak değerlendirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
do  
   statement  
while ( expression ) ;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sonlandırma koşulu test döngünün her yürütme sonrasında yapılan; Bu nedenle, bir `do-while` sonlandırma ifadenin değerine bağlı olarak bir veya birden çok kez döngü yürütür. `do-while` Deyimi de sonlandırmak ne zaman bir [sonu](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), veya [dönmek](../cpp/return-statement-cpp.md) deyimi deyimi gövdesi içinde yürütülür.  
  
 *İfade* aritmetik veya işaretçi türü olmalıdır. Yürütme gibi çalışır:  
  
1.  Deyimi gövdesi yürütülür.  
  
2.  Ardından, *ifade* değerlendirilir. Varsa *ifade* false, `do-while` açıklamayı sonlandıran ve denetim geçirir program sonraki ifadesine. Varsa *ifade* (sıfır), işlem yinelenir, adım 1 ile başlayan doğrudur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek gösterilmektedir `do-while` deyimi:  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yineleme deyimleri](../cpp/iteration-statements-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [while deyimi (C++)](../cpp/while-statement-cpp.md)   
 [for deyimi (C++)](../cpp/for-statement-cpp.md)   
 [Range-based for deyimi (C++)](../cpp/range-based-for-statement-cpp.md)