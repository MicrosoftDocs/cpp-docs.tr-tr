---
title: Derleyici hatası C3723
ms.date: 11/04/2016
f1_keywords:
- C3723
helpviewer_keywords:
- C3723
ms.assetid: ef0fb1ff-3f9a-4093-a6b6-894d1ab0c4b9
ms.openlocfilehash: c45eee5ead680f63b85dcdd94e4ca099dabfeefc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752996"
---
# <a name="compiler-error-c3723"></a>Derleyici hatası C3723

' function ': olay çözümlenemedi

`function` hangi olayın çağrılacağını çözümleyemedi.

Aşağıdaki örnek C3723 oluşturur:

```cpp
// C3723.cpp
struct A {
   // To resolve, comment void f(int); and uncomment the __event function
   void f(int);
   // __event void f(int);
   void f(float);

};

struct B {
   void g(int);
   B(A* a) {
   __hook(&A::f, a, &B::g);   // C3723
   }
};

int main() {
}
```

`__hook` ve `__unhook`/CLR programlama ile uyumlu değildir.  Bunun yerine + = ve-= işleçlerini kullanın.

Aşağıdaki örnek C3723 oluşturur:

```cpp
// C3723b.cpp
// compile with: /clr
using namespace System;

public delegate void delegate1();

public ref class CPSource {
public:
   event delegate1^ event1;
};

public ref class CReceiver {
public:
   void Handler1() {
   }

   void UnhookAll(CPSource^ pSrc) {
      __unhook(&CPSource::event1, pSrc, &CReceiver::Handler1); // C3723
      // Try the following line instead.
      // pSrc->event1 -= gcnew delegate1(this, &CReceiver::Handler1);
   }
};

int main() {
}
```
