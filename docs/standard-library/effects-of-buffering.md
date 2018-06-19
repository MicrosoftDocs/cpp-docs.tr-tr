---
title: Ara belleğe almanın etkileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c28deb0f5e30d3ec28fac4805a86645bebf27f22
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842384"
---
# <a name="effects-of-buffering"></a>Ara Belleğe Almanın Etkileri

Aşağıdaki örnek, ara belleğe almanın etkileri gösterir. Programın yazdırmasını bekleyebilirsiniz `please wait`, 5 saniye bekleyin ve sonra devam edin. Çıkışın arabelleğe alınıp olmadığından, mutlaka bu şekilde, ancak çalışmaz.

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

Mantıksal olarak, iş program yapmak için `cout` nesne gerekir boş kendisini ileti görünmesi olduğunda. Temizlemek için bir `ostream` nesne, göndermeden `flush` manipulator:

```cpp
cout <<"Please wait..." <<flush;
```

Bu adım, ileti önce bekleme yazdırır olduktan arabelleğini aktarır. Aynı zamanda `endl` manipulator, arabelleği temizler ve bir satır başı-satır besleme çıkarır veya kullanabileceğiniz `cin` nesnesi. Bu nesne (ile `cerr` veya `clog` nesneler) genellikle bağlı `cout` nesnesi. Bu nedenle, herhangi bir kullanımından `cin` (veya `cerr` veya `clog` nesneler) boşaltır `cout` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
