---
title: C Atama İşleçleri
description: Standart C dili atama işleçleri, söz dizimi ve anlamı.
ms.date: 10/30/2020
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
ms.openlocfilehash: 460e18772689de0d28fcfda3295a49b2f8a3c0d7
ms.sourcegitcommit: 4abc6c4c9694f91685cfd77940987e29a51e3143
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93238518"
---
# <a name="c-assignment-operators"></a>C Atama İşleçleri

Bir atama işlemi, sağ işleneninin değerini sol işlenen tarafından adlandırılan depolama konumuna atar. Bu nedenle, bir atama işleminin sol işleneni değiştirilebilir bir l değeri olmalıdır. Atama işleminden sonra, atama ifadesi sol işlenen değerine sahip olur, ancak bir l değeri değildir.

## <a name="syntax"></a>Syntax

*`assignment-expression`* :\
&emsp;*`conditional-expression`*\
&emsp;*`unary-expression`* *`assignment-operator`* *`assignment-expression`*

*`assignment-operator`* : biri<br/>
&emsp;**`=`** **`*=`** **`/=`** **`%=`** **`+=`** **`-=`** **`<<=`** **`>>=`** **`&=`** **`^=`** **`|=`**

C'deki atama işleçleri, tek bir işlemde değerleri hem dönüştürebilir hem de atayabilir. C, aşağıdaki atama işleçlerini sağlar:

|Operatör|Gerçekleştirilen İşlem|
|--------------|-------------------------|
|**`=`**|Basit atama|
|**`*=`**|Çarpma ataması|
|**`/=`**|Bölme ataması|
|**`%=`**|Geri kalan atama|
|**`+=`**|Toplama ataması|
|**`-=`**|Çıkarma ataması|
|**`<<=`**|Sola kaydırma ataması|
|**`>>=`**|Sağa kaydırma ataması|
|**`&=`**|Bit düzeyinde AND ataması|
|**`^=`**|Bit düzeyinde dışlamalı OR ataması|
|**`|=`**|Bit düzeyinde kapsamalı OR ataması|

Atama sırasında, sağdaki değerin türü soldaki değerin türüne dönüştürülür ve değer atama gerçekleştirildikten sonra sol işlenende depolanır. Sol işlenen bir dizi, işlev veya sabit olmamalıdır. İki türe bağlı olan belirli dönüştürme yolu, [tür dönüştürmelerinde](../c-language/type-conversions-c.md)ayrıntılı olarak özetlenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

- [Atama Işleçleri](../cpp/assignment-operators.md)
