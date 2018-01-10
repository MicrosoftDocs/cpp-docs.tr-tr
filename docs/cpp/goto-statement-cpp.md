---
title: goto deyimi (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: goto_cpp
dev_langs: C++
helpviewer_keywords: goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a002071bdb4e271df525b138647b0544cfe9f3c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="goto-statement-c"></a>goto Deyimi (C++)
`goto` Deyimi koşulsuz olarak aktarır denetimi tarafından belirtilen tanımlayıcı Etiketli ifade.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Etiketli deyim tarafından belirlenen `identifier` içinde geçerli bir işlev olmalıdır. Tüm `identifier` adları bir iç ad alanı üyesi olan ve bu nedenle diğer tanımlayıcıları ile engel olmaz.  
  
 Yalnızca anlamlı deyimi etiketidir bir `goto` deyimi; Aksi takdirde deyimi etiketleri göz ardı edilir. Etiketleri yeniden bildirilen olamaz.  
  
 Kullanmak için stil programlama iyi `break`, `continue`, ve `return` deyimleri yerine `goto` deyimi mümkün olduğunda. Ancak, çünkü `break` deyimi yalnızca tek bir döngü düzeyden çıkar, kullanmanız gerekebilir bir `goto` deyimi iç içe bir döngüden çıkın.  
  
 Etiketler hakkında daha fazla bilgi ve `goto` deyimi, bkz: [etiketli deyimleri](../cpp/labeled-statements.md) ve [goto deyimi kullanarak etiketlerle](http://msdn.microsoft.com/en-us/6cd7c31a-9822-4241-8566-f79f51be48fe).  
  
## <a name="example"></a>Örnek  
 Bu örnekte, bir `goto` deyimi denetim etiketli noktasına aktarır `stop` zaman `i` 3'e eşittir.  
  
```  
// goto_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 2; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 3 )  
                goto stop;  
        }  
    }  
  
    // This message does not print:   
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop:   
    printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
```Output  
Outer loop executing. i = 0  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 1  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 2  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 3  
 Inner loop executing. j = 0  
Jumped to stop. i = 3  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atlama deyimleri](../cpp/jump-statements-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)