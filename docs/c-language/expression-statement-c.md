---
title: "İfade Statement (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7438899eb9c1c2f17b4e74c859d454e2b69af600
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-statement-c"></a>İfade Deyimi (C)
İfade deyimi yürütüldüğünde, ifade özetlenen kurallarına göre değerlendirilir [ifadeler ve atamalar](../c-language/expressions-and-assignments.md).  
  
## <a name="syntax"></a>Sözdizimi  
 *ifade deyimi*:  
 *ifade* kabul**;**  
  
 İfade değerlendirmesinden gelen tüm yan etkiler, sonraki deyim yürütülmeden önce tamamlanır. Boş ifade deyimine null deyim denir. Bkz: [Null deyimi](../c-language/null-statement-c.md) daha fazla bilgi için.  
  
 Bu örnekler, ifade deyimlerini gösterir.  
  
```  
x = ( y + 3 );            /* x is assigned the value of y + 3  */  
x++;                      /* x is incremented                  */  
x = y = 0;                /* Both x and y are initialized to 0 */  
proc( arg1, arg2 );       /* Function call returning void      */  
y = z = ( f( x ) + 3 );   /* A function-call expression        */  
```  
  
 Son deyim olan işlev çağrısı ifadesinde, işlev tarafından döndürülen tüm değerleri içeren ifade değeri 3 artırılır ve ardından hem `y` hem de `z` değişkenine atanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimleri](../c-language/statements-c.md)