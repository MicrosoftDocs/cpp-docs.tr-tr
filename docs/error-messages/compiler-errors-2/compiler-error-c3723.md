---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3723'
title: Derleyici hatası C3723
ms.date: 11/04/2016
f1_keywords:
- C3723
helpviewer_keywords:
- C3723
ms.assetid: ef0fb1ff-3f9a-4093-a6b6-894d1ab0c4b9
ms.openlocfilehash: 9df2c13598ee634964b519be104eb406ab078ea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239005"
---
# <a name="compiler-error-c3723"></a>Derleyici hatası C3723

> ' function ': olay çözümlenemedi

`function` Hangi olayın çağrılacağını çözümlenemedi.

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

**`__hook`** ve **`__unhook`** programlamayla uyumlu değildir **`/clr`** .  Bunun yerine + = ve-= işleçlerini kullanın.

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
