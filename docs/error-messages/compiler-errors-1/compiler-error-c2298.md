---
title: Derleyici Hatası C2298 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2298
dev_langs:
- C++
helpviewer_keywords:
- C2298
ms.assetid: eb0120ad-c850-4bdd-911d-0361229cc859
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31dde7ee3b1de221fae78c5b6d3398fe743c6fc9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064431"
---
# <a name="compiler-error-c2298"></a>Derleyici Hatası C2298

'operation': işaretçi üye işlev ifadesinde geçersiz işlem

Üye işlev ifadesi için bir işaretçi, üye işlevi çağırmanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2298 oluşturur.

```
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

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2298 oluşturur.

```
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