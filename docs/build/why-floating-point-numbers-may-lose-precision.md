---
title: Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 387b2f4a7156e42e59bd70c5a6f747943fb54ca7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313590"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği

Ondalık kayan nokta değerlerine tam bir ikili gösterim genellikle gerekmez. Bir yan etkisi, CPU kayan nokta verisi nasıl temsil ettiğini budur. Bu nedenle, karşılaşabileceğiniz bazı kesinlik kaybı ve bazı kayan nokta işlemleri beklenmeyen sonuçlara neden olabilir.

Bu davranış aşağıdakilerden birini sonucudur:

- Ondalık sayı ikili gösterimini tam olmayabilir.

- Kullanılan sayılar arasında (örneğin, karıştırma float ve çift) tür uyuşmazlığı var.

Davranışını çözümlemek için çoğu programcılar ya da değer büyükse veya daha düşük gerekli olduğundan emin olun veya alın ve duyarlık tutacaktır bir ikili kodlanmış ondalık (BCD) kitaplığını kullanın.

Kayan nokta değerleri ikili gösterimini duyarlılık ve kayan nokta hesaplamalarının doğruluğunu etkiler. Microsoft Visual C++ kullanan [IEEE kayan nokta biçimi](ieee-floating-point-representation.md).

## <a name="example"></a>Örnek

```
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

## <a name="comments"></a>Açıklamalar

EPSILON için kayan 1.192092896e olarak tanımlanan flt_epsılon sabitleri kullanın-07F, ya da çift 2.2204460492503131e olarak için tanımlanan dbl_epsılon-016. Bu sabitleri için float.h eklemeniz gerekir. Bu sabitler tanımlanan en küçük pozitif x sayı, söz konusu x + 1.0 1.0 eşit değil. Bu çok az sayıda olduğundan çok büyük sayılar içeren hesaplamalar için kullanıcı tanımlı dayanıklılık içermelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu İyileştirme](optimizing-your-code.md)
