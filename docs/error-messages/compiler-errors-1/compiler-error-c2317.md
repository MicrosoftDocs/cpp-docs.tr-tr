---
title: Derleyici hatası C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: 95444951106d74d01efe84f829b606eb2c547c99
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221269"
---
# <a name="compiler-error-c2317"></a>Derleyici hatası C2317

' number ' satırında başlayan ' TRY ' bloğunda hiç catch işleyicisi yok

Bir **`try`** bloğun en az bir catch işleyicisi olmalıdır.

Aşağıdaki örnek C2317 oluşturur:

```cpp
// C2317.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   // C2317, no catch handler
}
```

Olası çözüm:

```cpp
// C2317b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   catch(char*) {}
}
```
