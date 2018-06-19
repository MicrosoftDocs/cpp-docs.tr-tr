---
title: İfade Statement (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18d28cdc695ae600616d63575328eeaf171bc28c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385903"
---
# <a name="expression-statement-c"></a>İfade Deyimi (C)
İfade deyimi yürütüldüğünde, ifade özetlenen kurallarına göre değerlendirilir [ifadeler ve atamalar](../c-language/expressions-and-assignments.md).  
  
## <a name="syntax"></a>Sözdizimi  
 *ifade deyimi*:  
 *ifade* kabul **;**  
  
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
 [Deyimler](../c-language/statements-c.md)