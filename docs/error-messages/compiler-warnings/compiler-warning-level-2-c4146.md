---
title: Derleyici Uyarısı (düzey 2) C4146
ms.date: 11/04/2016
f1_keywords:
- C4146
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
ms.openlocfilehash: cf0c6e9e2c33887082f945f3f2200d808ac13cd2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174264"
---
# <a name="compiler-warning-level-2-c4146"></a>Derleyici Uyarısı (düzey 2) C4146

Birli eksi işleci işaretsiz türe uygulandı, sonuç hala işaretsiz

İşaretsiz türler yalnızca negatif olmayan değerler tutabilir, bu nedenle birli eksi (olumsuzlama) genellikle işaretsiz bir türe uygulandığında anlamlı değildir. Hem işlenen hem de sonuç negatif değil.

Pratikte, bu durum programcı 'nin-2147483648 olan en düşük tamsayı değerini ifade edilmeye çalıştığı zaman oluşur. İfade iki aşamada işlendiği için bu değer-2147483648 olarak yazılamaz:

1. 2147483648 sayısı değerlendirilir. 2147483647 en büyük tamsayı değerinden büyük olduğundan, 2147483648 türü [int](../../c-language/integer-types.md)değil, ancak `unsigned int`.

1. Birli eksi değeri işaretsiz bir sonuç ile, ayrıca 2147483648 olarak da gerçekleşen değere uygulanır.

Sonucun işaretsiz türü beklenmedik davranışa neden olabilir. Sonuç bir karşılaştırmada kullanılıyorsa, örneğin, diğer işlenen bir `int`olduğunda işaretsiz karşılaştırma kullanılabilir. Bu, aşağıdaki örnek programın yalnızca bir satır yazdırmasını açıklar.

`((unsigned int)1) > 2147483648` false olduğundan beklenen ikinci satır `1 is greater than the most negative int`yazdırılmıyor.

C4146 ' den kaçınabilirsiniz. Bu, **işaretli Int**türünde olan limit.h 'dan INT_MIN.

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
