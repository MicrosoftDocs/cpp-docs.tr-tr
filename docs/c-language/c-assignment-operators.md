---
title: C atama işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a13f3b36ae4f5bbd11f170d78d735427882d2ff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-assignment-operators"></a>C Atama İşleçleri
Bir atama işlemi, sağ işleneninin değerini sol işlenen tarafından adlandırılan depolama konumuna atar. Bu nedenle, bir atama işleminin sol işleneni değiştirilebilir bir l değeri olmalıdır. Atama işleminden sonra, atama ifadesi sol işlenen değerine sahip olur, ancak bir l değeri değildir.  
  
 **Sözdizimi**  
  
 *atama ifadesi*:  
 *Koşullu ifade*  
  
 *Tek terimli ifadesi atama işleci atama ifadesi*  
  
 *atama işleci*: biri  
 **= \*=** `/=` `%=` `+=` **-= <\<= >>= &=** `^=` `|=`  
  
 C'deki atama işleçleri, tek bir işlemde değerleri hem dönüştürebilir hem de atayabilir. C, aşağıdaki atama işleçlerini sağlar:  
  
|İşleç|Gerçekleştirilen İşlem|  
|--------------|-------------------------|  
|**=**|Basit atama|  
|**\*=**|Çarpma ataması|  
|`/=`|Bölme ataması|  
|`%=`|Geri kalan atama|  
|`+=`|Toplama ataması|  
|**-=**|Çıkarma ataması|  
|**<\<=**|Sola kaydırma ataması|  
|**>>=**|Sağa kaydırma ataması|  
|**&=**|Bit düzeyinde AND ataması|  
|`^=`|Bit düzeyinde dışlamalı OR ataması|  
|`&#124;=`|Bit düzeyinde kapsamalı OR ataması|  
  
 Atama sırasında, sağdaki değerin türü soldaki değerin türüne dönüştürülür ve değer atama gerçekleştirildikten sonra sol işlenende depolanır. Sol işlenen bir dizi, işlev veya sabit olmamalıdır. İki türlerine bağlıdır, belirli dönüştürme yolunu ayrıntılı olarak gösterilmiştir [tür dönüşümleri](../c-language/type-conversions-c.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama İşleçleri](../cpp/assignment-operators.md)