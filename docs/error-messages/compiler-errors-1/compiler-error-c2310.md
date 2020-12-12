---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2310'
title: Derleyici hatası C2310
ms.date: 11/04/2016
f1_keywords:
- C2310
helpviewer_keywords:
- C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
ms.openlocfilehash: 235a80c8b144e348ec650baea7fd372de810b7a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282202"
---
# <a name="compiler-error-c2310"></a>Derleyici hatası C2310

catch işleyicilerinin bir tür belirtmesi gerekir

Bir catch işleyicisi tür veya birden çok tür belirtti.

Aşağıdaki örnek C2310 oluşturur:

```cpp
// C2310.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "Out of memory!";
   }
   catch( int ,int) {}   // C2310 two types
   // try the following line instead
   // catch( int)  {}
}
```
