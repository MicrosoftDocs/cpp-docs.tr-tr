---
title: return Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- return_cpp
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
ms.openlocfilehash: c8ea796ab40a2090ed9853377f7c9415914bc0e8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178988"
---
# <a name="return-statement-c"></a>return Deyimi (C++)

Bir işlevin yürütülmesini sonlandırır ve denetimi çağıran işleve (veya `main` işlevinden denetim aktarırsanız işletim sistemine) döndürür. Yürütme, çağrının hemen ardından gelen noktada çağırma işlevinde sürdürülür.

## <a name="syntax"></a>Sözdizimi

```
return [expression];
```

## <a name="remarks"></a>Açıklamalar

Varsa `expression` yan tümcesi, başlatma gerçekleştirilmiş gibi işlev bildiriminde belirtilen türe dönüştürülür. İfadenin türünden **dönüş** türüne dönüştürme geçici nesneler oluşturabilir. Geçiciler nasıl ve ne zaman oluşturulduğu hakkında daha fazla bilgi için bkz. [geçici nesneler](../cpp/temporary-objects.md).

`expression` yan tümcesinin değeri, çağırma işlevine döndürülür. İfade atlanırsa, işlevin dönüş değeri tanımsızdır. Oluşturucular ve Yıkıcılar ve **void**türündeki işlevler, **Return** deyiminde bir ifade belirtemez. Diğer tüm türlerin işlevleri, **Return** deyiminde bir ifade belirtmelidir.

Denetim akışı, işlev tanımını kapsayan bloğundan çıkıldığında, bir ifade olmayan bir **Return** deyimi yürütülürse, sonuç, bu durum aynı olur. Bu, değer döndüren olarak belirtilen işlevler için geçersizdir.

Bir işlevde herhangi bir sayıda **dönüş** ifadesi olabilir.

Aşağıdaki örnek, iki tamsayının en büyüğünü elde etmek için **Return** ifadesiyle bir ifade kullanır.

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
