---
title: varsa Statement (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- else
- if
dev_langs: C++
helpviewer_keywords:
- if keyword [C]
- else clauses
- else keyword [C]
- if keyword [C], if statement syntax
- nested statements
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1f7d7e43ab50cc50321aea79aad200231f719c3d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="if-statement-c"></a>if Deyimi (C)
**Varsa** deyimi denetimleri koşullu dallanma. Gövdesi bir **varsa** deyimi ifade değeri sıfır değilse yürütüldü. Sözdizimi **varsa** deyimi iki tür vardır.  
  
## <a name="syntax"></a>Sözdizimi  
 *Seçim deyimi*:  
 **varsa (***ifade***)***deyimi*   
  
 **varsa (***ifade***)***deyimi***başka***deyimi*   
  
 Her iki formlarda **varsa** deyimi, bir yapı dışındaki herhangi bir değer olabilir, ifadeler değerlendirilir, tüm yan etkileri dahil olmak üzere.  
  
 Sözdizimi ilk biçiminde ise *ifade* değeri true (sıfır), *deyimi* yürütülür. Varsa *ifade* false, *deyimi* göz ardı edilir. Sözdizimi ikinci biçiminde kullanan **başka**, ikinci *deyimi* varsa yürütülen *ifade* false olur. Öğesinden sonra geçişleri hem formlarıyla denetim **varsa** program sonraki deyiminde ifadesine deyimleri birini içermediği sürece bir **sonu**, **devam**, veya `goto`.  
  
 Örnekleri aşağıda verilmiştir **varsa** deyimi:  
  
```  
if ( i > 0 )  
    y = x / i;  
else   
{  
    x = i;  
    y = f( x );  
}  
```  
  
 Bu örnekte, deyim `y = x/i;` varsa yürütülen `i` 0'dan büyük. Varsa `i` 0, küçük veya eşit `i` atandığı `x` ve `f( x )` atandığı `y`. Oluşturan deyimi unutmayın **varsa** yan tümcesi noktalı virgül ile sona erer.  
  
 İç içe geçme zaman **varsa** deyimleri ve **başka** yan tümceleri, ifadeler ve yan tümceleri maksadınızı açıklamak bileşik deyimler gruplandırmak için ayraç kullanın. Hiçbir küme ayraçları mevcut olup olmadığını derleyici belirsizlikleri her ilişkilendirerek çözümler **başka** en yakın olan **varsa** , eksik bir **başka**.  
  
```  
if ( i > 0 )           /* Without braces */  
    if ( j > i )  
        x = j;  
    else  
        x = i;  
```  
  
 **Başka** yan tümcesi iç ile ilişkili **varsa** Bu örnekte deyimi. Varsa `i` küçük veya ona eşit herhangi bir değer atandığı 0 olarak `x`.  
  
```  
if ( i > 0 )   
{                      /* With braces */  
    if ( j > i )  
        x = j;  
}  
else  
    x = i;  
```  
  
 İç çevreleyen küme ayraçları **varsa** deyimi Bu örnekte olun **başka** dış yan tümcesi parçası **varsa** deyimi. Varsa `i` 0, küçük veya eşit `i` atandığı `x`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [if-else deyimi (C++)](../cpp/if-else-statement-cpp.md)