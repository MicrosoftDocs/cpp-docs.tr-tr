---
title: Derleyici hatası C2319
ms.date: 11/04/2016
f1_keywords:
- C2319
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
ms.openlocfilehash: b3da0297558a9b8281f9c4756a54a577cc78a682
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747923"
---
# <a name="compiler-error-c2319"></a>Derleyici hatası C2319

' try/catch ' arkasından bir bileşik ifade gelmelidir. ' {' Eksik

`try` veya `catch` deyimden sonra bir `try` veya `catch` bloğu bulunamadı. Bloğun küme ayraçları içine alınması gerekir.

Aşağıdaki örnek C2319 oluşturur:

```cpp
// C2319.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch( C ) ;    // C2319
   // try the following line instead
   // catch( C ) {}
}
```
