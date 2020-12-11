---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2680'
title: Derleyici hatası C2680
ms.date: 11/04/2016
f1_keywords:
- C2680
helpviewer_keywords:
- C2680
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
ms.openlocfilehash: 076a7409802a786f795ebac3cac83f8d5fdf968d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155689"
---
# <a name="compiler-error-c2680"></a>Derleyici hatası C2680

' Type ': ad için geçersiz hedef türü

Atama işleci, işaretçi veya başvuru olmayan bir türe dönüştürmeye çalıştı. [Dynamic_cast](../../cpp/dynamic-cast-operator.md) işleci yalnızca işaretçiler veya başvurular için kullanılabilir.

Aşağıdaki örnek C2680 oluşturur:

```cpp
// C2680.cpp
// compile with: /c
class A { virtual void f(); };
class B : public A {};

void g(B b) {
   A a;
   a = dynamic_cast<A>(b);   // C2680  target not a reference type
   a = dynamic_cast<A&>(b);   // OK
}
```

C2680, hedef tanımlanmadığında da gerçekleşebilir:

```cpp
// C2680b.cpp
// compile with: /clr /c
// C2680 expected
using namespace System::Collections;

// Delete the following line to resolve.
ref class A;   // not defined

// Uncomment the following line to resolve.
// ref class A{};

public ref class B : ArrayList {
   property A^ C[int] {
      A^ get(int index) {
         return dynamic_cast<A^>(this->default::get(index));
      }
      void set(int index, A^ value) {
         this->default::set(index, value);
      }
   }
};
```
