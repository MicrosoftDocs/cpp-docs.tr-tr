---
title: return Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- return_cpp
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
ms.openlocfilehash: 47bf9c50a2da039b0ffa074796a768290b732bb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507204"
---
# <a name="return-statement-c"></a>return Deyimi (C++)

Bir işlevin yürütülmesini sonlandırır ve denetim çağırma işlevine döndürür (veya işletim sistemine denetiminden aktarırsanız `main` işlevi). Çağıran işlevin çağrının hemen ardından bir noktada yürütmeyi devam ettirir.

## <a name="syntax"></a>Sözdizimi

```
return [expression];
```

## <a name="remarks"></a>Açıklamalar

`expression` Yan tümcesi varsa, dönüştürülür işlevi bildiriminde belirtilen türe alacağı bir başlatma gerçekleştirildi. İfade türü dönüştürme **dönüş** işlevin türünü, geçici nesneler oluşturabilir. Nasıl ve ne zaman türünü kopyalamıyorsa oluşturulur hakkında daha fazla bilgi için bkz. [geçici nesneler](../cpp/temporary-objects.md).

Değerini `expression` yan tümcesi, çağırma işlevine döndürülür. İfade atlanırsa, işlev dönüş değeri tanımsızdır. Oluşturucular ve Yıkıcılar ve işlevleri türü **void**, bir ifadede belirtemezsiniz **dönüş** deyimi. Diğer tüm türlerin işlevleri, bir ifadede belirtmelisiniz **dönüş** deyimi.

Denetim akışı işlev tanımı kapsayan blok çıktığında, olduğu gibi aynı sonucudur varsa bir **dönüş** deyimi bir ifade olmadan yürütülen. Bu, bir değer döndüren olarak bildirilen işlevler için geçersiz.

Herhangi bir sayıda bir işlev bulunabilir **dönüş** deyimleri.

Aşağıdaki örnek, bir ifade ile kullanır. bir **dönüş** deyimi iki tamsayının en büyük elde edilir.

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