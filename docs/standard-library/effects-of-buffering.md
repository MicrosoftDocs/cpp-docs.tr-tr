---
title: Ara belleğe almanın etkileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c387ce96d17e1db0dfefac6783dbdc87deeb94fb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
