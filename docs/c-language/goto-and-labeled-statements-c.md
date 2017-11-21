---
title: goto ve Labeled Statements (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: goto
dev_langs: C++
helpviewer_keywords:
- labeled statement
- statements, labeled
- goto keyword [C]
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ab5bfa5b145f698b1c93c4a494802cd63bbcfb04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="goto-and-labeled-statements-c"></a>goto ve Etiketli Deyimleri (C)
`goto` Deyimi bir etiket denetimi aktarır. Belirtilen etiket aynı işlevde bulunmalıdır ve aynı işlevde yalnızca bir deyim önce görünebilir.  
  
## <a name="syntax"></a>Sözdizimi  
 *deyimi*:  
 *Etiketli deyim*  
  
 *atlama deyimi*  
  
 *atlama deyimi*:  
 **goto***tanımlayıcısı***;**   
  
 *Etiketli deyim*:  
 *tanımlayıcı***:***deyimi*   
  
 Yalnızca anlamlı deyimi etiketidir bir `goto` deyimi; diğer herhangi bir bağlam içinde etiketli deyim dikkate almaksızın etiket yürütülür.  
  
 A *atlama deyimi* aynı işlevde bulunmalıdır ve aynı işlevde yalnızca bir deyim önce görünebilir. Kümesini *tanımlayıcısı* adları aşağıdaki bir `goto` adları ile diğer tanımlayıcıları karışmaması için kendi ad alanı vardır. Etiketleri yeniden bildirilen olamaz. Bkz: [ad alanları](../c-language/name-spaces.md) daha fazla bilgi için.  
  
 Kullanmak için stil programlama iyi **sonu**, **devam**, ve `return` preference için deyimi `goto` mümkün olduğunda. Bu yana **sonu** deyimi yalnızca bir döngü düzeyden çıkar bir `goto` iç içe bir döngü içinde bir döngüden çıkma için gerekli olabilir.  
  
 Bu örnekte gösterilmiştir `goto` deyimi:  
  
```  
// goto.c  
#include <stdio.h>  
  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 3; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 5 )  
                goto stop;  
        }  
    }  
  
    /* This message does not print: */  
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop: printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
 Bu örnekte, bir `goto` deyimi denetim etiketli noktasına aktarır `stop` zaman `i` 5'e eşittir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimleri](../c-language/statements-c.md)