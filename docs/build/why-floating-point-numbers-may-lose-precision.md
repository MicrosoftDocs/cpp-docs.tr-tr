---
description: 'Hakkında daha fazla bilgi edinin: neden Floating-Point sayıların duyarlık kaybı olabileceğini'
title: Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 97daabd7342e94022f309937c9986b61cbc8668c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120776"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği

Kayan nokta ondalık değerleri genellikle tam bir ikili gösterimine sahip değildir. Bu, CPU 'nun kayan nokta verilerini nasıl temsil ettiğini gösteren bir yan etkiye sahiptir. Bu nedenle, bazı duyarlık kaybı yaşayabilirsiniz ve bazı kayan nokta işlemleri beklenmedik sonuçlar verebilir.

Bu davranış, aşağıdakilerden birinin sonucudur:

- Ondalık sayının ikili temsili tam değer olmayabilir.

- Kullanılan sayılar arasında tür uyuşmazlığı var (örneğin, float ve Double karıştırma).

Bu davranışı çözümlemek için, çoğu programcı değerin gerekenden daha büyük veya daha az olduğundan emin olun ya da duyarlık sağlayacak Ikili kodlanmış bir ondalık (BCD) kitaplığı alır ve kullanır.

Kayan nokta değerlerinin ikili temsili, kayan nokta hesaplamalarının duyarlığını ve doğruluğunu etkiler. Microsoft Visual C++, [IEEE kayan nokta biçimini](ieee-floating-point-representation.md)kullanır.

## <a name="example"></a>Örnek

```c
// Floating-point_number_precision.c
// Compile options needed: none. Value of c is printed with a decimal
// point precision of 10 and 6 (printf rounded value by default) to
// show the difference
#include <stdio.h>

#define EPSILON 0.0001   // Define your own tolerance
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))

int main() {
   float a, b, c;

   a = 1.345f;
   b = 1.123f;
   c = a + b;
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result
   if (c == 2.468)            // Comment this line for correct result
      printf_s("They are equal.\n");
   else
      printf_s("They are not equal! The value of c is %13.10f "
                "or %f",c,c);
}
```

```Output
They are not equal! The value of c is  2.4679999352 or 2.468000
```

## <a name="comments"></a>Yorumlar

EPSILON için, 1.192092896 e-07F olarak float için tanımlanan FLT_EPSILON sabitleri veya Double olarak 2.2204460492503131 e-olarak tanımlanan DBL_EPSILON kullanabilirsiniz. Bu sabitler için float. h dahil etmeniz gerekir. Bu sabitler en küçük pozitif sayı olan x olarak tanımlanır, örneğin x + 1.0, 1,0 değerine eşit değildir. Bu çok küçük bir sayı olduğundan, çok büyük sayılar içeren hesaplamalar için Kullanıcı tanımlı tolerans yapmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu iyileştirme](optimizing-your-code.md)
