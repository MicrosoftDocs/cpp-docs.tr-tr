---
description: 'Daha fazla bilgi edinin: arabelleğe alma etkileri'
title: Ara Belleğe Almanın Etkileri
ms.date: 11/04/2016
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
ms.openlocfilehash: dc46a5a7a390250be1872f9264235e133b9f58ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232726"
---
# <a name="effects-of-buffering"></a>Ara Belleğe Almanın Etkileri

Aşağıdaki örnek, arabelleğe alma işleminin etkilerini gösterir. Programın yazdırılmasını bekleyebilir `please wait` , 5 saniye bekleyip devam edebilirsiniz. Ancak, çıkış arabelleğe alınmadığı için bu şekilde çalışmaz.

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

Programın mantıksal olarak çalışmasını sağlamak için, `cout` ileti görüntülenecek şekilde nesnenin kendisini boş olması gerekir. Bir nesneyi temizlemek için `ostream` , uygulamayı şu şekilde gönderin `flush` :

```cpp
cout <<"Please wait..." <<flush;
```

Bu adım, iletinin bekleme öncesinde yazdırılmasını sağlayarak arabelleği boşaltır. Ayrıca, `endl` arabelleği temizlemeli ve bir satır başı satır akışı çıktısı veren ve öğesini kullanabilirsiniz `cin` . Bu nesne ( `cerr` veya nesneleriyle birlikte `clog` ) genellikle `cout` nesnesine bağlıdır. Bu nedenle, (veya `cin` `cerr` nesnelerinin veya nesneleri) herhangi bir kullanımı `clog` nesneyi temizler `cout` .

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış akışları](../standard-library/output-streams.md)
