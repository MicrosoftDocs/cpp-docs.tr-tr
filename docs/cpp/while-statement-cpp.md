---
title: while deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f281007bea3f23bc8e7cebcdd68b9a306b500e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="while-statement-c"></a>while Deyimi (C++)
Yürütür *deyimi* kadar sürekli olarak *ifade* sıfır olarak değerlendirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      while ( expression )  
   statement  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Test *ifade* ; döngünün her yürütmeden önce gerçekleşmesi bu nedenle, bir `while` sıfır veya daha fazla kez döngü yürütür. *ifade* tamsayı türü, bir işaretçi türü ya da bir sınıf bir integral anlaşılır bir dönüştürme türünde veya işaretçi türü olmalıdır.  
  
 A `while` döngü de sonlandırmak ne zaman bir [sonu](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), veya [dönmek](../cpp/return-statement-cpp.md) deyimi içinde gövdesi yürütülür. Kullanım [devam](../cpp/continue-statement-cpp.md) çıkmadan geçerli yinelemeye sonlandırmak için `while` döngü. **Devam** sonraki yinelemesini denetim geçirir `while` döngü.  
  
 Aşağıdaki kod, bir dizeden sona eklenen alt çizgileri kesmek için bir `while` döngüsü kullanır:  
  
```  
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 Sonlandırma koşulu, döngünün en üstünde değerlendirilir. Hiçbir alt çizgi yoksa, döngü asla yürütülmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yineleme deyimleri](../cpp/iteration-statements-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [yapın-while deyimi (C++)](../cpp/do-while-statement-cpp.md)   
 [for deyimi (C++)](../cpp/for-statement-cpp.md)   
 [Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)