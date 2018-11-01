---
title: C Atama İşleçleri
ms.date: 06/14/2018
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
ms.openlocfilehash: 5080f390d302840e9e7b349cf1c21ab618ae48db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657034"
---
# <a name="c-assignment-operators"></a>C Atama İşleçleri

Bir atama işlemi, sağ işleneninin değerini sol işlenen tarafından adlandırılan depolama konumuna atar. Bu nedenle, bir atama işleminin sol işleneni değiştirilebilir bir l değeri olmalıdır. Atama işleminden sonra, atama ifadesi sol işlenen değerine sahip olur, ancak bir l değeri değildir.

## <a name="syntax"></a>Sözdizimi

*atama ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tekli ifade* *atama işleci* *atama ifadesi*

*atama işleci*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**=** **\*=** **/=** **%=** **+=** **-=** **\<\<=** **>>=** **&=** **^=** **|=**

C'deki atama işleçleri, tek bir işlemde değerleri hem dönüştürebilir hem de atayabilir. C, aşağıdaki atama işleçlerini sağlar:

|İşleç|Gerçekleştirilen İşlem|
|--------------|-------------------------|
|**=**|Basit atama|
|**&#42;=**|Çarpma ataması|
|**/=**|Bölme ataması|
|**%=**|Geri kalan atama|
|**+=**|Toplama ataması|
|**-=**|Çıkarma ataması|
|**<\<=**|Sola kaydırma ataması|
|**>>=**|Sağa kaydırma ataması|
|**&=**|Bit düzeyinde AND ataması|
|**^=**|Bit düzeyinde dışlamalı OR ataması|
|**&#124;=**|Bit düzeyinde kapsamalı OR ataması|

Atama sırasında, sağdaki değerin türü soldaki değerin türüne dönüştürülür ve değer atama gerçekleştirildikten sonra sol işlenende depolanır. Sol işlenen bir dizi, işlev veya sabit olmamalıdır. İki türe bağlı olan özel dönüştürme yolu, ayrıntılı olarak açıklandığı [tür dönüştürmeleri](../c-language/type-conversions-c.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Atama İşleçleri](../cpp/assignment-operators.md)