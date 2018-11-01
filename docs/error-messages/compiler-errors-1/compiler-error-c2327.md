---
title: Derleyici Hatası C2327
ms.date: 11/04/2016
f1_keywords:
- C2327
helpviewer_keywords:
- C2327
ms.assetid: 95278c95-d1f9-4487-ad27-53311f5e8112
ms.openlocfilehash: abc9aa92c41947a2536e53108c1fb646792a8202
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652315"
---
# <a name="compiler-error-c2327"></a>Derleyici Hatası C2327

'symbol': tür adı, statik veya numaralandırıcı değil

İç içe geçmiş bir sınıf içindeki kod, bir tür adı, statik bir üyeye veya numaralandırıcı değil kapsayan sınıf üyesi erişmeyi dener.

İle derlerken **/CLR**, yaygın bir nedeni C2327 için özellik türü olarak aynı ada sahip bir özelliktir.

Aşağıdaki örnek, C2327 oluşturur:

```
// C2327.cpp
int x;
class enclose {
public:
   int x;
   static int s;
   class inner {
      void f() {
         x = 1;   // C2327; enclose::x is not static
         s = 1;   // ok; enclose::s is static
         ::x = 1;   // ok; ::x refers to global
      }
   };
};
```

Bir türün adını bir üye adıyla gizliyse C2327 da meydana gelebilir:

```
// C2327b.cpp
class X {};

class S {
   X X;
   // try the following line instead
   // X MyX;
   X other;   // C2327, rename member X
};
```

C2327 de tam olarak parametrenin veri türünü belirtmek için gerek duyduğunuz bu durumda, bu özelliği kullanabilirsiniz:

```
// C2327c.cpp
// compile with: /c
struct A {};

struct B {
   int A;
   void f(A a) {   // C2327
   void f2(struct A a) {}   // OK
   }
};
```

Aşağıdaki örnek, C2327 oluşturur:

```
// C2327d.cpp
// compile with: /clr /c
using namespace System;

namespace NA {
   public enum class E : Int32 {
      one = 1,
      two = 2,
      three = 3
   };

   public ref class A {
   private:
      E m_e;
   public:
      property E E {
         NA::E get() {
            return m_e;
         }
         // At set, compiler doesn't know whether E is get_E or
         // Enum E, therefore fully qualifying Enum E is necessary
         void set( E e ) {   // C2327
            // try the following line instead
            // void set(NA::E e) {
            m_e = e;
         }
      }
   };
}
```

Aşağıdaki örnek, bir özellik, özellik türü ile aynı ada sahip olduğunda C2327 gösterir:

```
// C2327f.cpp
// compile with: /clr /c
public value class Address {};

public ref class Person {
public:
   property Address Address {
      ::Address get() {
         return address;
      }
      void set(Address addr) {   // C2327
      // try the following line instead
      // set(::Address addr) {
         address = addr;
      }
   }
private:
   Address address;   // C2327
   // try the following line instead
   // ::Address address;
};
```
