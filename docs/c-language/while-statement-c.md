---
title: while Statement (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: while
dev_langs: C++
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5f8157d4006d3f2a53e2f32a87d8923baf73628f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="while-statement-c"></a>while Deyimi (C)
`while` Deyimi bir deyim belirtilen ifadeye false olana kadar yineleyin olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
 *Yineleme deyimi*:  
 **sırada (***ifade***)***deyimi*   
  
 *İfade* aritmetik veya işaretçi türü olmalıdır. Yürütme gibi çalışır:  
  
1.  *İfade* değerlendirilir.  
  
2.  Varsa *ifade* başlangıçta yanlış gövdesini `while` deyimi hiçbir zaman yürütülür ve denetim geçirir `while` program sonraki ifadesine deyimi.  
  
     Varsa *ifade* (sıfır) true, deyim gövdesi yürütülür ve adım 1'den itibaren işlem tekrarlanır.  
  
 `while` Deyimi de sonlandırmak ne zaman bir **sonu**, `goto`, veya `return` deyimi içinde gövdesi yürütülür. Kullanım **devam** çıkmadan yineleme sonlandırmak için deyimi `while` döngü. **Devam** deyimi geçirir denetim sonraki yinelemesini `while` deyimi.  
  
 Bu bir örnektir `while` deyimi:  
  
```  
while ( i >= 0 )   
{  
    string1[i] = string2[i];  
    i--;  
}  
```  
  
 Bu örnek karakterlerinden kopyalar `string2` için `string1`. Varsa `i` büyük veya 0 olarak eşit `string2[i]` atandığı `string1[i]` ve `i` düşülür. Zaman `i` ulaştığında veya onu yürütülmesi 0 düştüğünde `while` açıklamayı sonlandıran.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [while deyimi (C++)](../cpp/while-statement-cpp.md)