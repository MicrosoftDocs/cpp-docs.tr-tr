---
title: Parantezlerdeki ifadeler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parentheses
- expression evaluation, evaluation order
- expressions [C++], evaluating
- parentheses, expressions
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c09209a323a06f883a54e7ecaec17c55a3bc6205
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-in-parentheses"></a>Parantezlerdeki İfadeler
Tür veya kapalı ifadenin değerini değiştirmeden herhangi işleneni parantez içine alın. Örneğin, ifade:  
  
```  
( 10 + 5 ) / 5  
```  
  
 parantezler `10 + 5` değerini anlamına `10 + 5` ilk olarak değerlendirilir ve bölümünün sol işleneni olur (**/**) işleci. Sonucu `( 10 + 5 ) / 5` 3'tür. Parantez olmadan `10 + 5 / 5` 11'e değerlendirmek.  
  
 Parantez işlenen bir ifadede gruplandırılır şeklinizi etkiler rağmen tüm durumlarda değerlendirme belirli bir sıraya garanti edemez. Örneğin, hangi değerini parantez ne ifadesini soldan sağa gruplandırması garanti `i` alt ifadelerin birini olacaktır:  
  
```  
( i++ +1 ) * ( 2 + i )  
```  
  
 Herhangi bir sırada Çarpmanın iki kenara değerlendirmek derleyici ücretsizdir. İlk değeri `i` sıfırsa, tam da bu iki ifade ifadenin:  
  
```  
( 0 + 1 + 1 ) * ( 2 + 1 )   
( 0 + 1 + 1 ) * ( 2 + 0 )  
```  
  
 Özel durumlar yan etkileri kaynaklanan içinde ele alınmıştır [yan etkileri](../c-language/side-effects.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Birincil İfadeler](../c-language/c-primary-expressions.md)