---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2309'
title: Derleyici hatası C2309
ms.date: 11/04/2016
f1_keywords:
- C2309
helpviewer_keywords:
- C2309
ms.assetid: 6303d5b5-72cf-42b8-92ce-b1eb48e80d48
ms.openlocfilehash: ed61e449ed12a15c72646f2648b1d4d15178e7f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282164"
---
# <a name="compiler-error-c2309"></a>Derleyici hatası C2309

catch işleyicisi parantez içinde bir özel durum bildirimi bekliyordu

Catch işleyicisinin parantez içine alınmış bir türü yoktur.

Aşağıdaki örnek C2309 oluşturur:

```cpp
// C2309.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch C {}   // C2309
   // try the following line instead
   // catch( C ) {}
}
```
