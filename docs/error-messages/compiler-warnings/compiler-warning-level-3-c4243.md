---
title: Derleyici Uyarısı (Düzey 3) C4243
ms.date: 11/04/2016
f1_keywords:
- C4243
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
ms.openlocfilehash: e08a8538c93681c59779f681812a9ba8f7e316a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636269"
---
# <a name="compiler-warning-level-3-c4243"></a>Derleyici Uyarısı (Düzey 3) C4243

'dönüştürme türünü' dönüştürme 'type1' 'type2' var, ancak erişilebilir değil

Bir taban sınıfı işaretçisini bir türetilmiş sınıf işaretçisine dönüştürülür, ancak türetilen sınıfın temel sınıf özel veya korumalı erişimle devralır.

Aşağıdaki örnek, C4243 oluşturur:

```
// C4243.cpp
// compile with: /W3
// C4243 expected
struct B {
   int f() {
      return 0;
   };
};

struct D : private B {};
struct E : public B {};

int main() {
   // Delete the following 2 lines to resolve.
   int (D::* d)() = (int(D::*)()) &B::f;
   d;

   int (E::* e)() = (int(E::*)()) &B::f; // OK
   e;
}
```