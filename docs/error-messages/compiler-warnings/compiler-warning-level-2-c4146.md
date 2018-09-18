---
title: Derleyici Uyarısı (Düzey 2) C4146 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4146
dev_langs:
- C++
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41d21f2be76e67c58599e214df764316dc845e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044632"
---
# <a name="compiler-warning-level-2-c4146"></a>Derleyici Uyarısı (Düzey 2) C4146

birli eksi işleci, sonuç hala işaretsiz işaretsiz türe uygulandı

Birli eksi (olumsuzlama) genellikle bir işaretsiz türe başvurulduğunda mantıklı şekilde imzasız türler yalnızca negatif olmayan değerleri tutabilir. Negatif olmayan hem işlenen hem de sonucu.

Pratikte, programcı -2147483648 en küçük tamsayı değeri express çalışırken bu oluşur. İfade iki aşamada işlendiğinden, bu değer -2147483648 yazılamıyor:

1. Sayı 2147483648 değerlendirilir. 2147483647 en büyük tamsayı değerinden daha büyük olduğundan, 2147483648 türünde değil [int](../../c-language/integer-types.md), ancak `unsigned int`.

1. Tek İşlenenli eksi işareti ile de 2147483648 özelleştirmede işaretsiz bir sonuç değeri uygulanır.

İşaretsiz bir sonuç türü beklenmeyen davranışlara neden olabilir. Sonucu bir Karşılaştırmada kullanılan sonra diğer işlenen olduğunda işaretsiz bir karşılaştırma, örneğin, kullanılabilir bir `int`. Bu, aşağıdaki örnek program tek bir satır neden yazdırır açıklanmaktadır.

Beklenen ikinci satırın `1 is greater than the most negative int`, çünkü yazdırılmaz `((unsigned int)1) > 2147483648` false'tur.

Int_mın türünde lımıts.h kullanarak C4146 kaçınabilirsiniz **signed int**.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4146 oluşturur:

```
// C4146.cpp
// compile with: /W2
#include <stdio.h>

void check(int i)
{
    if (i > -2147483648)   // C4146
        printf_s("%d is greater than the most negative int\n", i);
}

int main()
{
    check(-100);
    check(1);
}
```