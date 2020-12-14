---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2298'
title: Derleyici hatası C2298
ms.date: 11/04/2016
f1_keywords:
- C2298
helpviewer_keywords:
- C2298
ms.assetid: eb0120ad-c850-4bdd-911d-0361229cc859
ms.openlocfilehash: d1e381b4c3c8d734b01c1177cba905ac99eff47c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235196"
---
# <a name="compiler-error-c2298"></a>Derleyici hatası C2298

' Operation ': üye işlev ifadesi işaretçisi üzerinde geçersiz işlem

Üye işlevi ifadesi için bir işaretçi üye işlevini çağırmalıdır.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2298 oluşturur.

```cpp
// C2298.cpp
#include <stdio.h>

struct X {
   void mf() {
      puts("in X::mf");
   }

   void mf2() {
      puts("in X::mf2");
   }
};

X x;
// pointer to member functions with no params and void return in X
typedef void (X::*pmf_t)();

// a pointer to member function X::mf
void (X::*pmf)() = &X::mf;

int main() {
   int (*pf)();
   pf = x.*pmf;   // C2298
   +(x.*pmf);     // C2298

   pmf_t pf2 = &X::mf2;
   (x.*pf2)();   // uses X::mf2
   (x.*pmf)();   // uses X::mf
}
```

Aşağıdaki örnek C2298 oluşturur.

```cpp
// C2298_b.cpp
// compile with: /c
void F() {}

class Measure {
public:
   void SetTrackingFunction(void (Measure::*fnc)()) {
      TrackingFunction = this->*fnc;   // C2298
      TrackingFunction = fnc;   // OK
      GlobalTracker = F;   // OK
   }
private:
   void (Measure::*TrackingFunction)(void);
   void (*GlobalTracker)(void);
};
```
