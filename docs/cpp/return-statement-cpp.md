---
title: return Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- return_cpp
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
ms.openlocfilehash: 6a1ed4f374f133abd0233826d1b58896d49576cf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225871"
---
# <a name="return-statement-c"></a>return Deyimi (C++)

Bir işlevin yürütülmesini sonlandırır ve denetimi çağırma işlevine (veya işlevden denetim aktarırsanız, işletim sistemine `main` ) döndürür. Yürütme, çağrının hemen ardından gelen noktada çağırma işlevinde sürdürülür.

## <a name="syntax"></a>Sözdizimi

```
return [expression];
```

## <a name="remarks"></a>Açıklamalar

Varsa `expression` yan tümcesi, başlatma gerçekleştirilmiş gibi işlev bildiriminde belirtilen türe dönüştürülür. İfadenin türünden **`return`** işlev türüne dönüştürme geçici nesneler oluşturabilir. Geçiciler nasıl ve ne zaman oluşturulduğu hakkında daha fazla bilgi için bkz. [geçici nesneler](../cpp/temporary-objects.md).

Yan tümcesinin değeri, `expression` çağırma işlevine döndürülür. İfade atlanırsa, işlevin dönüş değeri tanımsızdır. Oluşturucular ve Yıkıcılar ve türündeki işlevler **`void`** , deyiminde bir ifade belirtemez **`return`** . Diğer tüm türlerin işlevleri, deyiminde bir ifade belirtmelidir **`return`** .

Denetim akışı, işlev tanımını çevreleyen bloğundan çıkıldığında, bir **`return`** ifade olmayan bir deyim yürütülürse, sonuç aynı olur. Bu, değer döndüren olarak belirtilen işlevler için geçersizdir.

Bir işlevde herhangi bir sayıda deyim olabilir **`return`** .

Aşağıdaki örnek, **`return`** iki tamsayının en büyüğünü elde etmek için ifadesiyle bir ifade kullanır.

## <a name="example"></a>Örnek

```cpp
// return_statement2.cpp
#include <stdio.h>

int max ( int a, int b )
{
   return ( a > b ? a : b );
}

int main()
{
    int nOne = 5;
    int nTwo = 7;

    printf_s("\n%d is bigger\n", max( nOne, nTwo ));
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Atlama Deyimleri](../cpp/jump-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
