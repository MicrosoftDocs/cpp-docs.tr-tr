---
title: Birli aritmetik işleçler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], unary
- tilde (~) one's complement operator
- bitwise-complement operator
- arithmetic operators [C++], unary
- + operator, unary operators
- unary operators
- exclamation points
- ~ operator, one's complement operator
- logical negation
- '! operator, unary arithmetic operators'
ms.assetid: 78c91415-d469-499e-9dfe-4435350fd333
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07fde5da39034ff180cad5b6678f27fe8252ce10
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="unary-arithmetic-operators"></a>Birli Aritmetik İşleçler
C birli artı, aritmetik olumsuzlama, tamamlayan ve mantıksal olumsuzlama işleçleri aşağıdaki listede açıklanmıştır:  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|**+**|Bir ifadenin başında parantez içinde gelen birli artı işleci, parantez içindeki işlemlerin gruplandırmasını zorlar. Birden fazla ilişkilendirilebilir veya değiştirebilir ikili işleç içeren ifadelerle kullanılır. İşlenen, aritmetik türde olmalıdır. Sonuç, işlenenin değeridir. Bir integral işlenen, integral yükseltme uygulanır. Sonucun türü yükseltilen işlenenin türüdür.|  
|**-**|Aritmetik olumsuzlama işlevi, işleneninin negatifini (ikinin tamamlayıcısı) üretir. İşlenen, bir tamsayı veya kayan değer olmalıdır. Bu işleç, her zamanki aritmetik dönüştürmeleri gerçekleştirir.|  
|`~`|Bitwise-complement (veya bitwise-NOT) işleci, işlenenin bit seviyesinde tamamlayıcısını üretir. İşlenen, tamsayı türünde olmalıdır. Bu işleç, her zamanki aritmetik dönüşümleri gerçekleştirir; sonuç, dönüştürme işleminden sonra işlenenin türündendir.|  
|**\!**|logical-negation (logical-NOT) işleci, işleneni doğru ise (sıfır dışında bir değer) 0 değerini üretir, işleneni yanlış ise (0) 1 değerini üretir. Sonuç `int` türündendir. İşlenen; bir tamsayı, kayan değer veya işaretçi değer olmalıdır.|  
  
 İşaretçilerde birli aritmetik işlemler geçersizdir.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örneklerde birli aritmetik işleçler gösterilmektedir:  
  
```  
short x = 987;  
    x = -x;  
```  
  
 Yeni değer, yukarıdaki örnekte `x` 987 ya da-987 negatif değil.  
  
```  
unsigned short y = 0xAAAA;  
    y = ~y;  
```  
  
 Bu örnekte, `y` öğesine atanan yeni değer, 0xAAAA veya 0x5555 değerine ilişkin birin tamamlayanıdır.  
  
```  
if( !(x < y) )  
```  
  
 `x`, `y` öğesine eşit veya ondan büyükse, ifadenin sonucu 1'dir (doğru). `x`, `y` öğesinden küçükse, sonuç 0'dır (yanlış).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)