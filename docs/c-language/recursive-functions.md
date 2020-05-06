---
title: Özyinelemeli İşlevler
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 82f0c820ab75fda4bae83db78fa402d7a07cb7fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232142"
---
# <a name="recursive-functions"></a>Özyinelemeli İşlevler

C programındaki herhangi bir işlev özyinelemeli olarak çağrılabilir; diğer bir deyişle, kendisini çağırabilir. Özyinelemeli çağrıların sayısı, yığının boyutuyla sınırlıdır. Yığın boyutunu ayarlama bağlayıcı seçenekleri hakkında bilgi için bkz. [/Stack (yığın ayırmaları)](../build/reference/stack-stack-allocations.md) (/Stack) bağlayıcı seçeneği. İşlev her çağrıldığında, parametrelere ve **Otomatik** ve **kayıt** değişkenlerine yönelik olarak, önceki ve tamamlanmamış çağrıların değerlerinin üzerine yazılmaması için yeni depolama alanı ayrılır. Parametrelere, yalnızca oluşturuldukları işlevin örneği doğrudan erişebilir. Önceki parametrelere, işlevin sonraki örnekleri tarafından doğrudan erişilemez.

**Statik** depolama ile belirtilen değişkenlerin her özyinelemeli çağrıda yeni depolama alanı gerektirmediğinden emin olduğunu unutmayın. Depolama alanları, programın ömrü boyunca kullanılır. Böyle bir değişkene yapılan her başvuru aynı depolama alanına erişir.

## <a name="example"></a>Örnek

Bu örnekte, özyinelemeli aramalar gösterilmektedir:

```C
int factorial( int num );      /* Function prototype */

int main()
{
    int result, number;
    .
    .
    .
    result = factorial( number );
}

int factorial( int num )      /* Function definition */
{
    .
    .
    .
    if ( ( num > 0 ) || ( num <= 10 ) )
        return( num * factorial( num - 1 ) );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Çağrıları](../c-language/function-calls.md)
