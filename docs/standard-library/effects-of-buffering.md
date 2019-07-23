---
title: Ara Belleğe Almanın Etkileri
ms.date: 11/04/2016
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
ms.openlocfilehash: 23e241794455a92f9e3628a786d75a6d4c7b037e
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376322"
---
# <a name="effects-of-buffering"></a>Ara Belleğe Almanın Etkileri

Aşağıdaki örnek, arabelleğe alma işleminin etkilerini gösterir. Programın yazdırılmasını `please wait`bekleyebilir, 5 saniye bekleyip devam edebilirsiniz. Ancak, çıkış arabelleğe alınmadığı için bu şekilde çalışmaz.

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

Programın mantıksal olarak çalışmasını sağlamak için, `cout` ileti görüntülenecek şekilde nesnenin kendisini boş olması gerekir. Bir `ostream` nesneyi temizlemek için, `flush` uygulamayı şu şekilde gönderin:

```cpp
cout <<"Please wait..." <<flush;
```

Bu adım, iletinin bekleme öncesinde yazdırılmasını sağlayarak arabelleği boşaltır. Ayrıca `endl` , arabelleği temizlemeli ve bir satır başı satır akışı çıktısı veren ve öğesini `cin` kullanabilirsiniz. Bu nesne ( `cerr` veya `clog` nesneleriyle birlikte) genellikle `cout` nesnesine bağlıdır. Bu nedenle, `cin` ( `cerr` veya `clog` nesnelerinin`cout` veya nesneleri) herhangi bir kullanımı nesneyi temizler.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
