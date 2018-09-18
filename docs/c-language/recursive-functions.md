---
title: Özyinelemeli İşlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 187c176aa90997e4841bc22e468fab079f9e8b2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062767"
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