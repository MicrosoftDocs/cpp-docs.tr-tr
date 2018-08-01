---
title: continue deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0ab1e052b3e6d843813c33e5444fc3c08796d00
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402097"
---
# <a name="continue-statement-c"></a>continue Deyimi (C++)
En küçük kapsayan denetleme ifade için Denetim aktarımı zorlar [yapmak](../cpp/do-while-statement-cpp.md), [için](../cpp/for-statement-cpp.md), veya [sırada](../cpp/while-statement-cpp.md) döngü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
continue;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kalan tüm geçerli yineleme deyimlerinde yürütülmedi. Döngünün sonraki yinelemesine şu şekilde belirlenir:  
  
-   İçinde bir **yapmak** veya **sırada** döngü, sonraki yineleme başlatır, denetleme ifadesiyle reevaluating tarafından **yapmak** veya **sırada** deyimi.  
  
-   İçinde bir **için** döngü (söz dizimi kullanılarak `for`(`init-expr`; `cond-expr`; `loop-expr`)), `loop-expr` yan tümcesi yürütülür. Ardından `cond-expr` yan tümcesi yeniden değerlendirimiş ve sonucuna bağlı olarak, döngü ya da sona erer veya başka bir yineleme gerçekleşir.  
  
 Aşağıdaki örnekte gösterildiği nasıl **devam** deyimi, kod bölümlerini atlayabilir ve bir döngünün sonraki yinelemesine başlatmak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Atlama deyimleri](../cpp/jump-statements-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)