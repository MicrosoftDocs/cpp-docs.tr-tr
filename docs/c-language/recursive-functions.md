---
description: 'Daha fazla bilgi edinin: özyinelemeli Işlevler'
title: Özyinelemeli İşlevler
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 4ea374b0831fdcfa8c63243c6e59c017856f047f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176216"
---
# <a name="recursive-functions"></a>Özyinelemeli İşlevler

C programındaki herhangi bir işlev özyinelemeli olarak çağrılabilir; diğer bir deyişle, kendisini çağırabilir. Özyinelemeli çağrıların sayısı, yığının boyutuyla sınırlıdır. Yığın boyutunu ayarlama bağlayıcı seçenekleri hakkında bilgi için bkz. [ `/STACK` (yığın ayırmaları)](../build/reference/stack-stack-allocations.md) bağlayıcı seçeneği. İşlev her çağrıldığında, parametreleri ve ve değişkenleri için yeni depolama alanı, **`auto`** **`register`** önceki ve tamamlanmamış çağrıların değerlerinin üzerine yazılmaması için ayrılır. Parametrelere, yalnızca oluşturuldukları işlevin örneği doğrudan erişebilir. Önceki parametrelere, işlevin sonraki örnekleri tarafından doğrudan erişilemez.

Depolama ile beyan edilen değişkenlerin **`static`** her özyinelemeli çağrıda yeni depolama alanı gerektirmediğinden emin olduğunu unutmayın. Depolama alanları, programın ömrü boyunca kullanılır. Böyle bir değişkene yapılan her başvuru aynı depolama alanına erişir.

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

[İşlev çağrıları](../c-language/function-calls.md)
