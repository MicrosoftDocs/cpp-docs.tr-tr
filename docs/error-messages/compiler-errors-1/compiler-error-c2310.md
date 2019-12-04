---
title: Derleyici hatası C2310
ms.date: 11/04/2016
f1_keywords:
- C2310
helpviewer_keywords:
- C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
ms.openlocfilehash: 13558be562206c491d0f4b0a08f0d5763ba463e7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759028"
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
