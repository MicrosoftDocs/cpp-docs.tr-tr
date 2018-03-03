---
title: "C atama işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c839538b94ff8f80eabed98dbaf16e4009d3e500
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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