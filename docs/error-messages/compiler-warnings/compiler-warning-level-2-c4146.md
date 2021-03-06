---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2) C4146'
title: Derleyici Uyarısı (düzey 2) C4146
ms.date: 11/04/2016
f1_keywords:
- C4146
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
ms.openlocfilehash: 85aebd34ed83ef14e306f7512689ccdfba713eec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326510"
---
# <a name="compiler-warning-level-2-c4146"></a>Derleyici Uyarısı (düzey 2) C4146

Birli eksi işleci işaretsiz türe uygulandı, sonuç hala işaretsiz

İşaretsiz türler yalnızca negatif olmayan değerler tutabilir, bu nedenle birli eksi (olumsuzlama) genellikle işaretsiz bir türe uygulandığında anlamlı değildir. Hem işlenen hem de sonuç negatif değil.

Pratikte, bu durum programcı 'nin-2147483648 olan en düşük tamsayı değerini ifade edilmeye çalıştığı zaman oluşur. İfade iki aşamada işlendiği için bu değer-2147483648 olarak yazılamaz:

1. 2147483648 sayısı değerlendirilir. 2147483647 en büyük tamsayı değerinden büyük olduğundan, 2147483648 türü [int](../../c-language/integer-types.md)değil, ancak **`unsigned int`** .

1. Birli eksi değeri işaretsiz bir sonuç ile, ayrıca 2147483648 olarak da gerçekleşen değere uygulanır.

Sonucun işaretsiz türü beklenmedik davranışa neden olabilir. Sonuç bir karşılaştırmada kullanılıyorsa, örneğin, diğer işlenen bir olduğunda işaretsiz karşılaştırma kullanılabilir **`int`** . Bu, aşağıdaki örnek programın yalnızca bir satır yazdırmasını açıklar.

Beklenen ikinci satır, yanlış olduğu için `1 is greater than the most negative int` yazdırılamaz `((unsigned int)1) > 2147483648` .

Tür olan limit.h INT_MIN kullanarak C4146 önleyebilirsiniz **`signed int`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4146 oluşturur:

```cpp
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
