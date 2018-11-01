---
title: Özyinelemeli İşlevler
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 69d7a1c82b7efb215b941aa5a6e9d94276bed529
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630132"
---
# <a name="recursive-functions"></a>Özyinelemeli İşlevler

C programındaki herhangi bir işlev özyinelemeli olarak çağrılabilir; diğer bir deyişle, kendisini çağırabilir. Özyinelemeli çağrıların sayısı, yığının boyutuyla sınırlıdır. Bkz: [/STACK (yığın ayırmaları)](../build/reference/stack-stack-allocations.md) (/ yığın) bağlayıcı seçeneği bağlayıcı hakkında bilgi için yığın boyutunu Ayarla seçenekleri. İşlevin çağrıldığı her zaman yeni bir depolama birimi ve parametreler için ayrılan **otomatik** ve **kaydetme** değişkenleri böylece değerlerini önceki, tamamlanmamış çağrılarındaki değerlerin üzerine. Parametrelere, yalnızca oluşturuldukları işlevin örneği doğrudan erişebilir. Önceki parametrelere, işlevin sonraki örnekleri tarafından doğrudan erişilemez.

Not ile bildirilen değişkenlerin **statik** depolama, her Özyinelemeli çağrı ile yeni depolama alanı gerektirmez. Depolama alanları, programın ömrü boyunca kullanılır. Böyle bir değişkene yapılan her başvuru aynı depolama alanına erişir.

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

## <a name="see-also"></a>Ayrıca Bkz.

[İşlev Çağrıları](../c-language/function-calls.md)