---
title: Ara Belleğe Almanın Etkileri
ms.date: 11/04/2016
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
ms.openlocfilehash: e10b28edffdfe3411f86c031bfd12ea886410e20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631445"
---
# <a name="effects-of-buffering"></a>Ara Belleğe Almanın Etkileri

Aşağıdaki örnek, ara belleğe almanın etkileri gösterir. Programın yazdırmak için bekleyebileceğiniz `please wait`, 5 saniye bekleyin ve ardından devam edin. Çıktısının arabelleğe alınıp olduğundan, mutlaka bu şekilde, ancak çalışmıyor.

```cpp
// effects_buffering.cpp
// compile with: /EHsc
#include <iostream>
#include <time.h>
using namespace std;

int main( )
{
   time_t tm = time( NULL ) + 5;
   cout << "Please wait...";
   while ( time( NULL ) < tm )
      ;
   cout << "\nAll done" << endl;
}
```

Programın mantıksal olarak çalışır hale getirmek için `cout` nesne gerekir boş kendisini görüntülenecek bir ileti olduğunda. Temizlemek için bir `ostream` nesne, göndermeden `flush` işleyici:

```cpp
cout <<"Please wait..." <<flush;
```

Bu adım, bekleme önce iletiyi yazdırmaz sağlayarak, arabelleğini aktarır. Ayrıca `endl` işleyici, arabelleği temizler ve çıkaran bir satır başı return-satır besleme veya kullanabileceğiniz `cin` nesne. Bu nesne (ile `cerr` veya `clog` nesneleri) genellikle bağlıdır `cout` nesne. Bu nedenle, kullanımı `cin` (veya `cerr` veya `clog` nesneleri) aktarır `cout` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
